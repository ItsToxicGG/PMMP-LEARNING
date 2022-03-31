# Branches
12 branches will be done in this github
telling you alot about pocketmine plugins
(including adding scoreboards, bossbars, forms and invmenu)
so be ready for all of this!
# INTRODUCTION (what is a pocketmine plugin)
A plugin is an external module which can be added to your server to add custom features, change default behaviours and more. PocketMine-MP supports plugins to customize and/or modify PocketMine-MP servers for better experience and customization. Plugins allows server owners to achieve certain tasks or behaviors in their servers that are not officially implemented in PocketMine-MP. There are many interesting and useful plugins that already exists, such as world editing, automatic restarts, and economy system.
# Plugin.yml
- Step 1: Create a new file named "plugin.yml"
Now with the plugin.yml:
- name: This is your plugins name
```yml
name: ExamplePlugin
```
- main: This is where you declare the path to the main file in the src folder
```yml
main: YourPluginName\YourName\Main
```
- version: This is your plugins current version (you may use custom tags, example: 1.0-dev or anything else)
```yml
version: 1.0
```
- api: This is where you declare your PocketMine-MP API version(s) which is compatible with your plugin.
It should contain the minimum API minor and patch version for every major API version supported by the
```yml
api: [4.0.0]
```
- mcpe-protocol: This is the minecraft version/protocol supported for the plugin to work (it would get an error if a certain protocol is not supported!)
```yml
mcpe-protocol:
- 486
- 471
- 465
```
- author: the owner of the plugin, if it is you, you may use your name/github name but you can let it be anything you want
```yml
author: Yourname
```
- description: the description of your plugin
```yml
description: This plugin allows you to do that or whatever
```
- website: the website of your plugin (this is recommond to be github)
```yml
website: https://github.com/YourGithub/YourPluginName
```
---------
# Commands and Permissions in the plugin.yml:
- Commands: If your plugin uses commands you need to register the commands here.
```yml
commands:
  example:
    description: Example command
    usage: "/example"
    permission: exampleplugin.command.example
```
- Permissions: If you registered commands (either in plugin.yml or code), you need to declare the permission usage.
```yml
permissions:
  yourpluginname.command.example:
    description: "Allows the user to run the example command"
    default: true
```
# Other infomation with commands and permissions
- There are 4 possible values for the default key:
- True - Everybody may use the command
- op - only players that are op may use the command
- notop - only players that are not op may use the command
- false - no players (including op) can use this command only the console
-----------
# lets start with your source now
In plugin.yml we added a path main. Now depending on the path we added for this tutorial, we will first create a folder called YourPluginName, in this folder we will create another folder called YourName and in this folder we will create a file called Main with the extension .php and it will look like this Main.php

- Lets start with the main.php or whatever you called it in plugin yml

- Namespace: Here you would add the sub-folders of the src dictionary. Based off main path in plugin.yml.
```php
<?php

namespace YourPluginName\YourName;
```
- Use statement: In a new line you will now add a use statement.
```php
use pocketmine\plugin\PluginBase;
// If you made another file like MN.php you sould use to find the file like:
use YourPluginName\YourName\MN;
```
- Class: We will now add the class. In the class we will be able to enable your plugin. But to enable your plugin you need to extend your class
```php
class Main extends PluginBase{
// you may also use:
class Main extends PluginBase implements Listener{ // dont worry about this we will learn it soon in this course
```
- Function: In the class we will add a function to enable your plugin and to do so we will be using the onEnable() function:
```php
class Main extends PluginBase { 

    public function onEnable() : void{  
        $this->getLogger()->info("Plugin has been Enabled");
    }

}
```
- Second Part of Functions
```php
// May use onLoad() and onDisable like this:
class Main extends PluginBase{

    public function onEnable() : void{  
        $this->getLogger()->info("Plugin has been Enabled");
    }
    
    public function onLoad(): void{
        $this->getLogger()->info("Plugin is currently loading...");
    }
    
    public function onDisable(): void{
        $this->getLogger()->info("Plugin has Disabled");
    }

}
```
- At the end of your main.php it would look like this:
```php
<?php

namespace YourPluginName\YourName;

use pocketmine\plugin\PluginBase{

class Main extends PluginBase{

    public function onEnable() : void{  
        $this->getLogger()->info("Plugin has been Enabled");
    }
    
    public function onLoad(): void{
        $this->getLogger()->info("Plugin is currently loading...");
    }
    
    public function onDisable(): void{
        $this->getLogger()->info("Plugin has Disabled");
    }

}
```
----------
Thats the course for lesson-1.
lesson-2 will learn you about commands!
