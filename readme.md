# Keylogger

## Description
Want a terrible keylogger? Look no further!

This keylogger runs in the background and copies all the keystrokes a user inputs. After an interval, it then emails these keystrokes to the gmail given. If the user doesn't type anything, the logger knows not to email anything. 

The logger is heavily based on the logger written by [x4nth055](https://github.com/x4nth055). 

I added the ability to feed in an email address and password rather than hardcode it in, the ability to feed in how often you want the script to report back to you, as well as an experimental attempt to report special character key strokes.

This logger is capable of collecting the keystrokes for 'blanked out' passwords in a 'nix terminal

### Prerequisites

This logger has been built on a number of assumptions:
* You've can run sudo / run as root on a linux system
* You have access to Gmail, and have turned on 'less secure app access' in your security settings

You'll need to install the following modules:
```bash
pip3 install keyboard
pip3 install argparse
```
### Installation
```bash
wget https://raw.githubusercontent.com/Purp1eW0lf/Keylogger/main/logger.py
```
### Usage
This logger requires you to feed your gmail email and password. I would create a throwaway account for this. 

You can also optionally feed the script the length of time you want it to wait and collect keystrokes, and send you an email of the keystrokes. The default waiting period is every 60 seconds, should you choose not to input length (the -l flag)

```bash
sudo python3 logger.py -e gmail@Address -p Password -l 120
```

#### Google Security
##### Make sure this option is selected in your Gmail Security
![Google Security](https://github.com/Purp1eW0lf/Keylogger/blob/main/images/Google%20Security.jpg)

#### Help Image
![Help Image](https://github.com/Purp1eW0lf/Keylogger/blob/main/images/HELP.jpg)

#### Usage Image
![Usage image](https://github.com/Purp1eW0lf/Keylogger/blob/main/images/Example%20Use.jpg)

#### Email Report Image
![Email report](https://github.com/Purp1eW0lf/Keylogger/blob/main/images/Logged%20Email.jpg)


## Known Issues
Sometimes the emails don't send at the regular interval, but will come in batch and you'll get a handful at once
* Fix: I'm not clever enough to figure out why yet.

The script tries to tranpose special characters by examining if the user presses the SHIFT key and a corresponding number. This is majorly flawed, however, as it is entirely dependent on the type/brand/langugage of the keyboard. The current script is based on a Macbook keyboard. 
* Fix: If you're able to do some recon on the user's keyboard type, you can change the section in the middle of the script, and reassign the key values for better accuracy. 

### Contact

If you notice a way the script can be improved you're welcome to make requests and raise issues. 
You're also welcome to slide in my Twitter DMs and tell me how shit the logger is.
[@Purp1eW0lf](https://twitter.com/Purp1eW0lf)

#### License
This tool is free to use. Do not use for illegal purposes. Only use for academic purposes, on computers that you have permission to access. 
