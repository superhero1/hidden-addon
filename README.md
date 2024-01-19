# Home Assistant Test Addon

This addon is to test the support of Eltako devices in [HA_enoceanmqtt](https://github.com/mak-gitdev/HA_enoceanmqtt).   


## Installation
1. If you don't have a MQTT broker yet, in Home Assistant go to **Settings → Add-ons → Add-on store** and install the **Mosquitto broker** addon.
1. Go back to the **Add-on store**, click **⋮ → Repositories**, fill in</br>  **`https://github.com/mak-gitdev/hidden-addon`** and click **Add → Close**.
1. Click on the addon and press **Install** and wait until the addon is installed.

## Usage
1. Stop HA_enoceanmqtt addon if you already use it.
2. Copy/paste your HA_enoceanmqtt addon configuration.
3. Add your Eltako devices in your existing device file if any. Get inspired by examples shared in [enoceanmqtt.devices.sample](addon-test-eltako/enoceanmqtt.devices.sample).
4. Have a look at mak-gitdev/hidden-addon#2 to know how to use your Eltako devices.

## Issues
If you have any issue, simply open a new discussion in the [discussion panel](https://github.com/mak-gitdev/hidden-addon/discussions) of this repository.   
⚠️ Please do not use the issue tracker nor the discussion panel of HA_enoceanmqtt. ⚠️
