# Spawnable Item Pack
Spawnable Item Pack (SIP) is an interface mod that allows you to spawn any item in the game for free, in quantities up to 9999.

## Table of Contents
- [Installation](#installation)
- [Usage](#usage)
- [Features](#features)
- [Adding Items](#adding-items)
- [Planned](#planned)
- [Potential Issues](#potential-issues)
- [Fatal Exception](#fatal-exception)
- [Contributing](#contributing)

## Installation
* [Download](https://github.com/Silverfeelin/SpawnableItemPack/releases) the release for the current version of Starbound.
* Place the `SpawnableItemPack.pak` file in your mods folder (eg. `D:\Steam\steamapps\common\Starbound\mods\`). Overwrite the existing file if necessary.
* Optionally, place the `ManipulatedUI.pak` in the same mods folder. This step is necessary if you don't have this mod yet (or your version is outdated).
 * This file is included in the zipped release.

## Usage
##### Opening the interface
* Open the matter manipulator upgrade panel.
* Select 'Open Spawnable Item Pack' from the available options.

Don't worry, the bundled [Manipulated UI][mui] mod ensures you still have access to the original functionality of the upgrade panel! This menu is used for the mod as it's multiplayer-friendly and can be accessed anywhere.

![Open MMU](https://raw.githubusercontent.com/Silverfeelin/SpawnableItemPack/master/readme/openInterface.png "Open the matter manipulator upgrade panel")

##### Using the interface
After opening the interface, you will be presented with a list of items. Note that the interface may take a second or two to load, as the item lists are being populated when you open the interface.

Also note that not every preview image may appear as expected. The preview images for a large number of animated objects and items will show all frames rather than one image. Finding a fix and applying it is planned.

The functionality of the interface is shown in the below image.  
You can only select one category at once. Deselecting the current category is possible.
![Interface](https://raw.githubusercontent.com/Silverfeelin/SpawnableItemPack/master/readme/sip.png "Interface")

## Features
* View item information by selecting an item.
* Spawn any item in any quantity.
* Filter items by categories.
* Filter items by item identifiers or names.
* Change settings such as the level of generated weapons in the advanced settings menu.
 * You can open this menu by selecting the cog in the top right corner of the interface.

## Adding items
There's a lot of custom items out there, and no easy way for us to fetch all items in-game automatically! This repository comes with a project that allows Windows users to easily generate a JSON patch for items found in an asset folder. This allows us to create a patch file that will add these items to the Wardrobe.

To use this application, you'll want to download the contents of /SpawnableItemFetcher/build/ and put them somewhere on your computer. All files in the directory are necessary to run the application!

#### Usage
* Open `create_patch.bat` in a text editor.
* Set the first path to an asset path. The assets you want to scan should be unpacked first.
 * EG. `D:\Steam\steamapps\common\Starbound\mods\MyMod`
* Set the second path to the output file. Make sure all directories leading up to the file exist!
* EG. `D:\Steam\steamapps\common\Starbound\mods\MyMod\sipCustomItems.json.patch`
* Save and run the batch file.
* If the application asks you to overwrite the file as it already exists, make your selection.

Patch files can easily be used to add items without modifying the SpawnableItemPack mod. For this you'll want to include the SpawnableItemPack mod in your `.metadata` file. This allows the mod to function fine without the SpawnableItemPack mod, but if the SpawnableItemPack mod is present the patch will be applied automatically since it ensures the SpawnableItemPack mod is loaded first.
```json
  "includes" : [
    "SpawnableItemPack"
  ]
```
You'll want to name and place the patch file at the following location:
`../mods/<modName>/sipCustomItems.json.patch`

## Planned
* Fixing preview images. This includes icons for random weapons, and single-frame previews.
* Custom categories, for items from mods.

## Potential Issues
* Game updates that remove items may cause issues, as the mod uses it's own item dump to populate lists.
* Game updates that add items requires an update to the item dump to show in SIP.
* Mixing Steam Workshop and GitHub releases may cause load order issues.
 * If you install Manipulated UI in the Workshop and Spawnable Item Pack here, it will cause a fatal exception. Hopefully Chucklefish will fix this, but the solution is to install Spawnable Item Pack through the Workshop *or* download and install Manipulated UI from GitHub.
 * Installing Manipulated UI from GitHub **and** the Steam Workshop doesn't seem to hurt.

## Fatal Exception
If you're greeted with a fatal exception after installing the mod, this most likely means you did not install the Manipulated UI dependency. Please read the Installation steps carefully.
The Manipulated UI dependency can be downloaded from [the official repository](https://github.com/Silverfeelin/Starbound-ManipulatedUI/releases), but is also bundled with [each release](https://github.com/Silverfeelin/SpawnableItemPack/releases).

## Contributing
If you have any suggestions or feedback that might help improve this mod, please do post them [on the discussion page](http://community.playstarbound.com/resources/spawnable-item-pack-spawn-all-items-for-free.515/)!
You can also create pull requests and contribute directly to the mod!

[mui]:(https://github.com/Silverfeelin/Starbound-ManipulatedUI)
[muiRelease]:(https://github.com/Silverfeelin/Starbound-ManipulatedUI/releases)
