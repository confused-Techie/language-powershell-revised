# Language-PowerShell-Revised Pulsar Package

Updated, revised PowerShell Syntax Highlighting Support in Pulsar.

## Developing

This Grammar is based solely off of the wonderful [PowerShell TextMate](https://github.com/PowerShell/EditorSyntax) Grammar.

The same exact way that [`language-powershell`](https://github.com/jrsconfitto/language-powershell/) is, but that one has fallen out of maintenance.

To update this grammar, you'll first need to clone [PowerShell's EditorSyntax](https://github.com/PowerShell/EditorSyntax) locally then run the following to build the grammar file:

```cmd
.\build.ps1 -Test
```

Once the grammar file is built there you can take the resulting `./grammars/powershell.tmLanguage.json` file and use it to replace the `./grammars/powershell.json` file within this package.

Lastly compare against the `./grammar.patch` file to ensure the very few changes needed are applied:

* Such as removing needless data
* Specifying the file types intended to be compatible with this file.

Once you are done making your changes ensure to generate a new PATCH file like so:

```cmd
git diff --no-index --patch ./grammars/powershell.tmLanguage .json ../language-powershell-revised/grammars/powershell.json --output ../language-powershell-revised/grammar.patch
```

> The last SHA pulled from [EditorSyntax](https://github.com/PowerShell/EditorSyntax) - [c0372a1](https://github.com/PowerShell/EditorSyntax/commit/c0372a1d2df136ca6b3d1a9f7b85031dedf117f9) [ Jan 2, 2022 ]
