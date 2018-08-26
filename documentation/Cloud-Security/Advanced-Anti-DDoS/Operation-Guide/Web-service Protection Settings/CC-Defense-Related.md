# Related Configurations of CC Protection Rules
CC protection rules are of web-based protection, so you need to switch the configuration to the web-based forwarding configuration first. </BR>
The steps are as follows:
- First, you need to log in to [Advanced Anti-DDoS Console] (https://ip-anti-console.jdcloud.com/instancelist).
- Find the instance that needs to be configured. Click the instance name to enter the ** Instance Details ** page.
- Switch to ** Website Forwarding Configuration **
   ![Website Forwarding Rules] (https://github.com/jdcloudcom/cn/blob/edit/image/Advanced%20Anti-DDoS/web-rule%2002.png)
   
### Operation Steps
1. Click ** Protection Rules ** to expand the configuration of protection rules.
 ![Website Forwarding Rules] (https://github.com/jdcloudcom/cn/blob/edit/image/Advanced%20Anti-DDoS/web-rule%2004.png)
2. Configure global CC protection policy.
 ![Website Forwarding Rules] (https://github.com/jdcloudcom/cn/blob/edit/image/Advanced%20Anti-DDoS/CC%20rules%2001.png)
The following is the interpretation of the rules:
- CC protection of the protection rules takes effect globally, so global CC protection is on when the CC protection is on.
- If the global CC protection is closed, all CC protection of the configured domain names in the website forwarding configuration will be turned off.
- CC protection peak value shows the peak size of CC protection of the purchased package.
- CC protection mode configuration. The system supports four kinds of CC protection modes: </BR>
"Loose": Only few of the visits will be checked through CC rules. Suitable for websites with not many visits. </BR>
"Normal": When there is no obvious exception in the website, please select the normal mode. Only part of visits is checked</BR>
"Critical": In case of the slow website response, and exception in the CPU, memory, etc., use the emergency mode. This mode is of rigorous detection and may cause false judgment. </BR>
"Customization": Appropriate for advanced users. Enables them to customize the protection threshold. Includes HTTP request number threshold, the protection threshold of each Host, the protection threshold of each Host + URI, the protection threshold of each source IP to Host, the protection threshold of each source IP to Host + URI. The maximum HTTP request number threshold does not exceed the threshold of the purchased package. </BR>

3. Configure CC protection policies for single domain name. </BR>
 - If the global CC protection is on, the CC protection of a separate domain name can be closed.
 - If global CC protection is off, the CC protection of certain single domain name cannot be turned on.
4. CC observation mode</BR>
If CC observation mode is turned on, CC protection only sends alarm and does not activate protection.
5. Configure speed limit
- Advanced protection supports limiting the visit speed of source IP. Click the "Edit" button in the speed limit rule for settings. The minimum time can be set to seconds.


