# squeezelite

## Build

### Debian

```
apt install libasound2-dev libflac-dev libmad0-dev libvorbis-dev libfaad-dev libmpg123-dev
```

```
make
```

### macOS

```
brew install faad2 flac libogg libvorbis mad mpg123 portaudio
```

```
make -f Makefile.osx
```

## Usage

```
Squeezelite v1.8, Copyright 2012-2015 Adrian Smith. See -t for license terms
Usage: squeezelite [options]
  -s <server>[:<port>]	Connect to specified server, otherwise uses autodiscovery to find server
  -o <output device>	Specify output device, default "default", - = output to stdout
  -l 			List output devices
  -a <b>:<p>:<f>:<m>	Specify ALSA params to open output device, b = buffer time in ms or size in bytes, p = period count or size in bytes, f sample format (16|24|24_3|32), m = use mmap (0|1)
  -a <f>		Specify sample format (16|24|32) of output file when using -o - to output samples to stdout (interleaved little endian only)
  -b <stream>:<output>	Specify internal Stream and Output buffer sizes in Kbytes
  -c <codec1>,<codec2>	Restrict codecs to those specified, otherwise load all available codecs; known codecs: flac,pcm,mp3,ogg,aac (mad,mpg for specific mp3 codec)
  -C <timeout>		Close output device when idle after timeout seconds, default is to keep it open while player is 'on'
  -d <log>=<level>	Set logging level, logs: all|slimproto|stream|decode|output, level: info|debug|sdebug
  -e <codec1>,<codec2>	Explicitly exclude native support of one or more codecs; known codecs: flac,pcm,mp3,ogg,aac (mad,mpg for specific mp3 codec)
  -f <logfile>		Write debug to logfile
  -m <mac addr>		Set mac address, format: ab:cd:ef:12:34:56
  -M <modelname>	Set the squeezelite player model name sent to the server (default: SqueezeLite)
  -n <name>		Set the player name
  -N <filename>		Store player name in filename to allow server defined name changes to be shared between servers (not supported with -n)
  -p <priority>		Set real time priority of output thread (1-99)
  -P <filename>		Store the process id (PID) in filename
  -r <rates>[:<delay>]	Sample rates supported, allows output to be off when squeezelite is started; rates = <maxrate>|<minrate>-<maxrate>|<rate1>,<rate2>,<rate3>; delay = optional delay switching rates in ms
  -L 			List volume controls for output device
  -U <control>		Unmute ALSA control and set to full volume (not supported with -V)
  -V <control>		Use ALSA control for volume adjustment, otherwise use software volume adjustment
  -z 			Daemonize
  -t 			License terms
  -? 			Display this help text

Build options: LINUX ALSA EVENTFD
```
