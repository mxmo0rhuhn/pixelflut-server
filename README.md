# Pixelflut

Small Ansible role to configure a Pixelflut ([the shoreline server implementation](https://github.com/TobleMiner/shoreline))server on a single Debian 10 based system.

Gives some convenience features like setting a picture behind it.

**Watch out: This setup is not intended for large scale deployments.** If you plan on using pixelflut in large scale deployments ([e.g. at conferences with up to 30 Gbit\s](https://twitter.com/Toble_Miner/status/1211094936122208257)). You should look at the *vnc* feature of shoreline in order to split presentation from the server features.

## Requirements

This assumes a server with a Debian 10 OS and the possibility for the user to log in with permissions for sudo.

## Role Variables

 - `pixelflut_port`: The port for the Pixelflut server. This is the port that clients connect to to play. Default: 1337
 - `pixelflut_user`: The user that is used for running the server. Default: pixelflut
 - `pixelflut_user_pwd`: Random password that is needed to allow auto-login for the user. To create such a password: https://docs.ansible.com/ansible/latest/reference_appendices/faq.html#how-do-i-generate-encrypted-passwords-for-the-user-module
 - `pixelflut_bg_image`: Optional image that is displayed behind the Pixelflut (can be made visible by moving Pixelflut around. Default: No image
 - `pixelflut_width`: The width of the canvas on which the Pixelflut is drawn. This should align with the size of your monitor or beamer.  Default: 1920
 - `pixelflut_x_location`: The x location of the Pixelflut window on the screen. Default: 0 which means that it is on the left side of the screen with no offset. A value higher than 0 moves the location of the window towards the right of the the screen.
 - `pixelflut_height`: The height of the canvas on which the Pixelflut is drawn. This should align with the size of your monitor or beamer and the take the y-location into consideration. Default: 1080
 - `pixelflut_y_location`: The y location of the Pixelflut window on the screen. Default: 0 which means that it is on top of the screen with no offset. A value higher than 0 moves the location of the window down the screen.
 - `pixelflut_description`: A text that can be displayed. Default: "Welcome to Pixelflut"
 - `pixelflut_take_screenshots`: A boolean that controls rather screenshots of the pixelflut shall be taken or not. Default: True
 - `pixelflut_screenshots_folder`: The folder that the screenshots would be placed in (if screenshots are active). Default: 'screenshots' folder in the home directory of the 'pixelflut_user'.
 - `pixelflut_screenshots_delay_seconds`: The interval for taking screenshots (in seconds). Default: 30
 - `pixelflut_minimum_free_memory_mb`: The minimum of free memory on the filesystem that hosts the pixelflut_screenshots_folder before pausing the screenshot creation. Value is in Megabyte. Default 100.

## Example Playbook

This is an example of how to use the role:
```
    - hosts: server
      vars:
        pixelflut_y_location: 150
        pixelflut_height: 650
        pixelflut_bg_image: 36c3.png
      roles:
         - { role: pixelflut }
```

License
-------

MIT
