# Gnome Top Bar Custom Menu Extension
Custom menu for Gnome Top Bar with your favorite program shortcuts, commands and scripts.

![another Preview](widget.png)


### Usage:
- Edit `.entries.json` to match your needs
- Copy `.entries.json` file to `$HOME/`  

If you edit `.entries.json` while running gnome please ensure to reload Gnome Session (Alt+F2, "r")  
Tested on Gnome v42-44.
The guide below describes available options. In the `examples` directory you can see some tests you can
pick for your setup.


---

## Guide
Here are some examples you can use with this extension:
### **- Launcher**
Create a new entry and put it in the menu
```json
    {
      "type": "launcher",
      "title": "Item Name on Menu",
      "command": "/your/command/to/execute --with-parameters"
    },
```

### **- Separator**
Place a menu separator _(\<hr>)_
```json
    {
      "type": "separator"
    },
```

### **- SubMenu**
Create a submenu inside current menu, items inside the submenu are placed inside `entries`
and they can be of any type (launcher, separator, submenu, ...)
```json
    {
        "type": "submenu",
        "title": "Menu Name",
        "entries": [
            //... Place your entries here ...//
        ]
    },
```

### **- Toggler**
Create a toggle item on menu, it has a detector and ON|OFF commands.
Command detector can be _activated|deactivated_ by a **0** _(success)_ return error level
and later detected with a plain JavaScript eval.
```json
    {
      "type": "toggler",
      "title":       "Widget Title",
      "command_on":  "/command/when/turned/on",
      "command_off": "/command/when/turned/off",
      "detector":    "/command/detector > /dev/null && echo yes"
    },
```
