# Whatsapp KDE

![banner](https://github.com/user-attachments/assets/64c8384c-fbce-4516-b22d-906222cdfa3f)

Simple bash script which kdocker to emulate whatsappapp application, not originally available on linux. <br />


## Requirements
    sudo apt install kdocker
    sudo apt install chromium

## Usage
The script must be added as a startup script from the KDE settings. <br />
Don't close the window, rather suspend it, otherwise kdocker will have to restart. <br />
To have the icon in the system tray, place it in your home folder. <br />

### Script 

```
#!/bin/bash

#############################################################################################################################################################################
#███████ ██    ██ ███    ██  ██████ ████████ ██  ██████  ███    ██ ███████
#██      ██    ██ ████   ██ ██         ██    ██ ██    ██ ████   ██ ██
#█████   ██    ██ ██ ██  ██ ██         ██    ██ ██    ██ ██ ██  ██ ███████
#██      ██    ██ ██  ██ ██ ██         ██    ██ ██    ██ ██  ██ ██      ██
#██       ██████  ██   ████  ██████    ██    ██  ██████  ██   ████ ███████
#############################################################################################################################################################################
HELP() # SHOW HELP MESSAGE
{
    echo "This is a program to start a Whatsapp web app"
    echo ""
    echo "Options:"
    echo "-h --help            Show this help message"
    echo ""
    echo "-w --whatsapp        Launch whatsapp web app"
    echo ""
}

WHATSAPP()
{
    kdocker -i /home/$(whoami)/WhatsApp.png -l chromium --app=https://web.whatsapp.com/
}
#############################################################################################################################################################################
#███    ███  █████  ██ ███    ██
#████  ████ ██   ██ ██ ████   ██
#██ ████ ██ ███████ ██ ██ ██  ██
#██  ██  ██ ██   ██ ██ ██  ██ ██
#██      ██ ██   ██ ██ ██   ████
#############################################################################################################################################################################
if [ ! -z "$1" ] && [ -z "$2" ];
then
    case $1 in

    -h|--help)
        HELP
        ;;

    -w|--whatsapp)
        WHATSAPP
        ;;

    *)
        echo "Use -h or --help to get the list of valid options and know what the program does"
        ;;
    esac

elif [ -z "$1" ]
then
    echo "Use -h or --help to get the list of valid options and know what the program does"
fi
#############################################################################################################################################################################
```
