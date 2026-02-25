Vector Presence Monitor - Installer

Simple setup to monitor your phone's network presence and trigger Vector actions automatically.

REQUIREMENTS

- Python 3.6+ must be installed and available in PATH
- Windows PC with Python access (Linux/Mac also supported)
- Download the zip file as well.

QUICK START

IMPORTANT: Before running the installer, you MUST set your phone's MAC address to permanent.
Most modern phones randomize their Wi-Fi MAC address for privacy. The monitor needs a stable MAC.

How to set permanent MAC:
- Android: Go to Wi-Fi settings > Advanced > MAC address randomization > Turn OFF
- iPhone: Settings > Wi-Fi > (Your network) > Disable "Private Wi-Fi Address"

Once set, note your phone's MAC address from your router or run: ipconfig /all on your PC

Download the Vector-Welcome-home.Zip firectly from github then extract its contents inside it is all you need to continue the following steps :)

1. Run the installer:
   install.bat
   
   This will prompt you for:
   - Phone IP address
   - Phone MAC address
   - Vector Bot ID (serial number)
   - Custom message to say

2. Configure:
   Enter your settings when prompted. The installer will save them to config.json.

3. Auto-Start:
   The installer will create a Windows startup shortcut, so the monitor runs automatically when you log in.

MANUAL LAUNCH

Run the monitor manually anytime:
run_monitor.bat

CONFIGURATION

Settings are stored in config.json:
- phone_ip: IP address of your phone
- phone_mac: MAC address of your phone
- bot_id: Vector's serial/ID (like "0jf3i71e")
- message: Custom message Vector will say
- wirepod_ip: Default is localhost (don't change unless needed)
- wait_time: Seconds to wait after phone connects before saying message (5 for testing, 60 for production)
- cooldown: Minimum seconds between triggers (default: 300 = 5 minutes)

HOW IT WORKS

1. Script monitors your phone's IP and MAC address
2. When phone connects to the network, Vector triggers an action:
   - explore mode: Vector will explore around
   - say mode: Vector will say your custom message after a delay
3. Cooldown prevents repeated triggers if your phone bounces on/off the network

TROUBLESHOOTING

- Check config.json to verify your settings
- Run without --allow-drive to simulate without actually moving Vector
- Check wirepod is running on localhost:8080

FILES

- install.bat - Run this to set up everything
- setup_installer.py - The installer script
- config.json - Your configuration (created by installer, don't share)
- vector_presence_monitor.py - The main monitor script
- run_monitor.bat - Launch the monitor anytime
