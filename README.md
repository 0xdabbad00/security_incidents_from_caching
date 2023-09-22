# Security Incidents From Caching
Collection of incidents resulting from web caching issues.  This is focused on the problem that results in users seeing the content of other users, when that problem appears as a direct result of a CDN or related web caching configuration change, noticable by many users. When this happens, numerous users will immediately report seeing the content of other users.  This will not record those incidents that result from activity by an attacker or bug bounty researcher, as it is believed those may be resulting from a different problem.

A common cause for some of these is Cloudfront request collapsing. Read about that feature [here](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/RequestAndResponseBehaviorCustomOrigin.html#request-custom-traffic-spikes).

## Why does this repo exist?
This is a problem that occurs regularly and the hope is to identify generic mitigation strategies to detect and avoid it from happening in the future.  If you know of good ways of identifying this problem before it gets pushed to production, please reach out (file a ticket, message me on twitter at https://twitter.com/0xdabbad00, or email me).

# Incidents
| Date | Organization impacted | References | Notes |
| ---- | --------------------- | ---------- | ----- |
| September 8, 2023 | Wyze cameras | [reddit](https://www.reddit.com/r/wyzecam/comments/16dlse8/seeing_someone_elses_webcam_feed/) | | 
| March 21, 2023 | ChatGPT | [reddit](https://www.reddit.com/r/ChatGPT/comments/11wkw5z/has_chatgpt_or_me_been_hacked_ive_never_had_these/) | |
| March 7, 2023 | Loom | [post-mortem](https://www.loom.com/blog/march-7-incident-update) | |
| February, 2023 | Scandinavian Airlines (SAS) | [news article](https://www.bleepingcomputer.com/news/security/scandinavian-airlines-says-cyberattack-caused-passenger-data-leak/amp/) | |
| October 12, 2022 | savelife.in.ua | [post-mortem](https://medium.com/@gleb.pushkov/how-to-prevent-data-leakage-when-using-aws-cloudfront-to-cache-api-requests-5a179bb04bd5) | Result of Cloudfront request collapsing |
| May 27, 2021 | Klarna | [post-mortem](https://www.klarna.com/us/blog/may-27-incident-report/) | |
| March 20, 2021 | Zulip | [post-mortem](https://blog.zulip.com/2021/03/20/zulip-cloud-security-incident/) | Result of Cloudfront request collapsing |
| March 8, 2021 | Github [post-mortem](https://github.blog/2021-03-18-how-we-found-and-fixed-a-rare-race-condition-in-our-session-handling/) | This was a thread safety problem, but the result was similar |
| April 2020 | Italian Social Security (INPS) | [news article](https://www-garanteprivacy-it.translate.goog/home/docweb/-/docweb-display/docweb/9344061?_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=en-US&_x_tr_pto=wapp) | |
| December 25, 2015 | Steam | [post-mortem](https://store.steampowered.com/oldnews/19852) | Cache change was made in response to a DDoS, which caused a different problem |
| Jan 29, 2015 | Apple iTunes | [news article](https://appleinsider.com/articles/15/01/29/itunes-connect-bug-logs-developers-into-random-apple-account-displays-wrong-apps) | Unclear if this was a caching issue, but the symptoms look similar |
