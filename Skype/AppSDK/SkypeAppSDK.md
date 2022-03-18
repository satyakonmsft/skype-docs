---
title: Skype for Business App SDK
description: Introduction to the Skype for Business App SDK
ms.date: 02/10/2021
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
[Skype for Business (SfB) Online will be retired in July 2021](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/skype-for-business-online-to-be-retired-in-2021/ba-p/777833). The Skype for Business App SDK will continue to function for on-premise Skype for Business Server 2019 deployments, but the retirement of SfB Online is reducing the market of addressable communication deployments for the SfB App SDK, and many SfB organizations are migrating to Teams. Teams Meetings cannot be joined by the SfB Mobile SDK. 

Azure Communication Services is a cloud-based communications service that lets you add voice, video, chat, and telephony to your apps. ACS applications have the ability to join Teams meetings (as a guest), and we encourage implementers of the SfB App SDK to transition to Azure Communication Services. The ability to [join Teams meetings using ACS](/azure/communication-services/concepts/join-teams-meeting) is now generally available.

### Azure SDKs that join Teams meetings

Azure Communication Services has multiple SDKs that can join Teams meetings listed below. 

|SDK| Implementation Complexity|	Customization Ability|	Calling| Chat| [Join Teams Meetings](https://docs.microsoft.com/azure/communication-services/concepts/voice-video-calling/teams-interop)
|---|---|---|---|---|---|
|[Core SDKs](https://docs.microsoft.com/azure/communication-services/concepts/sdk-options)|High|High|✔|✔ |✔|
|[Base Components](https://docs.microsoft.com/azure/communication-services/concepts/ui-framework/ui-sdk-overview)|Medium|Medium|✔|✔|✔|
|[Open-Source Composite](https://docs.microsoft.com/azure/communication-services/concepts/ui-framework/ui-sdk-overview)|Low|Low|✔|✔|✔|

More specific guidance for transitioning a SfB Mobile SDK implementation to ACS Meetings:

1. Explore key ACS concepts: 
 - [Overview](https://docs.microsoft.com/azure/communication-services/overview)
 - [Identity](https://docs.microsoft.com/azure/communication-services/concepts/identity-model)
 - [Client/server architecture](https://docs.microsoft.com/azure/communication-services/concepts/client-and-server-architecture)
 - [Authentication](https://docs.microsoft.com/azure/communication-services/concepts/authentication?tabs=csharp)
 - [UI Library](https://azure.github.io/communication-ui-library/)
2. Create an Azure Communication Services resource in the Azure portal[[quickstart](https://docs.microsoft.com/azure/communication-services/quickstarts/create-communication-resource?tabs=windows&pivots=platform-azp)]
3.  Allocate user access tokens [[quickstart](https://docs.microsoft.com/azure/communication-services/quickstarts/access-tokens?pivots=programming-language-csharp)]
4.   Use the Calling SDK to implement your app. [Samples](https://docs.microsoft.com/azure/communication-services/samples/calling-hero-sample?pivots=platform-ios) are available to help get started.
