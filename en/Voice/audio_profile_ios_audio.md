
---
title: Set the Stereo/High-fidelity Audio Profile
description: How to set the high-quality audio for iOS and macOS
platform: iOS
updatedAt: Thu Dec 27 2018 02:52:22 GMT+0800 (CST)
---
# Set the Stereo/High-fidelity Audio Profile
## Introduction 

High-fidelity audio is essential for professional audio scenarios, such as for podcasts and singing competitions. For example, podcasts require stereo and high-fidelity audio. High-fidelity audio refers to an audio profile with a 48-KHz sampling rate and a 192-Kbps bitrate. 


## Implementation
Ensure that you prepared the development environment. See [Integrate the SDK](../../en/Voice/ios_audio.md).

The Agora SDK provides the [setAudioProfile](https://docs.agora.io/en/Voice/API%20Reference/oc/Classes/AgoraRtcEngineKit.html#//api/name/setAudioProfile:scenario:) method for developers to set appropriate audio profiles according to the scenarios. This method has two parameters:

- `profile` sets the sampling rate, bitrate, encoding mode, and the number of channels.
- `scenario` sets the audio application scenario. For example, entertainment, education, or live gaming. The SDK optimizes the noise control and audio quality based on the scenarios.

```swift
// swift
// Gaming
agoraKit.setAudioProfile(.speechStandard, scenario: .chatRoomGaming)
// Entertainment
agoraKit.setAudioProfile(.musicStandard, scenario: .chatRoomEntertainment)
// KTV
agoraKit.setAudioProfile(.musicHighQuality, scenario: .chatRoomEntertainment)
// FM high-fidelity
agoraKit.setAudioProfile(.musicHighQuality, scenario: .gameStreaming)
```

```objective-c
// objective-c
// Gaming
[agoraKit setAudioProfile: AgoraAudioProfileSpeechStandard scenario: AgoraAudioScenarioChatRoomGaming];
// Entertainment
[agoraKit setAudioProfile: AgoraAudioProfilemusicStandard, scenario: AgoraAudioScenarioChatRoomEntertainment];
// KTV
[agoraKit setAudioProfile: AgoraAudioProfileMusicHighQuality, scenario: AgoraAudioScenarioChatRoomEntertainment];
// FM high-fidelity
[agoraKit setAudioProfile: AgoraAudioProfilemusicHighQuality, scenario: AgoraAudioScenarioGameStreaming]
```

### API Reference
- [`setAudioProfile`](https://docs.agora.io/en/Voice/API%20Reference/oc/Classes/AgoraRtcEngineKit.html#//api/name/setAudioProfile:scenario:)

## Considerations

- Call the [setAudioProfile](https://docs.agora.io/en/Voice/API%20Reference/oc/Classes/AgoraRtcEngineKit.html#//api/name/setAudioProfile:scenario:) method before joining the channel.
- The `scenario`  parameter takes effect only when the channel profile is live broadcast.
