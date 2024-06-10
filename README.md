# i2s_pi_connction

This works for all models of Raspberry pi even pi 5!.
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
### Save and exit the editor:

### Reboot the Raspberry Pi:

```console
sudo reboot
```

### Install the Advanced Linux Sound Architecture (ALSA) utilities:

```console
sudo apt-get install alsa-utils
```

### After rebooting, verify that the I2S microphone is recognized by listing the audio devices:

```console
arecord -l
```

### If the microphone is correctly listed, record a short audio clip to test it:

IF connected in mono use:

```console
arecord -D plughw:0 -c1 -r 48000 -f S32_LE -t wav -V mono -v file.wav
```

IF connected in stereo use:

```console
arecord -D plughw:0 -c2 -r 48000 -f S32_LE -t wav -V stereo -v file_stereo.wav
```

### Play back the recorded audio to verify it works:

```console
aplay file.wav
```

