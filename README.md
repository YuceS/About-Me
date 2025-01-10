# Profile [![CircleCI](https://circleci.com/gh/YuceS/About-Me.svg?style=shield)](https://circleci.com/gh/YuceS/About-Me)
Online information about me and my portfolio.

## TODO
* Generate a PDF version of the CV at build stage
* Add a printer friendly link

[firecracker](https://some-natalie.dev/blog/stop-saying-just-use-firecracker/#fn:1)
GITPOD processes
gitpod /workspace/About-Me (master) $ ps -ef
UID          PID    PPID  C STIME TTY          TIME CMD
root           1       0  0 17:07 ?        00:00:00 supervisor init
root          36       1  0 17:07 ?        00:00:01 supervisor run
gitpod        63      36  0 17:07 ?        00:00:00 sh /ide/bin/gitpod-code --log=info --install-builtin-extension gitpod.gitpod-theme --install-builtin-extension github.vscode-pull-request-github --port 23000 --host 0.0.0.0 --without-connection-token --server-data-dir /workspace/.vscode-remote --do-not-sync -
gitpod        72      63  3 17:07 ?        00:00:05 /ide/node /ide/out/server-main.js --log=info --install-builtin-extension gitpod.gitpod-theme --install-builtin-extension github.vscode-pull-request-github --port 23000 --host 0.0.0.0 --without-connection-token --server-data-dir /workspace/.vscode-remote --do-
gitpod       310      72  1 17:07 ?        00:00:03 /ide/node --dns-result-order=ipv4first /ide/out/bootstrap-fork --type=extensionHost --transformURIs --useHostProxy=false
gitpod       321      72  0 17:07 ?        00:00:00 /ide/node /ide/out/bootstrap-fork --type=fileWatcher
gitpod       341      72  0 17:07 ?        00:00:00 /ide/node /ide/out/bootstrap-fork --type=ptyHost --logsPath /workspace/.vscode-remote/data/logs/20250110T170750
gitpod       586     341  0 17:08 pts/1    00:00:00 /bin/bash --init-file /ide/out/vs/workbench/contrib/terminal/common/scripts/shellIntegration-bash.sh
gitpod       881      72  6 17:10 ?        00:00:02 /ide/node --dns-result-order=ipv4first /ide/out/bootstrap-fork --type=extensionHost --transformURIs --useHostProxy=false
gitpod       892      72  0 17:10 ?        00:00:00 /ide/node /ide/out/bootstrap-fork --type=fileWatcher
gitpod      1143     341  0 17:10 pts/3    00:00:00 /bin/bash --init-file /ide/out/vs/workbench/contrib/terminal/common/scripts/shellIntegration-bash.sh
gitpod      1503     586  0 17:10 pts/1    00:00:00 ps -ef




launch.json

{
    "configurations": [
        {
            "name": "Attach to Kubernetes Node",
            "type": "node",
            "request": "attach",
            "smartStep": true,
            "port": 9229,
            "address": "127.0.0.1",
            "localRoot": "${workspaceFolder}/components",
            "remoteRoot": "/app/node_modules/@gitpod",
            "skipFiles": [
                "<node_internals>/**"
            ]
        },
        {
            "name": "Attach to Node",
            "type": "node",
            "request": "attach",
            "smartStep": true,
            "port": 9229,
            "sourceMaps": true,
            "sourceMapPathOverrides": {
                "webpack:///./~/*": "${workspaceFolder}/node_modules/*",
                "webpack://?:*/*": "${workspaceFolder}/*",
                "file:///app/node_modules/*": "${workspaceFolder}/node_modules/*"
            }
        },
        {
            "name": "Attach to Delve",
            "type": "go",
            "request": "attach",
            "port": 32991,
            "mode": "remote"
        },
        {
            "type": "node",
            "request": "launch",
            "name": "gitpod-db-tests",
            "cwd": "${workspaceFolder}/components/gitpod-db",
            "runtimeExecutable": "yarn",
            "runtimeArgs": [
                "db-test"
            ],
            "internalConsoleOptions": "openOnSessionStart",
            "skipFiles": [
                "<node_internals>/**"
            ]
        }
    ]
}