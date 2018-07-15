i3blocks
====

Overview
For system monitering in use with i3wm.

## Description
This scrpits displays more colorful, and the output value of color is flexible.

## Demo
not already yet

## Requirement

Package  
`sudo apt-get install -y upower xbacklight lm_sensors easy_install speedtest-cli alsa-utils`  
Kernel  
Enable I2C_CHARDEV and hardware Monitoring support in the kernel

    Device Drivers  --->
        -*- I2C support  --->
	        <*>   I2C device interface
		    <*> Hardware Monitoring support  --->

        Select a driver, e.g.:
	        [*] Intel Core/Core2/Atom temperature sensor (coretemp)
		
## Usage

## Install
    cd ~/.config
    git clone git://github.com/lati-urr/i3blocks.git
    emacs ~/.config/i3/config

~/.config/i3/config

    # Volume
    bindsym F3 exec amixer sset Master 3%+ && pkill -SIGRTMIN+1 i3blocks
    bindsym F2 exec amixer sset Master 3%- && pkill -SIGRTMIN+1 i3blocks
    
    # Backlight
    bindsym F5 exec xbacklight -dec 3 && pkill -SIGRTMIN+2 i3blocks
    bindsym F6 exec xbacklight -inc 3 && pkill -SIGRTMIN+2 i3blocks

    bar {
    status_command i3blocks
    font xft:Ricty 10
    mode dock
    position top
    workspace_buttons yes
    separator_symbol "  "
    strip_workspace_numbers no
    binding_mode_indicator no
    colors {
    background #200020
    statusline #ffffff
    separator #2d2d2d
    focused_workspace  #200020 #ff0000 #ffffff
    active_workspace   #200020 #d64937 #dedede
    inactive_workspace #200020 #090909 #ffffff
    urgent_workspace #333333 #900000 #ffffff
    }
    }
    