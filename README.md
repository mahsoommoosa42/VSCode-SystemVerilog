[![Build Status](https://dev.azure.com/CPS-External/VSCode-SystemVerilog/_apis/build/status/VSCode-SystemVerilog%20Github?branchName=master)](https://dev.azure.com/CPS-External/VSCode-SystemVerilog/_build/latest?definitionId=5&branchName=master)

# SystemVerilog - Language Support 

This package adds language support for Verilog/SystemVerilog. It supports SystemVerilog syntax, with planned support for signal intelliSense.

- If you find a bug, or would like a feature; Add it as an [Issue](https://github.com/eirikpre/VSCode-SystemVerilog/issues) or a [Pull-Request](https://github.com/eirikpre/VSCode-SystemVerilog/pulls)

## Features
- Elaborate Syntax Highlighting

    ![syntax_example](docs/syntax_example_adder.PNG)
- Go to symbol in document
- Go to symbol in workspace folder (indexed modules/interfaces/programs/classes/packages)
- Keyboard shortcut to show the top symbols: `Ctrl + T`
- Go to definition (_Works for module/interface/program/class/package names, and for ports to!_)

    ![goToDef_example](docs/goToDef_demo.gif)

- Code snippets for many common blocks
- Instantiate module from already indexed module

    ![moduleInit_example](docs/moduleInit_demo.gif)

- Linter capabilites with simulators ( [More info on the wiki](https://github.com/eirikpre/VSCode-SystemVerilog/wiki) )

## Recommendations
- If you have netlists in your workspace you can exclude them in the settings, Eg: `**/syn/**`
- Disclaimer: This is not a functional HDL tool that will compile and simulate your code, but this extension will make it easier and more user-friendly to write/navigate SystemVerilog

## Settings
- Disable indexing
- Exclude files from indexing
- Number of files to process in parallel during indexing
- Verilator Launch Configuration
  * Default: _verilator --sv --lint-only --language 1800-2012 --Wall_
  * If not in path, replace _verilator_ with the appropriate command
- `systemverilog.compileOnSave`: _Boolean_, compile files when saved.
  * Default: *true*
- `systemverilog.compilerType`: _String_, drop down list to select a compiler type.
  * Default: *Verilator*

## Known Issues
- Starting up may be a little bit slow if it's a large workspace with many `.sv` files because of indexing
- `randcase` is not matching with `endcase` brackets properly

## Future
- Tree view of module hierarchy
- References document
- IntelliSense support
- Back-end Language server for Systemverilog

## Release Notes
See changelog for mode details
### 0.8
- Compile an opened document using `Verilator` simulator, display errors/warnings as `Diagnostics` in documents: `oehaddouchi`
- Compile documents on save feature using `Verilator` simulator
- Added output channel `SystemVerilog`
- Added an `LSP`, set it to communicate with the extension's client
- Keep track of the recently used modules in the indexer
- Added diagnostic support for `VCS` compiler
### 0.7
- Instantiate module from already indexed module, thanks to `oehaddouchi`
- Update to documentSymbolProvider
### 0.6
- Stability and performance upgrade
- PCRE Regexes
### 0.5
- HoverProvider added, thanks to `toastedcornflakes`
- Improvements to DocumentSymbolProvider to better support Hover
### 0.4
- Added setting to exclude folders from indexing
### 0.3
- DefinitionProvider fetching from indexed modules implemented
- Indexing is now more safe, and will work for large workspaces
### 0.2
- Alpha 2 release with expanded syntax highlighting and snippets
- Indexing of every module/interface/program/class in workspace
### 0.1
- Alpha 1 release with syntax highlighting, and go to symbols

