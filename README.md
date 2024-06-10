# i2s_pi_connction

To enable the I2S interface and configure your I2S MEMS microphone, you'll need to add the necessary lines in the appropriate section of the /boot/firmware/config.txt file. You can add the lines towards the end of the file, after the [all] section to ensure they are applied universally. Here’s what you need to do:


###Open the configuration file for editing:

```console
sudo nano /boot/firmware/config.txt
```

```console
cheetah_demo_mic --access_key ${ACCESS_KEY}
```
