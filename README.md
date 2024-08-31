# Autoimpro
8 computational agents select time frames from your improvisation and transpose them. This mimics the behavior of some improvisers and creates layers of sound that can give you ideas for proposing new improvisation materials.

### Autoimpro Configuration and Usage in Max

#### Prerequisites
- **Max 8 or higher**: Autoimpro is compatible with Max 8 and later versions. It is likely to work on earlier versions as well.
- **Compatible Platforms**: MacOS and Windows.
- **HIRT Libraries**: You need to have the HIRT libraries installed via Max's Package Manager.

### Launching Autoimpro
After downloading and unpacking, seek for 0-autoimpro10-0-0.maxpat and open it with Max. You do not need to autorize Max. You do not need to open any other file. The rest of files are dependencies.

#### Initial Setup
1. **Audio Device**:
   - Ensure your audio device is receiving a signal.
   - Select your audio device in Max to receive and emit audio signals.

2. **Audio Settings**:
   - **Leftmost panel**: Adjust the audio levels.
   - **Second panel from the left**: Adjust the recording level.
   - **First left panel**: Adjust the audio output channels according to your audio device's hardware description.

3. **Recording**:
   - Start recording by pressing the message box linked to the receiver [[r resettr]] in the second panel from the left.
   - You can continue recording without erasing everything by pressing the toggle marked with [[marcha]].
   - To record continuously after the recording period has ended, select the toggle labeled 'grabar siempre'. The default recording period is 10 minutes (3600000 ms), adjustable with the message [tampon size $1] in the rightmost panel.

4. **Storage and Retrieval**:
   - Input performances can be stored and retrieved using the messages [tampon write] and [tampon read].

5. **Additional Adjustments**:
   - Adjust the value of the >nTodos number box in the bottom panel for the general input level to the output matrix of all agents.
   - Agents can be muted by pressing the spacebar and reactivated by pressing it again. This setting is in the second panel from the right, where you can also select the fade-in and fade-out times.
   - Many of these settings can be manipulated from the TouchOSC patch attached to the software. Autoimpro's OSC receiver is set to port #8000

#### Advanced Controls
- **Dissent**: Adjust the percentage of times the agents copy each other.
- **Tempered**:
  - Tempered transposition: Adjust the limits in semitones above and below.
  - Non-tempered transposition: Adjust the limits proportionally (e.g., 1 is the same pitch, 2 is the octave above, 0.5 is the octave below).
  - Ensure the sample rate of the buffer memory matches the system's [tampon sr $1].
  - Stereo 1 provides stereo output. The performer is centered and the agents are distributed from left to rigth. This option is the default.
  - Stereo 0 provides octophonic output. The performer channels are 1 and 2. Agent outputs are 1 to 8.
  - Stereo 2 is an experimental option. It assumes you are working with Miller Puckette's Netty-McNetFace sending and receiving sound data through      Blackhole. Netty-McNetface received sound is sent throught Blackhole channels 3 and 4. Autoimpro receives input through a virtual device            consisting of a physical interface with 10 input channels and 12 output channels, along with the 64 input channels of Blackhole. Therefore,         this option automatically configures channels 3 and 4 of the [[adc~]] and [[dac~]] as inputs and outputs 13 and 14. You don't need to use this      options if you are no trying this weird configuration.

#### Useful Subpatches
- **[[p llegadassalidas]]**: Precise configuration of output behavior.
- **[[p afinar i tempo]]**: Provides beat and an oscillator for tuning. You should change the contents of sound buffers or adust de MIDI device in    order to perceive any rythm
- **[[p ip]]**: provides your ip public address. This is useful when running a Netty-McNetface server and Netty-McNetface clients. 

By following these steps and configurations, you can efficiently start using Autoimpro to generate complex sound patterns based on improvisation.

### Autoimpro Licence

Autoimpro is licensed under a CC BY-SA 4.0 license · ATTRIBUTION-SHAREALIKE 4.0 INTERNATIONAL

YOUR USE OF  IMPROSOLO IS ENTIRELY AT YOUR OWN RISK. WE MAKE NO REPRESENTATIONS OR WARRANTIES ABOUT IMPROSOLO. IMPROSOLO IS PROVIDED "AS IS", “WITH ALL FAULTS,” AND “AS AVAILABLE.” WITHOUT LIMITING THE GENERALITY OF THE FOREGOING, WE DISCLAIM ALL WARRANTIES, EXPRESS, STATUTORY OR IMPLIED, INCLUDING, BUT NOT LIMITED TO: (1) THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE, WORKMANLIKE EFFORT, TITLE, QUIET ENJOYMENT, NO LIENS AND NO ENCUMBRANCES; (2) THE WARRANTIES AGAINST INFRINGEMENT, MISAPPROPRIATION OR VIOLATION OF ANY INTELLECTUAL PROPERTY OR PROPRIETARY RIGHTS OF ANY PERSON; (3) THE WARRANTIES ARISING THROUGH COURSE OF DEALING OR USAGE IN TRADE; AND (4) THE WARRANTIES RELATING TO THE ACCURACY, RELIABILITY, CORRECTNESS, OR COMPLETENESS OF DATA OR CONTENT MADE AVAILABLE ON THE PLATFORM OR OTHERWISE BY SNAPPET. THERE IS NO WARRANTY THAT THE PLATFORM WILL MEET YOUR NEEDS OR REQUIREMENTS OR THE NEEDS OR REQUIREMENTS OF ANY OTHER PERSON OR THE NEEDS OR REQUIREMENTS SET FORTH IN ANY DOCUMENTATION. WE MAKE NO WARRANTIES, EXPRESS, STATUTORY OR IMPLIED THAT THE PLATFORM WILL BE TIMELY, SECURE, ACCURATE, ERROR-FREE, COMPLETE, UP-TO-DATE, FREE OF VIRUSES, OR UNINTERRUPTED. IF APPLICABLE LAW DOES NOT ALLOW THE EXCLUSION OF SOME OR ALL OF THE ABOVE IMPLIED OR STATUTORY WARRANTIES TO APPLY TO YOU, THE ABOVE EXCLUSIONS WILL APPLY TO YOU TO THE FULLEST EXTENT PERMITTED BY APPLICABLE LAW
