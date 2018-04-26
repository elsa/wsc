# wsc

A simplistic tool for sending and receiving websocket messages from a command line.
Mainly useful to test websocket servers.

This version has been adapted to work with ELSA speech assessment API.

Getting started:
```
$ go get github.com/elsa/wsc
$ wsc -o http://websocket.org -H "Sample-Header-1: foo" -H "Sample-Header-2: bar" -u ws://echo.websocket.org
2016/03/08 22:51:51 connecting to ws://echo.websocket.org...
2016/03/08 22:51:52 ready, exit with CTRL+C.
foo 
>> foo
<< foo
^C
exiting
```

Example for ELSA API:
```
$ go get -u github.com/elsa/wsc
$ wsc -o http://<elsa_url> -u ws://<elsa_url>/api/v2/connect -H "Authorization: ELSA <your _key>"
{"type": "ELSA:start_stream", "data": { "stream_info": { "sentence": "I’m so nervous it hurts"}}}
send_file("<path_to_file>/example_love.wav")
{"type": "ELSA:end_stream"}	
```