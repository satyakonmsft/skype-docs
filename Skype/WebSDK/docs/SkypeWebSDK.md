# Skype Web SDK

 _**Applies to:** Skype for Business 2015_, _Skype for Business Online_

The Skype Developer Platform for Web ("Skype Web SDK") is a set of JavaScript Web APIs and HTML controls that enable you to build web experiences that seamlessly integrate a wide variety of real-time collaboration models leveraging Skype for Business services and the larger Skype network. It provides support for multiple core collaboration services like presence, chat, audio, and video, enabling web experiences across a broad spectrum of users, platforms, and devices.

The Skype Web SDK documentation consists of the following sections:

- [Skype Web SDK general reference](GeneralReference.md)
- [Skype Web SDK API reference](http://officedev.github.io/skype-docs/Skype/WebSDK/model/api/modules/jcafe.html)
    
# Skype for Business Online Retirement

[Skype for Business (SfB) Online will be retired in July 2021](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/skype-for-business-online-to-be-retired-in-2021/ba-p/777833). The retirement of SfB Online is reducing the market of Skype tenants for the SfB Web SDK, and many SfB organizations are migrating to Teams.

Azure Communication Services (ACS) is a cloud-based communications service that lets you add voice, video, chat, and telephony to your apps. ACS applications today can interop with Teams on behalf of an anonymous user. The ability to interact with Teams on behalf of M365 users is in development, and we encourage implementers of the SfB Web SDK to transition to Azure Communication Services and Microsoft Graph APIs. Microsoft Graph APIs are used to control behavior specifically in the M365 ecosystems, such as presence.

The table below maps SfB Web SDK sub-systems to Graph and ACS capabilities.

| SfB SDK System | Description  | Alternative   |
|----------|-----------|------------|
| [Presence](https://docs.microsoft.com/en-us/skype-sdk/websdk/docs/presence) | Use presence information to help users decide whether and how they should person other users. | Graph Presence APIs  |
| [Local user](https://docs.microsoft.com/en-us/skype-sdk/websdk/docs/localuser) | Use the **mePerson** object to represent the currently signed-in user. | Graph APIs  |
| [Conversations](https://docs.microsoft.com/en-us/skype-sdk/websdk/docs/conversations) | Use conversation services to determine the ways for communication between persons. | ACS Calling SDK for voice/video [Graph for chat](https://docs.microsoft.com/en-us/graph/api/resources/chat?view=graph-rest-beta) |
| [Listening for and generating presence events](https://docs.microsoft.com/en-us/skype-sdk/websdk/docs/presenceevents) | Use events to get a person's current presence. | Graph Presence APIs  |
| [Persons](https://docs.microsoft.com/en-us/skype-sdk/websdk/docs/persons) | Use person objects to represent individual users. | Graph APIs  |
| [Devices](https://docs.microsoft.com/en-us/skype-sdk/websdk/docs/devices) | Select Cameras, Microphones, and Speakers to use for audio and video conversations. | ACS Calling SDK  |

Azure Communication Service SDKs are designed with a substantially different API model than SfB Web, and we do not host the SDK on a content delivery network (CDN). Your web application hosts the SDK, and you have the choice of using one of several SDKs listed below. The core Calling and Chat SDKs have essentially no GUI and allow for robust customization of the end-user experience. But for most SfB Web SDK implementations, usage of the open-source composites is recommended to reduce the amount of UI development required by the replacement of SfB.

| **SDK** | **Implementation Complexity** | **Customization Ability** | **Calling** | **Chat** | [Interact on behalf of a M365/Teams users](https://docs.microsoft.com/azure/communication-services/concepts/voice-video-calling/teams-interop) |
|------------------------------------------------------------------------------------------------------------------------|-------------------------------|---------------------------|-------------|----------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| [Core SDKs](https://docs.microsoft.com/azure/communication-services/concepts/sdk-options) | High | High | ✔ | ✔ | ✔  |
| [Base Components](https://docs.microsoft.com/azure/communication-services/concepts/ui-framework/ui-sdk-overview) | Medium | Medium | ✔ | ✔ | In Development  |
| [Open-Source Composite](https://docs.microsoft.com/azure/communication-services/concepts/ui-framework/ui-sdk-overview) | Low | Low | ✔ | ✔ | In Development  |

To use Graph and ACS SDKs as a SfB Web SDK replacement, you will leverage these
features:

| Product          | **Feature**                                                                    |  Status            |
|-----------|-----------------------------------------------------------------------------------------|-----------------|
| **Graph** | Log-in a user to M365                                                                   | Available Today |
| **Graph** | Set presence                                                                            | In Development  |
| **Graph** | Get Presence                                                                            | Available Today |
| **Graph** | Send and receive chat messages                                                          | Available Today |
| **Azure** | Create an ACS token for an M365 user                                                    | In Development  |
| **Azure** | M365 user can call a user in Teams                                                      | In Development  |
| **Azure** | M365 user can join a Teams meeting, interface with the video, audio, and chat channels  | In Development  |
| **Azure** | M365 user can initiate PSTN calls from Teams-allocated phone numbers                    | In Development  |
| **Azure** | M365 user can receive PSTN calls from Teams-allocated phone numbers                     | In Development  |
