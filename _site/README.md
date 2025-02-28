# zaidamartinez.github.io
Personal website

To run the visualizer:
1. Installed Ruby through [RubyInstaller](https://rubyinstaller.org/downloads/)
2. In a PowerShell terminal outside VSCode:
   1. Install bundler: `gem install bundler`
   2. Install Jekyll: `gem install jekyll`
   3. Install minima theme: `gem install minima`
   4. Test their installations with `ruby -v`, `bundler -v` and `jekyll -v`
3. Then, navigate to the folder location: `cd "B:\OneDrive\MyWebsite\zaidaemtzmo.github.io\"`
4. Run `jekyll serve`
5. Open an Internet navigator and go to [`http://localhost:4000/`](http://localhost:4000/). You will visualize the website there!
6. Once you are happy with the results, then you can commit it and publish it.

Other options:
1. In a PowerShell terminal inside VSCode:
   1. Run: `$env:PATH = [System.Environment]::GetEnvironmentVariable("Path", "Machine") + ";" + [System.Environment]::GetEnvironmentVariable("Path", "User")`
   2. Test that it identifies the paths: `ruby -v`, `bundler -v` and `jekyll -v`
2. Press `Ctrl+Shift+P` and select `Tasks: Configure Task`. If a `tasks.json` file doesn't exist, create one and add:
    ```
    {
        "version": "2.0.0",
        "tasks": [
            {
                "label": "Run Jekyll Server",
                "type": "shell",
                "command": "C:\\Ruby33-x64\\bin\\jekyll.bat",
                "args": ["serve"],
                "options": {
                    "cwd": "B:/OneDrive/MyWebsite/zaidaemtzmo.github.io",
                    "shell": {
                        "executable": "C:\\Windows\\System32\\cmd.exe"
                    }
                },
                "problemMatcher": [],
                "group": {
                    "kind": "build",
                    "isDefault": true
                },
                "detail": "Start Jekyll development server"
            },
            {
                "label": "Run Jekyll Server (Bundle)",
                "type": "shell",
                "command": "C:\\Ruby33-x64\\bin\\bundle.bat",
                "args": ["exec", "jekyll", "serve"],
                "options": {
                    "cwd": "B:/OneDrive/MyWebsite/zaidaemtzmo.github.io",
                    "shell": {
                        "executable": "C:\\Windows\\System32\\cmd.exe"
                    }
                },
                "problemMatcher": [],
                "group": {
                    "kind": "build",
                    "isDefault": false
                },
                "detail": "Run Jekyll server with bundle"
            },
            {
                "label": "Run Jekyll Server (Bundle - Incremental)",
                "type": "shell",
                "command": "C:\\Ruby33-x64\\bin\\bundle.bat",
                "args": ["exec", "jekyll", "serve", "--incremental"],
                "options": {
                    "cwd": "B:/OneDrive/MyWebsite/zaidaemtzmo.github.io",
                    "shell": {
                        "executable": "C:\\Windows\\System32\\cmd.exe"
                    }
                },
                "problemMatcher": [],
                "group": {
                    "kind": "build",
                    "isDefault": false
                },
                "detail": "Run Jekyll server with bundle and incremental builds"
            }
        ]
    }
    ```
    The idea was that then I could press `Ctrl+Shift+P`, select `Tasks: Run Task` and then `Run Jekyll Server` and it would initialize the webpage, but it didn't work.