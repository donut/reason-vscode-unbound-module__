```
VSCode: Version 1.33.1 (1.33.1)
reason-vscode: 1.5.2
```

When there is any other .ml file in the lib directory, reason-vscode gives the
error in lib.ml:

> File "command line", line 1:
> Error: Unbound module Lib__

If you remove lib/goomba.ml and re-compile, everything is fine.

Relevant issues:

* https://github.com/jaredly/reason-language-server/issues/255
* https://github.com/jaredly/reason-language-server/issues/105


Things tried:

* [Moving to dune <= 1.6](https://github.com/jaredly/reason-language-server/issues/105#issuecomment-477140975)
* [Downgrading OCaml](https://github.com/jaredly/reason-language-server/issues/105#issuecomment-415058074)


node_modules/.lsp/debug.log:
```log
Hello - from /Users/donut/.vscode/extensions/jaredly.reason-vscode-1.5.2/bin.native
Previous log location: /var/folders/64/z8mfxtld7fgdcsqx385q8vwm0000gn/T/lsp.log
Sending notification {"jsonrpc": "2.0", "method": "client/registerCapability", "params": {"registrations": [{"id": "watching", "method": "workspace/didChangeWatchedFiles", "registerOptions": {"watchers": [{"globPattern": "**/bsconfig.json", "globPattern": "**/.merlin"}]}}]}}
Sending response {"id": 0, "jsonrpc": "2.0", "result": {"capabilities": {"textDocumentSync": 1, "hoverProvider": true, "completionProvider": {"resolveProvider": true, "triggerCharacters": ["."]}, "signatureHelpProvider": {"triggerCharacters": ["("]}, "definitionProvider": true, "typeDefinitionProvider": true, "referencesProvider": true, "documentSymbolProvider": true, "codeActionProvider": true, "executeCommandProvider": {"commands": ["reason-language-server.add_to_interface_inner"]}, "codeLensProvider": {"resolveProvider": true}, "documentHighlightProvider": true, "documentRangeFormattingProvider": true, "documentFormattingProvider": true, "documentFormattingProvider": true, "renameProvider": true}}}
Read message 
{"jsonrpc":"2.0","method":"initialized","params":{}}
Read message 
{"jsonrpc":"2.0","method":"workspace/didChangeConfiguration","params":{"settings":{"reason_language_server":{"location":"","build_system_override_by_root":{},"refmt":"","lispRefmt":"","format_width":"80","per_value_codelens":false,"dependencies_codelens":true,"opens_codelens":true,"show_module_path_on_hover":true,"reloadOnChange":false,"show_debug_errors":false,"autoRebuild":true}}}}
Read message 
{"jsonrpc":"2.0","method":"textDocument/didOpen","params":{"textDocument":{"uri":"file:///Users/donut/work/rls-vscode-weirdness/lib/lib.ml","languageId":"ocaml","version":1,"text":"\nlet metoo () =\n  print_endline \"Welcome?\""}}}
Found a `dune` file at /Users/donut/work/rls-vscode-weirdness/lib
]] Making a new jbuilder package at /Users/donut/work/rls-vscode-weirdness/lib
=== Project root: /Users/donut/work/rls-vscode-weirdness
Detected `esy` dependency manager for local use
=== Build dir:    /Users/donut/work/rls-vscode-weirdness/_esy/default/store/b/goombas-16812775
Get ocaml stdlib dirs
Include subdirs? no :/
Got a compiled base /Users/donut/work/rls-vscode-weirdness/_esy/default/store/b/goombas-16812775/default/lib
Local file: /Users/donut/work/rls-vscode-weirdness/lib/goomba.ml
Local .cmt file: /Users/donut/work/rls-vscode-weirdness/_esy/default/store/b/goombas-16812775/default/lib/Goomba.cmt
Local file: /Users/donut/work/rls-vscode-weirdness/lib/lib.ml
Local .cmt file: /Users/donut/work/rls-vscode-weirdness/_esy/default/store/b/goombas-16812775/default/lib/Lib.cmt
>> Collecting deps for /Users/donut/.esy/3___________________________________________________________________/i/ocaml-4.6.10-1dc037cc/lib/ocaml
Depedency dirs /Users/donut/.esy/3___________________________________________________________________/i/ocaml-4.6.10-1dc037cc/lib/ocaml
>> Build system running: esy
>>> stdout

>>> stderr
info esy 0.5.6 (using package.json)
Affected files: 
Cleaning bsconfig.json
Sending notification {"jsonrpc": "2.0", "method": "textDocument/publishDiagnostics", "params": {"uri": "file:///Users/donut/work/rls-vscode-weirdness/lib/bsconfig.json", "diagnostics": []}}
Running diagnostics for file:///Users/donut/work/rls-vscode-weirdness/lib/lib.ml
➡️ running bsc /Users/donut/.esy/3___________________________________________________________________/i/ocaml-4.6.10-1dc037cc/bin/ocamlopt.opt -c -I '/Users/donut/work/rls-vscode-weirdness/_esy/default/store/b/goombas-16812775/default/lib' -I '/Users/donut/.esy/3___________________________________________________________________/i/ocaml-4.6.10-1dc037cc/lib/ocaml' -bin-annot -open Lib__ -w @a-4-29-40-41-42-44-45-48-58-59-60-40 -strict-sequence -strict-formats -short-paths -keep-locs -impl /Users/donut/work/rls-vscode-weirdness/_esy/default/store/b/goombas-16812775/.lsp/Lib.ast with pwd /Users/donut/work/rls-vscode-weirdness/lib
<< Making lastDefinitions with type error for file:///Users/donut/work/rls-vscode-weirdness/lib/lib.ml
type error here File "command line", line 1:
Error: Unbound module Lib__
Sending notification {"jsonrpc": "2.0", "method": "textDocument/publishDiagnostics", "params": {"uri": "file:///Users/donut/work/rls-vscode-weirdness/lib/lib.ml", "diagnostics": [{"range": {"start": {"line": 0, "character": 0}, "end": {"line": 0, "character": 0}}, "message": "File \"command line\", line 1:\nError: Unbound module Lib__", "severity": 1}]}}
Read message 
{"jsonrpc":"2.0","id":1,"method":"textDocument/documentSymbol","params":{"textDocument":{"uri":"file:///Users/donut/work/rls-vscode-weirdness/lib/lib.ml"}}}
[server] Got a method textDocument/documentSymbol
[server] processing took 0.00596046447754ms
Sending response {"id": 1, "jsonrpc": "2.0", "result": []}
Read message 
{"jsonrpc":"2.0","id":2,"method":"textDocument/codeAction","params":{"textDocument":{"uri":"file:///Users/donut/work/rls-vscode-weirdness/lib/lib.ml"},"range":{"start":{"line":2,"character":25},"end":{"line":2,"character":25}},"context":{"diagnostics":[]}}}
[server] Got a method textDocument/codeAction
[server] processing took 0.0138282775879ms
Sending response {"id": 2, "jsonrpc": "2.0", "result": null}
Read message 
{"jsonrpc":"2.0","id":3,"method":"textDocument/codeLens","params":{"textDocument":{"uri":"file:///Users/donut/work/rls-vscode-weirdness/lib/lib.ml"}}}
[server] Got a method textDocument/codeLens
[server] processing took 0.00905990600586ms
Sending response {"id": 3, "jsonrpc": "2.0", "result": [{"range": {"start": {"line": 0, "character": 0}, "end": {"line": 0, "character": 0}}, "command": {"title": "Dependencies: ", "command": ""}}]}
Read message 
{"jsonrpc":"2.0","id":4,"method":"textDocument/codeAction","params":{"textDocument":{"uri":"file:///Users/donut/work/rls-vscode-weirdness/lib/lib.ml"},"range":{"start":{"line":2,"character":25},"end":{"line":2,"character":25}},"context":{"diagnostics":[]}}}
[server] Got a method textDocument/codeAction
[server] processing took 0.00500679016113ms
Sending response {"id": 4, "jsonrpc": "2.0", "result": null}
Read message 
{"jsonrpc":"2.0","method":"$/cancelRequest","params":{"id":2}}
Read message 
{"jsonrpc":"2.0","id":5,"method":"textDocument/codeAction","params":{"textDocument":{"uri":"file:///Users/donut/work/rls-vscode-weirdness/lib/lib.ml"},"range":{"start":{"line":0,"character":0},"end":{"line":0,"character":0}},"context":{"diagnostics":[{"range":{"start":{"line":0,"character":0},"end":{"line":0,"character":0}},"message":"File \"command line\", line 1:\nError: Unbound module Lib__","severity":1}]}}}
[server] Got a method textDocument/codeAction
[server] processing took 0.0219345092773ms
Sending response {"id": 5, "jsonrpc": "2.0", "result": null}
```