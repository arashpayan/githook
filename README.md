githook
=======

Go program that receives GitHub Webhooks then executes scripts for repo deployment

building
========

To build, make sure you have the Go tools installed then run `go build githook.go`

running
=======

`githook` takes a single argument, a rules file in json format. For example

`
[
  {
    "RepoUrl": "https://github.com/<username>/<reponame>",
    "RepoBranch": "refs/heads/master",
    "DeployScript": "/path/to/deployment/script.sh",
    "DeployScriptArgumets": [ "arg1", "arg2", "arg3" ]
  }
]
`

To execute and keep the program running in the background:
`./githook -rules=rules_file.json &> output.log &`
