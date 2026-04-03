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
or when a default route VPN is active

#### Implemented captive portal types
- IC "`hotspot_pesa`"
- IC "`hotspot_fps`"
- IC "`portal<dot>passengera<dot>com`"
- KD "`hotspot<dot>ente<dot>pl`"
  - note: this hotspot type will execute untrusted js code as the `nobody` user.
- IC "openNDS"
- ČD

#### Automatic login
Try creating a script in /etc/NetworkManager/dispatcher.d/ that calls this utility after connecting to a supported hotspot.
See the `NetworkManager-dispatcher(8)` manpage for more info

#### Binding to an interface
If the environment variable `MB_IH_INTERFACE` or `DEVICE_IFACE` (latter being set by networkmanager if executed as a dispatcher script) then the script will force curl to send all requests through this interface.
