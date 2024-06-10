# i2s_pi_connction

To enable the I2S interface and configure your I2S MEMS microphone, you'll need to add the necessary lines in the appropriate section of the /boot/firmware/config.txt file. You can add the lines towards the end of the file, after the **[all]** section to ensure they are applied universally. Here’s what you need to do:


### Open the configuration file for editing:

```console
sudo nano /boot/firmware/config.txt
```
### Add the following lines to enable I2S and configure the microphone:

```console
# Enable I2S interface
dtparam=i2s=on

# I2S mmap overlay
dtoverlay=i2s-mmap

# ADAU7002 simple overlay for MEMS microphone
dtoverlay=adau7002-simple
```
