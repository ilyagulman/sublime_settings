# sublime_settings

## Done macro
marks a line with done and tiestamp
Tools->Developer->New plugin
Save as : mkdone.py
```
import sublime
import datetime
import sublime_plugin

class ExampleCommand(sublime_plugin.TextCommand):
    def run(self, edit):
        timestamp = " [%s]\t" % (datetime.datetime.now().strftime("%H:%M"))
        self.view.insert(edit, self.view.line(self.view.sel()[0]).begin(),  '~V~ ' )
        self.view.insert(edit, self.view.line(self.view.sel()[0]).end(),  timestamp)
        #debug self.view.insert(edit, 0, "Hello")
```

### Key binding:
in preferences->key binsings
user
```
[
	{ "keys": ["f5"], "command": "mkdone"}
]
```

### Debug  
run in the console
```
sublime.log_input(True) sublime.log_commands(True)
```
