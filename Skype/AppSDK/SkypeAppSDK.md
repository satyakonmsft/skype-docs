---
title: Skype for Business App SDK
description: Introduction to the Skype for Business App SDK
---
# Skype for Business App SDK

 **Last modified:** Feburary 10, 2021

The Skype for Business App SDK enables developers to seamlessly integrate messaging, audio, and video experiences into mobile and tablet applications. The focus of this SDK is “remote advisor” solutions that enable consumer iOS and Android apps to embed communications from external guests to users within a Skype for Business organization.  To achieve this, the SDK uses the “guest meeting join” capability that is available both for Skype for Business Online and for Skype for Business Server.  

The Skype App SDK documentation consists of the following sections:

- [Overview: Embed Skype business-to-consumer communications in your mobile app](EmbedSkypeB2Ccomms.md)
- [Getting started](GettingStarted.md)
- [App SDK orientation](Orientation.md)
- [Download the App SDK](Download.md)
- [App SDK samples](Samples.md)
- [App SDK library reference - Android](https://aka.ms/sfbAppSDKRef_Android)
- [App SDK library reference - iOS](https://aka.ms/sfbAppSDKRef_iOS)
- [Submit your questions, bugs, feature requests, and contributions](Feedback.md)

## Licensing

Please carefully read the license terms that are included in the SDK download.  By using the SDK, you accept the license terms.


## Migrating to Azure Communication Services
[Skype for Business (SfB) Online will be retired in July 2021](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/skype-for-business-online-to-be-retired-in-2021/ba-p/777833).

The retirement of SfB Online is reducing the market of addressable meetings for the SfB App SDK, and many SfB organizations are migrating to Teams. Teams Meetings cannot be joined by the SfB Mobile SDK.

Azure Communication Services is a cloud-based communications service that lets you add voice, video, chat, and telephony to your apps. ACS applications have the ability to join Teams meetings (as a guest), and we encourage implementers of the SfB App SDK to transition to Azure Communication Services. The ability to join Teams meetings is in active development and restricted to a private preview at this time. 

### Azure SDKs that join Teams meetings

Azure Communication Services has multiple SDKs that can join Teams meetings listed below. The Meeting UI SDK is available for iOS and Android and is the closest equivalent to SfB Mobile, requiring the least amount of code and providing an all-in-one Teams styled interface. For most SfB App SDK customers, this is the best option. 

|SDK| Implementation Complexity|	Customization Ability|	Calling| Chat| [Join Teams Meetings](https://docs.microsoft.com/azure/communication-services/concepts/voice-video-calling/teams-interop)
|---|---|---|---|---|---|
|[Core SDKs](https://docs.microsoft.com/azure/communication-services/concepts/sdk-options)|High|High|✔|✔ |✔|❌
|[Base Components](https://docs.microsoft.com/en-us/azure/communication-services/concepts/ui-framework/ui-sdk-overview)|Medium|Medium|✔|✔|Coming|❌
|[Open-Source Composite](https://docs.microsoft.com/en-us/azure/communication-services/concepts/ui-framework/ui-sdk-overview)|Low|Low|✔|✔|Coming|❌
|[Meeting Composite](https://review.docs.microsoft.com/en-us/azure/communication-services/concepts/ui-framework/meetings?branch=pr-en-us-144662)|Low|Low|❌|❌|✔|✔

More specific guidance for transitioning a SfB Mobile SDK implementation to ACS Meetings:

1. Join the Azure Communication Services TAP program [[on-boarding form](https://aka.ms/ACS-EarlyAdopter)]. 
2. Explore key ACS concepts: 
 - [Overview](https://docs.microsoft.com/en-us/azure/communication-services/overview),
 - [Identity](https://docs.microsoft.com/en-us/azure/communication-services/concepts/identity-model),
 - [Client/server architecture](https://docs.microsoft.com/en-us/azure/communication-services/concepts/client-and-server-architecture),
 - [Authentication](https://docs.microsoft.com/en-us/azure/communication-services/concepts/authentication?tabs=csharp)
3. Create an Azure Communication Services resource in the Azure portal[[quickstart](https://docs.microsoft.com/en-us/azure/communication-services/quickstarts/create-communication-resource?tabs=windows&pivots=platform-azp)]
4.  Allocate user access tokens [[quickstart](https://docs.microsoft.com/en-us/azure/communication-services/quickstarts/access-tokens?pivots=programming-language-csharp)]

5.   Use the Meeting UI SDK. Embeding the Meeting UI SDK is very similar to SfB Mobile. You will authenticate the client with the user access tokens allocated earlier. [[concept](https://review.docs.microsoft.com/en-us/azure/communication-services/concepts/ui-framework/meetings?branch=pr-en-us-144662)][quickstarts:[iOS](https://review.docs.microsoft.com/en-us/azure/communication-services/quickstarts/meeting/getting-started-with-meeting-composite?branch=pr-en-us-144662&pivots=platform-ios),[Android](https://review.docs.microsoft.com/en-us/azure/communication-services/quickstarts/meeting/getting-started-with-meeting-composite?branch=pr-en-us-144662&pivots=platform-android)]

