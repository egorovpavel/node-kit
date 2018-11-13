# Node-Kit

This NuGet package allows you to use Node.js without requiring a local install. It contains latest versions for following platforms:

- Windows x64
- Linux x64
- OSX 

It also ships with `npm`. 

# Usage

Main intetion of this plugin is to be able to pull `npm` dependencies and run diferent tasks as part of preBuild tasks.

```xml
<Target Name="BeforeBuild">
    <Exec Command="..\packages\Node-Kit.11.1.0\node\node.exe ..\packages\Node-Kit.11.1.0\npm\bin\npm-cli.js install" Condition=" '$(OS)' == 'Windows_NT' "/>
    <Exec Command="..\packages\Node-Kit.11.1.0\node\node.exe ..\packages\Node-Kit.11.1.0\npm\bin\npm-cli.js update" Condition=" '$(OS)' == 'Windows_NT' "/>
    <Exec Command="..\packages\Node-Kit.11.1.0\node\node.exe .\node_modules\gulp\bin\gulp.js build" Condition=" '$(OS)' == 'Windows_NT' "/>
</Target>
```

