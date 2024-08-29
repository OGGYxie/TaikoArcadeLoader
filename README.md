# TaikoArcadeLoader

This is a loader for Taiko no Tatsujin Nijiiro ver.

## Setup

Copy the extracted contents of dist.zip to the same directory as Taiko.exe

### config.toml

```toml
[amauth]
# connection server
server = "127.0.0.1"
# connection port
port = "54430"
# dongle serial
chassis_id = "284111080000"
# shop name
shop_id = "TAIKO ARCADE LOADER"
# game version
game_ver = "00.00"
# country code
country_code = "JPN"

[patches]
# patch version
# auto: hash detection (you need to use the original exe)
# JPN00: JPN 00.18
# JPN08: JPN 08.18
# JPN39: JPN 39.06
# CHN00: CHN 00.32 (based on JPN 32.09)
version = "auto"
# window resolution
res = { x = 1920, y = 1080 }
# window mode
windowed = false
# vertical sync
vsync = false
# unlock all songs
unlock_songs = true

  [patches.chn00]
  # sync test mode language to attract etc
  fix_language = false
  # show demo movie
  demo_movie = true
  # enable one piece collab mode
  mode_collabo025 = false
  # enable ai soshina mode
  mode_collabo026 = false

[audio]
# wasapi shared mode
# allows you to have multiple audio sources at once at a cost of having higher latency
wasapi_shared = true
# use asio
asio = false
# asio driver name
# to find it, open up regedit then navigate to HKEY_LOCAL_MACHINE\SOFTWARE\ASIO
# the name is case sensitive !
asio_driver = ""

[card_reader]
# enable card reader emulation
enabled = true

[qr]
# enable qr emulation
enabled = true
# qr image path
image_path = ""

  # qr data used for other events (ex. gaiden, custom folder)
  [qr.data]
  # qr serial
  serial = ""
  # qr type
  # 0: default (serial only)
  # 5: custom folder
  type = 0
  # song noes used for custom folder
  song_no = []

[drum]
# input interval (if using taiko drum controller, should be set to 0)
wait_period = 4

[controller]
# use analog input
analog_input = false

[keyboard]
# auto change to english ime mode
auto_ime = false
# use jp layout scan code (if using jp layout keyboard, must be set to true)
jp_layout = false

[layeredfs]
# replace assets from the game using a layered file system.
# For example if you want to edit the wordlist, add your edited version like so : 
# DumpFolder\Data_mods\x64\datatable\wordlist.bin
enabled = false
# AES encryption keys needed to dynamically encrypt datatable files and fumens
# keys need to be provided in an hexlified form. A missing or incorrect key will crash the game !
# keys are not needed if you provide already encrypted files
datatable_key = ""
fumen_key = ""
```

