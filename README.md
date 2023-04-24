# Widget PSTN Dialout
This is repo serves as an example of how you can use functionality of the [Webex Browser SDK](https://developer.webex.com/docs/sdks/browser) (like the ```.invite()``` function) in conjunction with the Webex Widget.

## Overview

In some cases, the Webex [Widget](https://developer.webex.com/docs/widgets) may be ideal for a demo or Proof of Concept application, because it is much easier to implement than the Browser SDK.  The main reason for this, is that the widget comes with many UI components built in already.  If your app needs to use even one function of the SDK, then that could mean that your entire app needs to utilize the SDK, in order to be able to access that one function.  

In this project, we show that you can implement the Widget and the SDK in the same web app, so that you can still leverage the widget for your UI components, and use the SDK for [any functions](https://webex.github.io/webex-js-sdk/api/) that don't exist in the widget, but do exist in the SDK.

1. In widget_pstn_dialout.html, we init the widget and the SDK.  
2. Then, we listen for a new call to be "created" in the widget (which happens when the user clicks the button to join the space meeting).
3. When our call listener is triggered, we sync the meetings in our SDK instance, so that it will be aware of our Widget's meeting.
4. Once the SDK has synced, we can perform a function of the SDK on the meeting.  In this case, we .invite() a PSTN to join the ongoing meeting.


## Setup

### Prerequisites & Dependencies: 
No special requirements.  Simply follow the instructions in the next section.

### Installation and Usage:
You will need to replace the following variables with actual values (currently lines 13 - 15 in the .html file):
```
      let token = 'ACCESS_TOKEN';
      let spaceId = 'ROOM_ID';
      let phoneNumber = '+13215555555'
```
```token``` should be a Webex Access Token with Meetings scopes.  You can copy your (temporary) Access Token from the field here:  
https://developer.webex.com/docs/getting-started#accounts-and-authentication  
```spaceId``` should be a string roomId of the space where you want the call to be made:  
https://developer.webex.com/docs/api/v1/rooms  
```phoneNumber``` should be a string that begins with "+" and the country code ("1" for U.S./Canada).  

Then, you can simply open this HTML file in a supported web browser.

## License
All contents are licensed under the MIT license. Please see [license](LICENSE) for details.


## Disclaimer
<!-- Keep the following here -->  
 Everything included is for demo and Proof of Concept purposes only. Use of the site is solely at your own risk. This site may contain links to third party content, which we do not warrant, endorse, or assume liability for. These demos are for Cisco Webex usecases, but are not Official Cisco Webex Branded demos.

## Support

Please reach out to the WXSD team at [wxsd@external.cisco.com](mailto:wxsd@external.cisco.com?subject=advanced-presentation-controls).
