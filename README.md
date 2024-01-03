### HTB Visual machine

Intial foothold repository

1. Using Evilsln technique to execute code in application accepting git link
- Application accepting git link as input => Clone repo and build the project

- Ultilize `PreBuildEvent` attribute in `.csproj` file to execute commands:
  
    > \<Target Name="PreBuild" BeforeTargets="PreBuildEvent">
    >  \<Exec Command="call prebuild.bat" />
    >  \</Target>
  
- Referenece: `https://github.com/cjm00n/EvilSln`



1. Create a C# project so with malicious `.csproj`:
- Create new C# project uing: `dotnet new console --framework net6.0 --use-program-main`
- Add a new sln template to project: `dotnet new sln`
- Add project to sln template: `dotnet sln add .\Visual.csproj`
- Inject reverse shell into `Visual.csproj`