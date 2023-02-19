# Yandex-DDNS-AsusWrt-Merlin
Custom script for Asuswrt-Merlin router firmware to update DDNS, uses new [Api360](https://yandex.ru/dev/api360/).\
Automatically updates external router IP in A records of a domain. 

## Setup your domain on yandex
https://yandex.ru/support/business/domains/delegate-domain.html

## Get access token for your router
https://yandex.ru/dev/id/doc/dg/oauth/concepts/about.html

## Prepare router
1. Connect usb drive
1. Connect to router via SSH https://github.com/RMerl/asuswrt-merlin.ng/wiki/Entware
1. Run `amtm` command and format the drive to ext4 https://github.com/RMerl/asuswrt-merlin.ng/wiki/AMTM
1. Reboot router
1. Install `optware` via `amtm`
1. Run `opkg install nano jq`

## Set script
1. Copy `ddns-start` file to router path `/jffs/scripts` dir
1. Set `chmod +x` to the file
1. Enable custom ddns script in router's web UI `{protocol}://{host}/Advanced_ASUSDDNS_Content.asp`
1. Check logs that script works fine `{protocol}://{host}/Main_LogStatus_Content.asp`
  > custom_script: Running /jffs/scripts/ddns-start\
  > [DDNS]: {domain} updated successfully.
