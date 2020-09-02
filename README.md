# Polybar Weather

## Installation

Execute these commands to install weather.py scripts in the polybar directory.

```bash
git clone https://github.com/petmi627/Polybar-Weather
cd Polybar-Weather
pip3 install requests
cp weather.py ~/.config/polybar/scripts/
```

Install Weather Icons

```bash
mkdir -p weather-icons && cd weather-icons
wget https://github.com/erikflowers/weather-icons/archive/master.zip
unzip master.zip
mkdir -p ~/.fonts
cp weather-icons-master/font/weathericons-regular-webfont.ttf ~/.fonts/
fc-cache -fv ~/.fonts
fc-list | grep weather
```

Polybar configuration

```
fonts-n = Weather Icons:pixelsize=14;3
---
[module/weather]
type = custom/script
label = %output%
exec = python3 -u ~/.config/polybar/scripts/weather.py Diekirch,LU
interval = 600
click-left = firefox https://openweathermap.org/?q=Diekirch,LU
```

