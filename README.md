Environment:
* Vim version: 8.2 including patch 1-4473
* omnisharp-vim up-to-date (`8595016 27 hours ago Nick Jensen    Merge pull request #757 from kit494way/fix-selector-clap`)
* omnisharp-roslyn version: 1.38.0.0
* dotnet sdk version: 6.0.101

Reproduction:
* run `dotnet build` on the solution
* go to the file test
* run `OmniSharpDebugTest`

Witnessed behaviour:
```
Error detected while processing function OmniSharp#proc#vimOutHandler[11]..OmniSharp#stdio#HandleResponse[42]..<SNR>172_DebugTestsRH:
line    1:
E121: Undefined variable: FileName
```

Additional information:
* I tried using dotnet core 5 via a `global.json` and updating the `Test.csproj` dotnet version
  * The error stayed
  * but I noticed I get `Error: "Failed to connect to 'dotnet test' process"   - this may indicate a failed build` when running `OmniSharpRunTest` and `OmniSharpRunTestsInFile`
  * For information, `dotnet test` works correctly from the command line
