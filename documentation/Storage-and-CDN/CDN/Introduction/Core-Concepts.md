# Core concept
 **CNAME Record**

It is a Canonical Name record; when the DNS system queries the name on the left side of CNAME, it will go to the name on the right side of CNAME and then query it until the last PTR or A name, and will respond after successful query; otherwise it fails.

**CNAME Domain Name**

The CDN domain name acceleration needs to use the CNAME record. After the CDN acceleration is configured in the JD Cloud console, the user will get an accelerated CNAME domain name (*.*.jcloud-cdn.com), and the user needs to configure a CNAME record at the domain name service provider and point his domain name to the domain name of *.* .jcloud-cdn.com as CNAME, so that all requests for the domain name will be redirected to the node of JD Cloud CDN.

**Edge Node**

Also known as a CDN node, a Cache node, etc., that is, a server cluster distributed in various regions and among various operators and caches the origin server content. Because it is physically closest to netizens, netizens can obtain content faster, thus realizing the acceleration of website or application content.