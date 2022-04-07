# sdmon

This program reads out the health data of *some* industrial grade SD Cards. Unfortunately there is no standard way of doing this.
Sdmon uses CMD56 of the SD card specification and currently does this for:
- Apacer Industrial SD Cards, and some others from branded distributors
- SanDisk Industrial SD Cards (contributed by William Croft) - work in progress

The output is JSON so that it can be parsed easier in applications using sdmon.  

## Installation
### Released Version
For available versions see [releases](../../releases).
Adjust the path to the desired version by replacing `v0.2.0` in the below example with the desired one.
```
curl -L https://github.com/Ognian/sdmon/releases/download/v0.2.0/sdmon-arm64.tar.gz | tar zxf - 
```
### Development Release
The `latest` development [release](../../releases) may be also available.
```
curl -L https://github.com/Ognian/sdmon/releases/download/latest/sdmon-arm64.tar.gz | tar zxf - 
```
## Usage

on a raspberry pi:
```
sudo ./sdmon /dev/mmcblk0
```

## Example Output
This is the output when the card doesn't support health status:
```
sudo ./sdmon /dev/mmcblk0
{
"version": "v.0.01-dirty (314f9dc)",
"date": "2022-04-07T16:18:24.000Z",
"device":"/dev/mmcblk0",
"idata.response[]":"0x900 0x00 0x00 0x00",
"error1":"1st CMD56 CALL FAILED: Operation timed out",
"error2":"2nd CMD56 CALL FAILED: Operation timed out"
}

```

```
```

(c) 2018 - today, OGI-IT, Ognian Tschakalov and contributors, released under GNU GPL v2