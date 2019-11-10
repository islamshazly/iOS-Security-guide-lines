# iOS-security-guid-lines
***A few guide lines to secure your iOS app***

**Why you should secure your ios app?**

If your app storing sensitive data like `JWT`, `API keys`, `subscription flags` or any kind of coins for your app, That might be risky if some one knows and use these information. And how ever security level that apple provides us by thier magic but we should do some tricks and movments to secure our app.
So implementing security for your app should never be neglected. 

**Now the instructions :**

- Enable `Bitcode` = `yes`, because if you don't, Any once can make reverse engineering and any malefactor can obtian your app or library then retrive your code from it and steal it's secrets.
And aslo `Bitcode` mminmize your code's size. 

- Disable any logs in `relase` mode, You can do that by using schema supported by xcode it self.

- Don't store sensitive data in UserDefaults, It's easy to explore without any complix proccess.

- Use encrypted database that Apple provided us called keychain too save passwords or any secrets that you  care about such as credit card information or even any other sensitive information.

- You shouldn't store sensitve data in your app's database, It will be easy to get if anyone open app's dir and show database that stors in caches folder.

- `(ATS)` improves privacy and data integrity ,App Transport Security has blocked a cleartext HTTP (http://) resource load since it is insecure. Temporary exceptions can be configured via your app's Info.plist file.

```<key>NSAppTransportSecurity</key>
<dict>
    <key>NSAllowsArbitraryLoads</key>
    <true/>
    <key>NSAllowsArbitraryLoadsForMedia</key>
    <true/>
    <key>NSAllowsArbitraryLoadsInWebContent</key>
    <true/>
</dict>
```
But that may affect of ads of your applications 

-  Don't run your app on Jailbreak device it can get your information form keychain 

- Spend more time for selecting third libs you will use to ensure you don't have leak. 

- Some apps need to hide and show window according app's states that app delegate handle them. 
