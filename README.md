## Repository Information

- Patched MRA files for encrypted and decrypted titles on [**jotego's**](https://github.com/jotego/) verilog implementation of Capcom Play System hardware. 


## What Are These For?

- These patches utilize encrypted roms from [**mame 0.229 or higher**](https://www.mamedev.org). The patched MRA files do not require additional roms in `games/mame` or  `games/hbmame` and patch the rom on the fly.

- Patches include unlocked characters, modes, enchancements, trainers, or other features available in encrypted and decrypted roms. These features may have been previously available by inputting codes or not present prior to the patched data.

- Readme files for each MRA available cite the author. If none is notated, then the patch has sourced from me or hbmame.

## How Do I Get Them?

- These patched mra files are available with the popular [**update_all.sh**](https://github.com/theypsilon/Update_All_MiSTer) updater script.  Enable Arcade_Offset in the downloader to retrieve them.

## Patched MRA Format

This is the provided layout used for jtcps2. Patches are applied to the loaded rom from `rom index="0"`.  For roms that use soft dips and store settings in the eeprom (nvram file). Hex is taken from soft dip settings and applied to `rom index="02"`. 

Usage of  rom index's vary from core and are dependent on the author.  These are generated from a tool chain utilized in jtframe, they do not mirror the example shown on [**MiSTer-devel/Main_MiSTer #MRA Format**](https://github.com/MiSTer-devel/Main_MiSTer/wiki/Arcade-Roms-and-MRA-files#mra-format).

<details>
        <summary><b>Patched MRA Template</b></summary>
<p>

```xml
        <misterromdescription>
            <about author=/>
            <name></name>
            <setname></setname>
            <rbf></rbf>
            <mameversion></mameversion>
            <year></year>
            <manufacturer></manufacturer>
            <players></players>
            <joystick></joystick>
            <rotation></rotation>
            <region></region>
            <platform></platform>
            <category></category>
            <catver></catver>
            <mraauthor></mraauthor>
            <rom index="0" zip="rom1.zip|rom2.zip" type="merged" md5="None" address="0x30000000">
                <part>
                Example encryption / configuration
                </part>
                <!-- example rom - starts at 0x0 -->
                <part name="example.00" crc="12345678"/>
                <!-- example rom - starts at 0x14 -->
                <part name="example.01" crc="91011121"/>
                <!-- Total 0x000000 bytes - 00000 kBytes -->
                <patch 0x0>"hex information"</patch>
            </rom>
            <rom index="1">
                <part>00=horizontal / 01=vertical / 02= 4-Way Joystick</part>
            </rom>
            <rom index="2">
                <part>"soft dip information"</part>
            </rom>
            <nvram index="2" size="128"/>
            <buttons names="B1,B2,B3,B4,B5,B6,Start,Coin,Core Credits" default="Y,X,B,A,L,R,Select,Start,-" count="6"/>
        </misterromdescription>
```

</p>
</details>
