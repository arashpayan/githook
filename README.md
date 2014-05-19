Githook
-------
Go program that receives GitHub Webhooks then executes scripts for repo deployment

Building
--------
To build, make sure you have the Go tools installed then run `go build githook.go`

Running
-------

`githook` takes a single argument, a rules file in json format. For example


    [
        {
            "RepoUrl": "https://github.com/<username>/<reponame>",
            "RepoBranch": "refs/heads/master",
            "DeployScript": "/path/to/deployment/script.sh",
            "DeployScriptArgumets": [ "arg1", "arg2", "arg3" ]
        }
    ]


To execute and keep the program running in the background after you log out:
`./githook -rules=rules_file.json &> output.log &`

License
-------
Copyright 2014 Arash Payan

    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <http://www.gnu.org/licenses/>.
