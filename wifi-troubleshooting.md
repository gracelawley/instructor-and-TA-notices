Wifi Troubleshooting
====================

**Problem:**

Can connect to the conference wifi successfully but some/all webpages
won’t load.

**Things to try:**

1.  Turn on airplane mode for ~30 seconds and then reconnect to the wifi
    (causes wifi to forget your computer and assign you a new IP
    address)
2.  Renew DHCP lease (same as above)
    -   Mac: *Open Network Preferences*, *Advanced*, *TCP IP*, *Renew
        DHCP Lease*
3.  Disconnect and reconnect to wifi
4.  Try a different browser
5.  Restart your computer
6.  Double check that you are using the conference wifi and not the
    hotel wifi

Other notes:
============

-   `devtools::install_github(...)` fails with an error message saying:
    “Error: HTTP error 403. API rate limit exceeded for…”
    -   Meaning: there are too many people also installing packages from
        GitHub at the moment. Try again in 5 minutes and see if you have
        any luck.
