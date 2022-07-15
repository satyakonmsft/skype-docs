---
title: Skype for Business 2015 Sign Out
description: Describes signing out in the Skype Web SDK and provides a code example for the sign out functionality.
---
# Sign Out

 _**Applies to:** Skype for Business 2015_

After sign-in  and creation of the application object we can get access to the signInManager and call signOut() which will trigger cleanup any conversation and active outstanding resources.

## Signing Out

1. Signing Out.

 ```js
    application.signInManager.signOut().then(function () {
        // signed out succesfully
    }, function (error) {
        // handle error
    });
  ```
