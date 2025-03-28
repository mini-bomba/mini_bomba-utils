# [ic-hotspot](/bin/ic-hotspot)
## a simple script to automatically authenticate to PKP InterCity's hotspots

### Requirements

* bash
* curl
* grep
* sudo & node (for KD hotspots)

### Installation

Install the requirements, if not already met.

Clone the repo & add it to the PATH, or download the file, put it in a directory on the PATH (such as `/usr/local/bin`, or `~/.local/bin`) and mark it executable.

### Usage
Connect to the WiFi hotspot, run the script, hope it works.

The script should work even when using DNS over TLS (which was my main issue with these captive portals)

#### Implemented captive portal types
- IC "`hotspot_pesa`"
- IC "`hotspot_fps`"
- IC "`portal<dot>passengera<dot>com`"
- KD "`hotspot<dot>ente<dot>pl`"
  - note: this hotspot type will execute untrusted js code as the `nobody` user.

#### Automatic login
Try creating a script in /etc/NetworkManager/dispatcher.d/ that calls this utility after connecting to a supported hotspot.
See the `NetworkManager-dispatcher(8)` manpage for more info
