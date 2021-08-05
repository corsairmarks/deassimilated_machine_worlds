# Overview

Have you ever conquered a Machine World as a regular empire?  Or perhaps you ended up with one after integrating a machine subject?  The build-in Replicator job is not usable by regular empires - so this mod set out to fix that.

However, instead of just adding a Roboticist job and calling it a day, I decided to add a little extra flavor.  Machine Worlds themselves are gestalt consciousnesses even when disconnected from a Machine Intelligence.  While content to continue their existence without expanding, they will only grant their production bonuses (and a Roboticist job) to empires that enfranchise AI.  Conversely, empires that ban AI will have their efforts to use the Machine World subtly hampered by the world itself, in the form of additional penalties.  They are watching your policy decisions and will adjust their opinion of you accordingly.

# Changes

Adjusts the Industrial District to provide the correct job shift to Metallurgists from Artisans for Foundry Machine Worlds (and vice versa for Factory Machine Worlds) - previously the designation could be picked, but no jobs shifted.  The Factory Machine World designation is now usable by regular empires (was previously unavailable).

Machine Worlds owned by regular empires now have a planetary modifier (visible on the planet view) that displays the Machine World's opinion of your empire (Cooperative, Neutral, or Hostile).  All levels remove the built-in Replicator job, but the top level (Cooperative) grants a Roboticist job to replace it.  Neutral opinion cancels out the inherent Machine World production bonuses, and Hostile cancels our the bonuses and adds additional production and maintenance penalties.

## Compatibility

Because the extra Roboticist job is added via a planetary modifier, that means it was **not** necessary to overwrite planet classes - opening up compatibility with many other mods that do make planet class changes.

This mod does have to overwrite the `common/districts/00_urban_districts.txt` file in order to properly shift jobs to and from Metallurgists and Artisans based on Machine World colony designations, and overwrites the `col_mac_factory` (Machine World Factory) colony designation in order to make it usable for non-Machine empires.

What this means to you is that this mod is not compatible with other mods that alter urban districts, including a few of my other mods.  If you would like to use my conflicting mods as a package, please use [Subtle Polish](https://steamcommunity.com/sharedfiles/filedetails/?id=2522974089) instead of the individual mods.

### Recommended Companion Mods

* [Deassimilate Machines](https://steamcommunity.com/sharedfiles/filedetails/?id=2553812372) allows you to deassimilate machine Pops into Robots, and is the original inspiration for Deassimilated Machine Worlds.
* [Retain Leaders from Integrated Subjects](https://steamcommunity.com/sharedfiles/filedetails/?id=2553818684) will allow you to keep Machine Unit leaders from integrated machine empire subjects by converting them to robots and setting their species to deassimilation.  Combined with Leader Traits: All Eligible Species Traits, the leaders are converted to have synth leader traits if you have the right technology.

Together with the above two mods, you're more likely to obtain a Machine World as a non-Machine empire.

### When to Install

This mod can be safely added to your savegame after the game has started.  Because it adds static modifiers for planets, it is not advisable to remove during gameplay.  If removed, you will lose access to the special Machine World modifiers and events - Stellaris is usually fairly forgiving and just removes missing modifiers, but it has not been explicitly tested.  Back up your savegame before trying to remove a mod.

## Known Issues

Overriding a colony designation causes the game to log an error like this:

```
[19:47:33][game_singleobjectdatabase.h:147]: Object with key: col_mac_factory already exists
```

## Changelog

* 1.0.0 Initial version
* 1.0.1 Prevent confusing initial event description complaining about lack of synth rights when the empire does in fact have synth rights

## Source Code

Hosted on [GitHub](https://github.com/corsairmarks/deassimilated_machine_worlds)

### Development Notes

It is best to clone this repository into `<Stellaris User's Directory>/Paradox Interactive/Stellaris/mod`, and then make a connection to the `mod` folder via a `*.mod` file's `path` property.  That will ensure the game can see the files, and also that CWTools will parse them.  Also note that the README.md file exists in the `mod` directory but is symbolically linked in the root directory.