# Voice control for ROS turtlebot with pocketsphinx

The script shows how to control ROS turtlebot 
with English keywords using pocketsphinx

Compared to [an earlier implementation](https://github.com/mikeferguson/pocketsphinx), this one:
- enables the keyword search mode, which should better filter not needed words
- uses [pocketsphinx-python](https://github.com/cmusphinx/pocketsphinx-python) instead of Gstreamer
- is really simple (just a script to run)

It was currently tested only for linux and ROS Indigo turtlebot

## Installation

### Install pocketsphinx with dependencies

```
sudo apt-get install -y python python-dev python-pip build-essential swig libpulse-dev git
sudo pip install pyaudio
sudo pip install pocketsphinx
```

### Install ROS

If you are new to ROS (like me), check this [introductory video](https://www.youtube.com/watch?v=9U6GDonGFHw) for ROS installation details

More instructions can be found on [ROS website](http://wiki.ros.org/ROS/Installation)

## Running an example 

Run turtlebot environment:

```
roslaunch turtlebot_gazebo turtlebot_world.launch
```

In a separate terminal run the script:

```
python ros_voice_control.py
```

Speak one of the default commands ( forward / move / stop / left / right / back / full speed / half speed )

## Using your own keywords

You can run this with any set of words. To do that, you need lexicon and keyword list files
(check voice_cmd.dic and voice_cmd.kwlist for details). 

Word pronunciations for English can be found in 
[CMUdict](https://sourceforge.net/projects/cmusphinx/files/G2P%20Models/phonetisaurus-cmudict-split.tar.gz)

You can also download pocketsphinx acoustic models for several other languages [here](https://sourceforge.net/projects/cmusphinx/files/)

Read more about pocketsphinx on the official website: http://cmusphinx.sourceforge.net

