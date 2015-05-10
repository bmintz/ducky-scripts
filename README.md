This is my collection of duckyscripts, mostly for Windows (because it's an 
easier target :-P).

#To encode a script
1. Install java.
* Drag-and-drop a script (usually named source.txt) from the "scripts"
	subdirectory on the \encode.bat file.
* If the current \inject.bin file correlates to a different script than was
	previously on the root of the drive, modify \current_script.txt accordingly.

The [composite duck](https://cdn.rawgit.com/midnitesnake/USB-Rubber-Ducky/master/Firmware/Images/c_duck_v2.1.hex) firmware is recommended.
Flash it following the instructions on [midnitesnake's Ducky Wiki](https://github.com/midnitesnake/USB-Rubber-Ducky/wiki/Flashing-ducky).

New scripts should be organized as follows:

```
scripts\
	[OS Name]\
		[version name | "all"]\
			[script name]\
				source.txt			# contains the duckyscript source code
				description.txt			# (optional) human-readable description of this script,
								# including other variants/versions if applicable
				inject.bin			# binary-encoding of source.txt
```

# Copying it to an SD card:
```sh
cp -a ducky-scripts/* /mnt/DUCKY
```
