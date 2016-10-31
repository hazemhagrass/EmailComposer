
# EmailComposer with attachments handling

This Plugin is inspired from EmailComposer plugin [here](https://github.com/GalCohen/EmailComposer-phonegap-plugin).

This plugin allows you to send html email to any email accounts you want including attachments

This has been successfully tested from Cordova 2.2.0 through to version 6.3.

  Callable interface:
```javascript
	window.plugins.EmailComposer.showEmailComposerWithCallback(callback,subject,body,toRecipients,ccRecipients,bccRecipients,isHtml,attachments);
```

or

  ```javascript
	window.plugins.EmailComposer.showEmailComposer(subject,body,toRecipients,ccRecipients,bccRecipients,isHtml,attachments);
```

## Installation

for Cordova >= 3.0.0

```javascript
    phonegap local plugin add https://github.com/hazemhagrass/EmailComposer.git
    cordova plugin add https://github.com/hazemhagrass/EmailComposer.git
```

for Cordova >= 5.0.0
```javascript
    cordova plugin add com-badrit-emailcomposer
```

**ATTENTION:** the callback will never be triggered, it's here only for consistency with the iOS plugin

**Parameters:**
- callback: just for compatability with the old plugin and will be updated to work soon
- subject: a string representing the subject of the email; could be empty
- body: a string representing the email body (could be HTML code, in this case set **isHtml** to **true**); could be empty
- toRecipients: array containing all the email addresses for TO field; could be empty
- ccRecipients: array containing all the email addresses for CC field; could be empty
- bccRecipients: a js array containing all the email addresses for BCC field;  could be empty
- isHtml: a bool value indicating if the body is HTML or plain text
- attachments: a js array containing all full paths to the files you want to attach; could be empty

**Example**

```javascript
window.plugins.EmailComposer.showEmailComposerWithCallback(null,"Look at this photo","Take a look at <b>this<b/>:",["example@email.com", "johndoe@email.org"],[],[],true,["_complete_path/image.jpg", "_other_complete_path/file.zip"]);
```