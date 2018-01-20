# Asset_Util

Asset_Util is incredibly powerful and can automatically rip numerous asset types including images, sounds, and scripts, as well as automatically regenerate CSV files for characters, aitypes, and xmodelaliases through intelligent script analysis!

To automatically run *all* asset ripping, extracting, and regeneration routines, simply run `/bin/scripts/setup.bat`. If you only want to run the routines for a specific asset type, see below. If you do not want to overwrite any existing files, do not include the `-o` argument when running asset_util.

## Rawfiles, Images, Sounds
Note: This may not support *all* rawfiles, but should support the most common rawfile types.
```
asset_util.exe extract-iwd -o --all
asset_util.exe extract-ff -o --all
```

## Aitypes, Characters, XModelAliases
Aitypes, characters, and xmodelaliases are slightly different from other asset types, in that when they are generated through converter, several related assets are created, as well as a CSV file that contains a list of these assets. When the respective aitype, character, or xmodelalias is included in a fastfiles zone_source file, the respective CSV file is included, which in return causes all assets in that CSV file to be included as well. Unfortunately, these CSV files do not exist in the compiled game data - luckily asset_util can intelligently parse the script files for these given asset types and regenerate the CSV files.

To regenerate these files, simply extract all rawfiles (see the steps above), and then run asset_util with the following arguments:
```
asset_util.exe csvgen -o --aitype --character --xmodelalias *
```

## Soundaliases
To rip the soundaliases for all maps in the game simply run the following batch file. Note that this will cause the game to sequentially load every map in the game while asset_util regenerates the soundalias files.
```
/bin/scripts/soundalias.bat
```

To rip the soundaliases for only a specific map, launch asset_util using the following arguments, replacing MAPNAME with the name of the map you want to rip the soundaliases from.
```
asset_util.exe rip --targetMap MAPNAME
```

## Map Entities
To regenerate Radiant compatible map files that contain a list of all entities for each map run the following batch file:
```
/bin/scripts/ents.bat
```