```
VSCode: Version 1.33.1 (1.33.1)
reason-vscode: 1.5.2
```

When there is any other .ml file in the lib directory, reason-vscode gives the
error in lib.ml:

> File "command line", line 1:
> Error: Unbound module Lib__

If you remove lib/goomba.ml and re-compile, everything is fine.

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
{"jsonrpc":"2.0","method":"textDocument/didOpen","params":{"textDocument":{"uri":"file:///Users/donut/work/rls-vscode-weirdness/bin/main.ml","languageId":"ocaml","version":1,"text":"\nlet () = \n  print_endline \"hi, there\";\n  Lib.metoo ()"}}}
Found a `dune` file at /Users/donut/work/rls-vscode-weirdness/bin
]] Making a new jbuilder package at /Users/donut/work/rls-vscode-weirdness/bin
=== Project root: /Users/donut/work/rls-vscode-weirdness
Detected `esy` dependency manager for local use
=== Build dir:    /Users/donut/work/rls-vscode-weirdness/_esy/default/store/b/ovpsync-d2a69d39
Get ocaml stdlib dirs
Include subdirs? no :/
Got a compiled base /Users/donut/work/rls-vscode-weirdness/_esy/default/store/b/ovpsync-d2a69d39/default/bin/.main.eobjs
Local file: /Users/donut/work/rls-vscode-weirdness/bin/main.ml
Local .cmt file: /Users/donut/work/rls-vscode-weirdness/_esy/default/store/b/ovpsync-d2a69d39/default/bin/.main.eobjs/Main.cmt
Not a library
>> Collecting deps for /Users/donut/.esy/3___________________________________________________________________/i/ocaml-4.7.1004-e5a2754f/lib/ocaml
Depedency dirs /Users/donut/.esy/3___________________________________________________________________/i/ocaml-4.7.1004-e5a2754f/lib/ocaml
>> Build system running: esy
>>> stdout

>>> stderr
info esy 0.5.6 (using package.json)
Affected files: 
Cleaning bsconfig.json
Sending notification {"jsonrpc": "2.0", "method": "textDocument/publishDiagnostics", "params": {"uri": "file:///Users/donut/work/rls-vscode-weirdness/bin/bsconfig.json", "diagnostics": []}}
Running diagnostics for file:///Users/donut/work/rls-vscode-weirdness/bin/main.ml
➡️ running bsc /Users/donut/.esy/3___________________________________________________________________/i/ocaml-4.7.1004-e5a2754f/bin/ocamlopt.opt -c -I '/Users/donut/work/rls-vscode-weirdness/_esy/default/store/b/ovpsync-d2a69d39/default/bin/.main.eobjs' -I '/Users/donut/.esy/3___________________________________________________________________/i/ocaml-4.7.1004-e5a2754f/lib/ocaml' -bin-annot -w @a-4-29-40-41-42-44-45-48-58-59-60-40 -strict-sequence -strict-formats -short-paths -keep-locs -impl /Users/donut/work/rls-vscode-weirdness/_esy/default/store/b/ovpsync-d2a69d39/.lsp/Main.ast with pwd /Users/donut/work/rls-vscode-weirdness/bin
<< Making lastDefinitions with type error for file:///Users/donut/work/rls-vscode-weirdness/bin/main.ml
type error here File "/Users/donut/work/rls-vscode-weirdness/_esy/default/store/b/ovpsync-d2a69d39/.lsp/Main.ast", line 4, characters 2-11:
Error: Unbound module Lib
Sending notification {"jsonrpc": "2.0", "method": "textDocument/publishDiagnostics", "params": {"uri": "file:///Users/donut/work/rls-vscode-weirdness/bin/main.ml", "diagnostics": [{"range": {"start": {"line": 3, "character": 2}, "end": {"line": 3, "character": 11}}, "message": "Error: Unbound module Lib", "severity": 1}]}}
Read message 
{"jsonrpc":"2.0","id":1,"method":"textDocument/documentSymbol","params":{"textDocument":{"uri":"file:///Users/donut/work/rls-vscode-weirdness/bin/main.ml"}}}
[server] Got a method textDocument/documentSymbol
[server] processing took 0.00500679016113ms
Sending response {"id": 1, "jsonrpc": "2.0", "result": []}
Read message 
{"jsonrpc":"2.0","id":2,"method":"textDocument/codeAction","params":{"textDocument":{"uri":"file:///Users/donut/work/rls-vscode-weirdness/bin/main.ml"},"range":{"start":{"line":3,"character":13},"end":{"line":3,"character":13}},"context":{"diagnostics":[]}}}
[server] Got a method textDocument/codeAction
[server] processing took 0.0159740447998ms
Sending response {"id": 2, "jsonrpc": "2.0", "result": null}
Read message 
{"jsonrpc":"2.0","id":3,"method":"textDocument/codeLens","params":{"textDocument":{"uri":"file:///Users/donut/work/rls-vscode-weirdness/bin/main.ml"}}}
[server] Got a method textDocument/codeLens
[server] processing took 0.00691413879395ms
Sending response {"id": 3, "jsonrpc": "2.0", "result": [{"range": {"start": {"line": 0, "character": 0}, "end": {"line": 0, "character": 0}}, "command": {"title": "Dependencies: Stdlib", "command": ""}}]}
Read message 
{"jsonrpc":"2.0","id":4,"method":"textDocument/codeAction","params":{"textDocument":{"uri":"file:///Users/donut/work/rls-vscode-weirdness/bin/main.ml"},"range":{"start":{"line":3,"character":13},"end":{"line":3,"character":13}},"context":{"diagnostics":[]}}}
[server] Got a method textDocument/codeAction
[server] processing took 0.00691413879395ms
Sending response {"id": 4, "jsonrpc": "2.0", "result": null}
Read message 
{"jsonrpc":"2.0","method":"$/cancelRequest","params":{"id":2}}
Read message 
{"jsonrpc":"2.0","method":"$/setTraceNotification","params":{"value":"off"}}
Read message 
{"jsonrpc":"2.0","method":"workspace/didChangeConfiguration","params":{"settings":{"reason_language_server":{"location":"","build_system_override_by_root":{},"refmt":"","lispRefmt":"","format_width":"80","per_value_codelens":false,"dependencies_codelens":true,"opens_codelens":true,"show_module_path_on_hover":true,"reloadOnChange":false,"show_debug_errors":false,"autoRebuild":true}}}}
Read message 
{"jsonrpc":"2.0","method":"$/setTraceNotification","params":{"value":"off"}}
Read message 
{"jsonrpc":"2.0","method":"workspace/didChangeConfiguration","params":{"settings":{"reason_language_server":{"location":"","build_system_override_by_root":{},"refmt":"","lispRefmt":"","format_width":"80","per_value_codelens":false,"dependencies_codelens":true,"opens_codelens":true,"show_module_path_on_hover":true,"reloadOnChange":false,"show_debug_errors":false,"autoRebuild":true}}}}
Read message 
{"jsonrpc":"2.0","method":"textDocument/didOpen","params":{"textDocument":{"uri":"file:///Users/donut/work/rls-vscode-weirdness/lib/lib.ml","languageId":"ocaml","version":1,"text":"\nlet metoo () =\n  print_endline \"Welcome?\""}}}
Found a `dune` file at /Users/donut/work/rls-vscode-weirdness/lib
]] Making a new jbuilder package at /Users/donut/work/rls-vscode-weirdness/lib
=== Project root: /Users/donut/work/rls-vscode-weirdness
Detected `esy` dependency manager for local use
=== Build dir:    /Users/donut/work/rls-vscode-weirdness/_esy/default/store/b/ovpsync-d2a69d39
Get ocaml stdlib dirs
Include subdirs? no :/
Got a compiled base /Users/donut/work/rls-vscode-weirdness/_esy/default/store/b/ovpsync-d2a69d39/default/lib
Local file: /Users/donut/work/rls-vscode-weirdness/lib/goomba.ml
Local .cmt file: /Users/donut/work/rls-vscode-weirdness/_esy/default/store/b/ovpsync-d2a69d39/default/lib/Goomba.cmt
Local file: /Users/donut/work/rls-vscode-weirdness/lib/lib.ml
Local .cmt file: /Users/donut/work/rls-vscode-weirdness/_esy/default/store/b/ovpsync-d2a69d39/default/lib/Lib.cmt
>> Collecting deps for /Users/donut/.esy/3___________________________________________________________________/i/ocaml-4.7.1004-e5a2754f/lib/ocaml
Depedency dirs /Users/donut/.esy/3___________________________________________________________________/i/ocaml-4.7.1004-e5a2754f/lib/ocaml
>> Build system running: esy
>>> stdout

>>> stderr
info esy 0.5.6 (using package.json)
Affected files: 
Cleaning bsconfig.json
Sending notification {"jsonrpc": "2.0", "method": "textDocument/publishDiagnostics", "params": {"uri": "file:///Users/donut/work/rls-vscode-weirdness/lib/bsconfig.json", "diagnostics": []}}
Running diagnostics for file:///Users/donut/work/rls-vscode-weirdness/lib/lib.ml
➡️ running bsc /Users/donut/.esy/3___________________________________________________________________/i/ocaml-4.7.1004-e5a2754f/bin/ocamlopt.opt -c -I '/Users/donut/work/rls-vscode-weirdness/_esy/default/store/b/ovpsync-d2a69d39/default/lib' -I '/Users/donut/.esy/3___________________________________________________________________/i/ocaml-4.7.1004-e5a2754f/lib/ocaml' -bin-annot -open Lib__ -w @a-4-29-40-41-42-44-45-48-58-59-60-40 -strict-sequence -strict-formats -short-paths -keep-locs -impl /Users/donut/work/rls-vscode-weirdness/_esy/default/store/b/ovpsync-d2a69d39/.lsp/Lib.ast with pwd /Users/donut/work/rls-vscode-weirdness/lib
<< Making lastDefinitions with type error for file:///Users/donut/work/rls-vscode-weirdness/lib/lib.ml
type error here File "command line", line 1:
Error: Unbound module Lib__
Sending notification {"jsonrpc": "2.0", "method": "textDocument/publishDiagnostics", "params": {"uri": "file:///Users/donut/work/rls-vscode-weirdness/lib/lib.ml", "diagnostics": [{"range": {"start": {"line": 0, "character": 0}, "end": {"line": 0, "character": 0}}, "message": "File \"command line\", line 1:\nError: Unbound module Lib__", "severity": 1}]}}
Read message 
{"jsonrpc":"2.0","id":5,"method":"textDocument/documentSymbol","params":{"textDocument":{"uri":"file:///Users/donut/work/rls-vscode-weirdness/lib/lib.ml"}}}
[server] Got a method textDocument/documentSymbol
[server] processing took 0.00619888305664ms
Sending response {"id": 5, "jsonrpc": "2.0", "result": []}
Read message 
{"jsonrpc":"2.0","method":"$/setTraceNotification","params":{"value":"off"}}
Read message 
{"jsonrpc":"2.0","method":"workspace/didChangeConfiguration","params":{"settings":{"reason_language_server":{"location":"","build_system_override_by_root":{},"refmt":"","lispRefmt":"","format_width":"80","per_value_codelens":false,"dependencies_codelens":true,"opens_codelens":true,"show_module_path_on_hover":true,"reloadOnChange":false,"show_debug_errors":false,"autoRebuild":true}}}}
Read message 
{"jsonrpc":"2.0","method":"$/setTraceNotification","params":{"value":"off"}}
Read message 
{"jsonrpc":"2.0","method":"workspace/didChangeConfiguration","params":{"settings":{"reason_language_server":{"location":"","build_system_override_by_root":{},"refmt":"","lispRefmt":"","format_width":"80","per_value_codelens":false,"dependencies_codelens":true,"opens_codelens":true,"show_module_path_on_hover":true,"reloadOnChange":false,"show_debug_errors":false,"autoRebuild":true}}}}
Read message 
{"jsonrpc":"2.0","method":"$/setTraceNotification","params":{"value":"off"}}
Read message 
{"jsonrpc":"2.0","method":"workspace/didChangeConfiguration","params":{"settings":{"reason_language_server":{"location":"","build_system_override_by_root":{},"refmt":"","lispRefmt":"","format_width":"80","per_value_codelens":false,"dependencies_codelens":true,"opens_codelens":true,"show_module_path_on_hover":true,"reloadOnChange":false,"show_debug_errors":false,"autoRebuild":true}}}}
Read message 
{"jsonrpc":"2.0","id":6,"method":"textDocument/codeLens","params":{"textDocument":{"uri":"file:///Users/donut/work/rls-vscode-weirdness/lib/lib.ml"}}}
[server] Got a method textDocument/codeLens
[server] processing took 0.00810623168945ms
Sending response {"id": 6, "jsonrpc": "2.0", "result": [{"range": {"start": {"line": 0, "character": 0}, "end": {"line": 0, "character": 0}}, "command": {"title": "Dependencies: ", "command": ""}}]}
Read message 
{"jsonrpc":"2.0","id":7,"method":"textDocument/codeAction","params":{"textDocument":{"uri":"file:///Users/donut/work/rls-vscode-weirdness/lib/lib.ml"},"range":{"start":{"line":2,"character":25},"end":{"line":2,"character":25}},"context":{"diagnostics":[]}}}
[server] Got a method textDocument/codeAction
[server] processing took 0.00691413879395ms
Sending response {"id": 7, "jsonrpc": "2.0", "result": null}
Read message 
{"jsonrpc":"2.0","method":"$/setTraceNotification","params":{"value":"off"}}
Read message 
{"jsonrpc":"2.0","method":"workspace/didChangeConfiguration","params":{"settings":{"reason_language_server":{"location":"","build_system_override_by_root":{},"refmt":"","lispRefmt":"","format_width":"80","per_value_codelens":false,"dependencies_codelens":true,"opens_codelens":true,"show_module_path_on_hover":true,"reloadOnChange":false,"show_debug_errors":false,"autoRebuild":true}}}}
Read message 
{"jsonrpc":"2.0","id":8,"method":"textDocument/hover","params":{"textDocument":{"uri":"file:///Users/donut/work/rls-vscode-weirdness/lib/lib.ml"},"position":{"line":2,"character":13}}}
[server] Got a method textDocument/hover
[server] processing took 0.00596046447754ms
Sending response {"id": 8, "jsonrpc": "2.0", "result": null}
Read message 
{"jsonrpc":"2.0","id":9,"method":"textDocument/documentHighlight","params":{"textDocument":{"uri":"file:///Users/donut/work/rls-vscode-weirdness/lib/lib.ml"},"position":{"line":2,"character":13}}}
[server] Got a method textDocument/documentHighlight
[server] processing took 0.00596046447754ms
Sending response {"id": 9, "jsonrpc": "2.0", "result": null}
Read message 
{"jsonrpc":"2.0","method":"$/cancelRequest","params":{"id":8}}
Read message 
{"jsonrpc":"2.0","id":10,"method":"textDocument/codeAction","params":{"textDocument":{"uri":"file:///Users/donut/work/rls-vscode-weirdness/lib/lib.ml"},"range":{"start":{"line":2,"character":13},"end":{"line":2,"character":13}},"context":{"diagnostics":[]}}}
[server] Got a method textDocument/codeAction
[server] processing took 0.00596046447754ms
Sending response {"id": 10, "jsonrpc": "2.0", "result": null}
Read message 
{"jsonrpc":"2.0","method":"$/cancelRequest","params":{"id":7}}
Read message 
{"jsonrpc":"2.0","id":11,"method":"textDocument/codeAction","params":{"textDocument":{"uri":"file:///Users/donut/work/rls-vscode-weirdness/lib/lib.ml"},"range":{"start":{"line":1,"character":13},"end":{"line":1,"character":13}},"context":{"diagnostics":[]}}}
[server] Got a method textDocument/codeAction
[server] processing took 0.00905990600586ms
Sending response {"id": 11, "jsonrpc": "2.0", "result": null}
Read message 
{"jsonrpc":"2.0","id":12,"method":"textDocument/hover","params":{"textDocument":{"uri":"file:///Users/donut/work/rls-vscode-weirdness/lib/lib.ml"},"position":{"line":0,"character":0}}}
[server] Got a method textDocument/hover
[server] processing took 0.0109672546387ms
Sending response {"id": 12, "jsonrpc": "2.0", "result": null}
Read message 
{"jsonrpc":"2.0","id":13,"method":"textDocument/codeAction","params":{"textDocument":{"uri":"file:///Users/donut/work/rls-vscode-weirdness/lib/lib.ml"},"range":{"start":{"line":2,"character":25},"end":{"line":2,"character":25}},"context":{"diagnostics":[]}}}
[server] Got a method textDocument/codeAction
[server] processing took 0.00786781311035ms
Sending response {"id": 13, "jsonrpc": "2.0", "result": null}
Read message 
{"jsonrpc":"2.0","id":14,"method":"textDocument/codeLens","params":{"textDocument":{"uri":"file:///Users/donut/work/rls-vscode-weirdness/bin/main.ml"}}}
[server] Got a method textDocument/codeLens
[server] processing took 0.014066696167ms
Sending response {"id": 14, "jsonrpc": "2.0", "result": [{"range": {"start": {"line": 0, "character": 0}, "end": {"line": 0, "character": 0}}, "command": {"title": "Dependencies: Stdlib", "command": ""}}]}
Read message 
{"jsonrpc":"2.0","id":15,"method":"textDocument/codeAction","params":{"textDocument":{"uri":"file:///Users/donut/work/rls-vscode-weirdness/bin/main.ml"},"range":{"start":{"line":3,"character":13},"end":{"line":3,"character":13}},"context":{"diagnostics":[]}}}
[server] Got a method textDocument/codeAction
[server] processing took 0.0109672546387ms
Sending response {"id": 15, "jsonrpc": "2.0", "result": null}
Read message 
{"jsonrpc":"2.0","id":16,"method":"textDocument/hover","params":{"textDocument":{"uri":"file:///Users/donut/work/rls-vscode-weirdness/bin/main.ml"},"position":{"line":2,"character":6}}}
[server] Got a method textDocument/hover
[server] processing took 0.0169277191162ms
Getting global Stdlib
FINDING /Users/donut/.esy/3___________________________________________________________________/i/ocaml-4.7.1004-e5a2754f/lib/ocaml/stdlib.cmti src /Users/donut/.esy/3___________________________________________________________________/i/ocaml-4.7.1004-e5a2754f/lib/ocaml/stdlib.cmti
Getting for 1547 in print_endline
Trying for declared Value 1547 in file file:///Users/donut/.esy/3___________________________________________________________________/i/ocaml-4.7.1004-e5a2754f/lib/ocaml/stdlib.cmti
Yes!! got it
Sending response {"id": 16, "jsonrpc": "2.0", "result": {"range": {"start": {"line": 2, "character": 2}, "end": {"line": 2, "character": 15}}, "contents": {"kind": "markdown", "value": "```\nstring => unit\n```\n\n Print a string, followed by a newline character, on\n   standard output and flush standard output. \n\nfile:///Users/donut/.esy/3___________________________________________________________________/i/ocaml-4.7.1004-e5a2754f/lib/ocaml/stdlib.cmti"}}}
Read message 
{"jsonrpc":"2.0","id":17,"method":"textDocument/hover","params":{"textDocument":{"uri":"file:///Users/donut/work/rls-vscode-weirdness/bin/main.ml"},"position":{"line":3,"character":6}}}
[server] Got a method textDocument/hover
[server] processing took 0.014066696167ms
Sending response {"id": 17, "jsonrpc": "2.0", "result": null}
Read message 
{"jsonrpc":"2.0","id":18,"method":"textDocument/codeAction","params":{"textDocument":{"uri":"file:///Users/donut/work/rls-vscode-weirdness/bin/main.ml"},"range":{"start":{"line":1,"character":8},"end":{"line":1,"character":8}},"context":{"diagnostics":[]}}}
[server] Got a method textDocument/codeAction
[server] processing took 0.0100135803223ms
Sending response {"id": 18, "jsonrpc": "2.0", "result": null}
Read message 
{"jsonrpc":"2.0","method":"textDocument/didOpen","params":{"textDocument":{"uri":"file:///Users/donut/work/rls-vscode-weirdness/lib/goomba.ml","languageId":"ocaml","version":1,"text":"let notme () = \n  print_endline \"poop\"\n"}}}
Read message 
{"jsonrpc":"2.0","id":19,"method":"textDocument/codeAction","params":{"textDocument":{"uri":"file:///Users/donut/work/rls-vscode-weirdness/lib/goomba.ml"},"range":{"start":{"line":0,"character":0},"end":{"line":0,"character":0}},"context":{"diagnostics":[]}}}
[server] Got a method textDocument/codeAction
[server] processing took 0.00715255737305ms
➡️ running bsc /Users/donut/.esy/3___________________________________________________________________/i/ocaml-4.7.1004-e5a2754f/bin/ocamlopt.opt -c -I '/Users/donut/work/rls-vscode-weirdness/_esy/default/store/b/ovpsync-d2a69d39/default/lib' -I '/Users/donut/.esy/3___________________________________________________________________/i/ocaml-4.7.1004-e5a2754f/lib/ocaml' -bin-annot -open Lib__ -w @a-4-29-40-41-42-44-45-48-58-59-60-40 -strict-sequence -strict-formats -short-paths -keep-locs -impl /Users/donut/work/rls-vscode-weirdness/_esy/default/store/b/ovpsync-d2a69d39/.lsp/Goomba.ast with pwd /Users/donut/work/rls-vscode-weirdness/lib
<< Making lastDefinitions with type error for file:///Users/donut/work/rls-vscode-weirdness/lib/goomba.ml
Sending response {"id": 19, "jsonrpc": "2.0", "result": null}
Read message 
{"jsonrpc":"2.0","id":20,"method":"textDocument/documentSymbol","params":{"textDocument":{"uri":"file:///Users/donut/work/rls-vscode-weirdness/lib/goomba.ml"}}}
[server] Got a method textDocument/documentSymbol
[server] processing took 0.00715255737305ms
Sending response {"id": 20, "jsonrpc": "2.0", "result": []}
Read message 
{"jsonrpc":"2.0","id":21,"method":"textDocument/codeLens","params":{"textDocument":{"uri":"file:///Users/donut/work/rls-vscode-weirdness/lib/goomba.ml"}}}
[server] Got a method textDocument/codeLens
[server] processing took 0.0112056732178ms
Sending response {"id": 21, "jsonrpc": "2.0", "result": [{"range": {"start": {"line": 0, "character": 0}, "end": {"line": 0, "character": 0}}, "command": {"title": "Dependencies: ", "command": ""}}]}
Running diagnostics for file:///Users/donut/work/rls-vscode-weirdness/lib/goomba.ml
type error here File "command line", line 1:
Error: Unbound module Lib__
Sending notification {"jsonrpc": "2.0", "method": "textDocument/publishDiagnostics", "params": {"uri": "file:///Users/donut/work/rls-vscode-weirdness/lib/goomba.ml", "diagnostics": [{"range": {"start": {"line": 0, "character": 0}, "end": {"line": 0, "character": 0}}, "message": "File \"command line\", line 1:\nError: Unbound module Lib__", "severity": 1}]}}
Read message 
{"jsonrpc":"2.0","id":22,"method":"textDocument/codeAction","params":{"textDocument":{"uri":"file:///Users/donut/work/rls-vscode-weirdness/lib/goomba.ml"},"range":{"start":{"line":0,"character":0},"end":{"line":0,"character":0}},"context":{"diagnostics":[{"range":{"start":{"line":0,"character":0},"end":{"line":0,"character":0}},"message":"File \"command line\", line 1:\nError: Unbound module Lib__","severity":1}]}}}
[server] Got a method textDocument/codeAction
[server] processing took 0.113964080811ms
Sending response {"id": 22, "jsonrpc": "2.0", "result": null}
Read message 
{"jsonrpc":"2.0","id":23,"method":"textDocument/hover","params":{"textDocument":{"uri":"file:///Users/donut/work/rls-vscode-weirdness/lib/goomba.ml"},"position":{"line":0,"character":12}}}
[server] Got a method textDocument/hover
[server] processing took 0.0131130218506ms
Sending response {"id": 23, "jsonrpc": "2.0", "result": null}
Read message 
{"jsonrpc":"2.0","id":24,"method":"textDocument/hover","params":{"textDocument":{"uri":"file:///Users/donut/work/rls-vscode-weirdness/lib/goomba.ml"},"position":{"line":0,"character":1}}}
[server] Got a method textDocument/hover
[server] processing took 0.00905990600586ms
Sending response {"id": 24, "jsonrpc": "2.0", "result": null}
Read message 
{"jsonrpc":"2.0","id":25,"method":"textDocument/hover","params":{"textDocument":{"uri":"file:///Users/donut/work/rls-vscode-weirdness/lib/goomba.ml"},"position":{"line":0,"character":2}}}
[server] Got a method textDocument/hover
[server] processing took 0.0100135803223ms
Sending response {"id": 25, "jsonrpc": "2.0", "result": null}
Read message 
{"jsonrpc":"2.0","id":26,"method":"textDocument/codeAction","params":{"textDocument":{"uri":"file:///Users/donut/work/rls-vscode-weirdness/lib/lib.ml"},"range":{"start":{"line":0,"character":0},"end":{"line":0,"character":0}},"context":{"diagnostics":[{"range":{"start":{"line":0,"character":0},"end":{"line":0,"character":0}},"message":"File \"command line\", line 1:\nError: Unbound module Lib__","severity":1}]}}}
[server] Got a method textDocument/codeAction
[server] processing took 0.0200271606445ms
Sending response {"id": 26, "jsonrpc": "2.0", "result": null}
Read message 
{"jsonrpc":"2.0","method":"textDocument/didClose","params":{"textDocument":{"uri":"file:///Users/donut/work/rls-vscode-weirdness/lib/goomba.ml"}}}

```