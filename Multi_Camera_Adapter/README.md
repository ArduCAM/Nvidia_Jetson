##Jetson Naono Multi Camera Adapter

###Dependency
sudo pip install Jetson.GPIO

###Setting User Permissions
In order to use the Jetson GPIO Library, the correct user permissions/groups must be set first.

Create a new gpio user group. Then add your user to the newly created group.

`sudo groupadd -f -r gpio`  
`sudo usermod -a -G gpio $USER`  
Install custom udev rules by copying the 99-gpio.rules file into the rules.d directory:

sudo cp /opt/nvidia/jetson-gpio/etc/99-gpio.rules /etc/udev/rules.d/
Please note that for the new rule to take place, you may either need to reboot or reload the udev rules by issuing this command:

`sudo udevadm control --reload-rules && sudo udevadm trigger`  
`sudo reboot`  

More Info [Jetson.GPIO - Linux for Tegra](https://pypi.org/project/Jetson.GPIO/#description)


###Run the Demo
sudo python JetsonNanoAdapterTestDemo.py

This demo will capture a image from each camera and save to local folder.