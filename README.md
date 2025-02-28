# zaidamartinez.github.io
Personal website

To run the visualizer:
1. Installed Ruby through RubyInstaller
2. In a PowerShell terminal outside VSCode:
   1. Install bundler: `gem install bundler`
   2. Install Jekyll: `gem install jekyll`
   3. Install minima theme: `gem install minima`
   4. Test their installations with `ruby -v`, `bundler -v` and `jekyll -v`
3. In a PowerShell terminal inside VSCode:
   1. Run: `$env:PATH = [System.Environment]::GetEnvironmentVariable("Path", "Machine") + ";" + [System.Environment]::GetEnvironmentVariable("Path", "User")`
   2. Test that it identifies the paths: `ruby -v`, `bundler -v` and `jekyll -v`
4. Press `Ctrl+Shift+P` and select `Tasks: Configure Task`. If a `tasks.json` file doesn't exist, create one and add:
    ```
    {
        "version": "2.0.0",
        "tasks": [
            {
                "label": "Run Jekyll Server",
                "type": "shell",
                "command": "bundle exec jekyll serve",
                "problemMatcher": [],
                "group": {
                    "kind": "build",
                    "isDefault": true
                },
                "detail": "Start Jekyll development server"
            },
            {
                "label": "Run Jekyll Server (Incremental)",
                "type": "shell",
                "command": "bundle exec jekyll serve --incremental",
                "problemMatcher": [],
                "group": {
                    "kind": "build",
                    "isDefault": false
                },
                "detail": "Run Jekyll server with incremental builds"
            }
        ]
    }
    ```
5. 