
---
title: Release Notes
description: 
platform: Unity
updatedAt: Mon Jan 28 2019 11:27:35 GMT+0800 (CST)
---
# Release Notes
## Introduction

The Agora Unity SDK for Interactive Gaming provides C# interfaces to implement the voice and video functions for gaming on the Unity platform. 

For key features, see [Interactive Gaming Overview](https://docs.agora.io/en/Interactive%20Gaming/product_gaming?platform=All%20Platforms).

## v2.2.0 

v2.2.0 was released on January 28, 2019. See below for new features and API changes.

### New Features

#### 1. Set the Voice-only Mode

Adds the `SetVoiceOnlyMode` method to set the voice-only mode. Once voice-only mode is enabled, the SDK transmits only the voice stream, but not other streams, like the sound of keyboard strokes. This function effectively optimizes the audio quality.

#### 2. Set the Audio Effect Playback Position

Adds the `SetRemoteVoicePosition` method to set the playback position and volume of the audio effects sent from the remote user.

#### 3. Enables/Disables the Local Audio Module

When an app joins a channel, the audio module is enabled by default. Added the `EnableLocalAudio` method to disable and re-enable the local audio capture, that is, to stop or restart local audio capturing and processing. The `OnMicrophoneEnabledHandler` callback is triggered once the local audio module is disabled or re-enabled. This method does not affect receiving or playing the remote audio streams, and is applicable to scenarios where the user wants to receive remote audio streams without sending any audio stream to other users in the channel.

#### 4. Sets Whether to Receive the Audio/Video Streams by Default

Added the `SetDefaultMuteAllRemoteAudioStreams` and `SetDefaultMuteAllRemoteVideoStreams` methods to set whether to receive the audio or video streams by default.

#### 5. Indicate the First Local Audio Frame is Received/Sent 

Added the `OnFirstRemoteAudioFrameHandler` and `OnFirstLocalAudioFrameHandler` callbacks to indicate that the first remote audio frame is received or sent successfully.

#### 6. Indicate an API is Executed

Added the `OnApiExecutedHandler` callback to indicate that an API method is executed.

### API Changes

#### Added

- [EnableLocalAudio](../../en/API%20Reference/game_unity.md)
- [SetDefaultMuteAllRemoteAudioStreams](../../cn/API%20Reference/game_unity.md)
- [SetDefaultMuteAllRemoteVideoStreams](../../en/API%20Reference/game_unity.md)
- [OnMicrophoneEnabledHandler](../../en/API%20Reference/game_unity.md)
- [OnFirstRemoteAudioFrameHandler](../../en/API%20Reference/game_unity.md)
- [OnFirstLocalAudioFrameHandler](../../en/API%20Reference/game_unity.md)
- [OnApiExecutedHandler](../../cn/API%20Reference/game_unity.md)

#### Deleted

- `GetMediaEngineVersion`
- `GetParemeter`
- `Poll`

## v2.1.0

The version 2.1.0 was released on February 27, 2018. See below for new features, improvements, and issues fixed.

### New Features

<table>
<colgroup>
<col/>
<col/>
</colgroup>
<thead>
<tr><th>Function</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr><td>Set the Voice-only Mode</td>
<td>Added an interface to set the voice-only mode to optimize the audio quality.</td>
</tr>
<tr><td>Set the Audio Effect Position</td>
<td>Added an interface to set the position and volume of the audio effects sent from the remote user.</td>
</tr>
<tr><td>Set the Local Voice Pitch</td>
<td>Added an interface to set the pitch of the local voice.</td>
</tr>
<tr><td>Indicate a Role Change</td>
<td>Added a callback interface in the command mode to indicate a role change between the host and audience in the channel.</td>
</tr>
<tr><td>Indicate the Video is Muted</td>
<td>Added a callback interface to indicate whether the remote user muted/unmuted the video stream.</td>
</tr>
<tr><td>Update the API Names</td>
<td>Deleted <code>ForGaming</code> in all the API classes and enumerations.</td>
</tr>
</tbody>
</table>



### Improvements

<table>
<colgroup>
<col/>
<col/>
</colgroup>
<thead>
<tr><th>Improvement</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr><td>Reduce the Bandwidth</td>
<td>
<ul>
<li>Before v2.1.0: If you muted the audio or video stream of the remote user, the network still sent the stream.</li> 
<li>Starting from v2.1.0: If you mute the stream of the remote user, the network will not send the stream to reduce the bandwidth.</li>
</ul></td>
</tr>
</tbody>
</table>



### Fixed Issues

-   Occasional crashes under specific circumstances.
-   Unexpected behavior related to the audio routing.


## v2.0

The version 2.0 was released on August 26, 2017. See below for new features and issues fixed.

### New Features:

-   Added the video functions for Unity.
-   Added a function of adjusting the background music with the volume keys after the audio is muted.


### Fixed Issues:

-   Audio effect playback-related issues.
-   Low-volume with earphones on iOS devices.
-   Recording related issues on Android devices.


## v1.1

The version 1.1 was released on May 25, 2017. 

- Native-iOS: Renamed the <code>joinChannel</code> API to <code>joinChannelByToken</code>.
- Native-iOS: Added the <code>startAudioRecording</code>and <code>stopAudioRecording</code> methods.
- Native-iOS: Added the <code>onWarning</code> message to indicate low recording volume.
- Native-Android: Added the <code>startAudioRecording</code> and <code>stopAudioRecording</code> methods.
- Android: Optimized the native <code>pause</code>/<code>resume</code> interfaces.
- Optimized the audio quality on certain cell phones.
- Fixed the recording noise when calling <code>startAudioRecording</code>.


## v1.0 

The version 1.0 was released on May 3, 2017.

This is the first release of the SDK, which includes the following functions:

### 1. Provided the following APIs:


- Unity3D SDK (C# APIs).
- Cocos2d SDK (C++ APIs).
- Native SDK: Android (Java APIs) and iOS (Objective-C APIs).
- Multiple audio effect mixing, such as preload mode and panning.
- Virtual surround sound panning of each UID’s voice according to the in-game coordinates.
- Voice morphing feature.
- Noise block API: Block all non-vocal sounds to ensure a clear in-game chat.

### 2. Package size reduction.

### 3. Performance optimization.
