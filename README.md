# Vscode how to for Ruby
Rubocop extension for ruby using rvm on Windows WSL through bat file 

## Here you will find:
- [How to setup Rubocop for Visual Studio Code using wsl and rvm](https://github.com/vishhnu-dev/vs-code-settings#how-to-setup-rubocop-for-visual-studio-code-using-wsl-and-rvm)
- [How to includes erb files into emmet.triggerExpansionOnTab](https://github.com/vishhnu-dev/vs-code-settings#how-to-includes-erb-files-into-emmettriggerexpansionontab)

### How to Setup Rubocop for Visual Studio Code using WSL and RVM
  Install rubocop gem
  ```console
    gem install rubocop
  ```
  Install Ruby for Visual Studio-> [Ruby ext](https://marketplace.visualstudio.com/items?itemName=rebornix.Ruby)
  
  Install Rubocop for Visual Studio-> [Rubocop ext](https://marketplace.visualstudio.com/items?itemName=misogi.ruby-rubocop)

  Create a bat file named rubocop under 'C:/bin' containing the code below
  * newfile->put the code->save

  ```console
    @echo off
    bash.exe -c "~/.rvm/gems/ruby-2.5.8/wrappers/rubocop %*"
  ```

  * 2.5.8 is an example, rewrite this using your version, ruby -v

  Tell to vscode settings.json where is the current path to the created bat file
  ```console
    {
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
      "editor.formatOnSave": false,
      "diffEditor.ignoreTrimWhitespace": false
    }
  ```
  The "ruby.rubocop.executePath" line tells to vscode where the bat file is.
  
### How to includes erb files into emmet.triggerExpansionOnTab
- Just add into your settings.json
```console
  {
    "emmet.triggerExpansionOnTab": true,
    "emmet.includeLanguages": {
      "erb": "html"
    }
  }
```
