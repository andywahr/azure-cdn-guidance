# Azure CDN Guidance

Azure has a number of ways to host your Web Applications and Content.  The Azure Content Delivery Network (CDN) service provides added capabilitiy that allows you thru one of 3 CDN Providers (Microsoft, Verizon, Akamai):
* Cache Static File Content (JS, CSS, Images, Videos, Files, etc..) 
* Cache Web Page Content **Warning read: Caching Dynamic Content** 
* Dynamic Site Acceleration:  Make a consistent global experience for your website utilizing the CDN Provider's network 
* Web Application Firewalll ([WAF](https://en.wikipedia.org/wiki/Web_application_firewall)): Filters, monitors, blocks HTTP traffic.

A CDN Provider deploys an extremely large (regionally or globally) infrastructure that consists of a network of Points of Presences (Pops) which effectively are mini-data centers.  These data centers are linked together in a private network allowing a CDN Provider to control latency and performance, and provide consistent service for regional or global traffic management and caching.  By using a CDN in front of your site, you effectively extend the "Edge" of your web site closer to end users.  When you have an asset being served by a CDN:
1. Your end users' connection to your site is handled closer to them (much more consistent connection and faster SSL handshake since this almost always since the CDN is closer to the user than your site)
1. If the asset is cached, it will be delivered directly from that Pop (it doesn't have to make a request to your web site)
1. If your site is being accelerated, you get more consistent world wide performance (users connect to the nearest Pop, then traverse close to your site thur the CDN's private network not the public internet)
1. If your site has WAF, blocking occurs at the "Edge" or at the Pop, and you site is not impacted

There are several strategies on how to take advantage of CDN, but it has all to do about how often the content of the URL request changes.

# Static File Content
This is the easiest
