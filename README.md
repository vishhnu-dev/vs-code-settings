# vscode settings for Ruby
Rubocop extension for ruby using rvm on Windows WSL through bat file 

# Here you will find:
- [How to setup Rubocop for Visual Studio Code using wsl and rvm](https://github.com/vishhnu-dev/vs-code-settings#how-to-setup-rubocop-for-visual-studio-code-using-wsl-and-rvm)
- [How to includes erb and rb files into emmet.triggerExpansionOnTab](https://github.com/vishhnu-dev/vs-code-settings#how-to-includes-erb-and-rb-files-into-emmettriggerexpansionontab)
- [How to setup wsl terminal on vscode](https://github.com/vishhnu-dev/vs-code-settings#how-to-setup-wsl-terminal-on-vscode)

## How to setup Rubocop for Visual Studio Code using wsl and rvm
  - run:
    ```console
      gem install rubocop
    ```
  - Install Ruby for Visual Studio Code Extension -> [ruby](https://marketplace.visualstudio.com/items?itemName=rebornix.Ruby)
  - Install Rubocop for Visual Studio Code Extension -> [Rubocop](https://marketplace.visualstudio.com/items?itemName=misogi.
  - Create a file bat like:
    ```console
      @echo off
      bash.exe -c "~/.rvm/gems/ruby-2.5.8/wrappers/rubocop %*"
    ```
  - 2.5.8 is an example, rewrite this using your version, ruby -v
  - This will print out on vscode the absolute path to you rubocop wrapper
    - Now we have to tell to vscode to execute this bat file in settings.json
      ```console
        // RUBOCOP
        // Code analyzer for ruby
        // INSTALATION https://docs.rubocop.org/rubocop/1.41/installation.html
        "ruby.rubocop.executePath": "C:/bin/",
        "ruby.format": "rubocop",
        "ruby.rubocop.onSave": true,
        // IDE
        "editor.detectIndentation": false,
        "editor.tabSize": 2,
        "editor.formatOnPaste": true,
        "editor.formatOnSave": true,
        "diffEditor.ignoreTrimWhitespace": false
      ```
    - The "ruby.rubocop.executePath" line tells to vscode where is the bat file.
    - Others Lines are Rubocop conventions
  
## How to includes erb and rb files into emmet.triggerExpansionOnTab
- Just add into your settings.json
```console
  // Emmet https://code.visualstudio.com/docs/editor/emmet
  // ul>li*10>a -> reproduces an list with 10 itens including a link in wicth one of then.
  "emmet.triggerExpansionOnTab": true,
  "emmet.includeLanguages": {
    "erb": "html",
    "ruby": "html"
  },
```
## How to setup wsl terminal on vscode
- Just install the [WSL Extension for vscode](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl)