# WiFi Troubleshooting

## Problem

You can connect to the conference WiFi successfully, but webpages won't load. 


### Verify the Problem

Go to [speedtest.net](https://www.speedtest.net) and click "go".
If your upload and download speeds are << 0.5 Mbps, your problem is, in fact, related to your connection to the internet or the WiFi.


### Things to try

*These are really just wild guesses of what might work and what seemed to have worked for some people. Correlation != causation, etc.*

1. Disable any virtual private network (VPN) that might be running your computer and interfering with the connection. *Note: this may reduce the security of your network connection* 
2. Get a new IP address for your computer on the WiFi. To do so:
    - Disable your WiFi (or enable airplane mode) for ~30 seconds and then reconnect to the WiFi, or
    - Renew your DHCP lease.
        - on macOS: *System Preferences* > *Network* > select WiFi > *Advanced* > *TCP/IP* > *Renew DHCP Lease*
3. Remove the conference SSID (e.g. `rstudio20`) from your known networks, wait ~30 seconds, then add it again.
    - on macOS: *System Preferences* > *Network* > select WiFi > *Advanced* > *WiFi* > select `rstudio20` and delete it > join the WiFi again
4. Try a different web browser.
5. Power cycle your computer.
6. If it seems as though the connectivity is better in different areas of the hotel (we found that download speeds were noticeably better right outside of the workshop room), you might want to try downloading necessary material somewhere else.


# RStudio Cloud Troubleshooting

## Problem

Your RStudio Server Pro session is stuck loading.

### Things to try

1. Delete your browser cache and then restart your browser.
    - There's *no* need to delete cookies, history, autocomplete suggestions etc.
2.  Quit the session that isn't loading and start a new one. *Note: This will delete any unsaved changes in your files!* To do so:
    1. Click on the *Home* icon in the upper right. This will take your to the RStudio Server Home page where you can see an overview of your RStudio Server Pro sessions.
    2. Under *Sessions*, click *Quit* for the session that isn't loading.
    3. Click *New Session*.


# Package Installation Troubleshooting

## Problem

When running `remotes::install_github()` you get:

> `Error: HTTP error 403. API rate limit exceeded for` ...

This problem is likely caused by many conference attendees sharing the same external IP address. 
As GitHub notices a lot of these unauthenticated requests from the same IP address, we collectively hit a rate limit that GitHub has implemented for security reasons.


### Things to try

1. Wait and try `remotes::install_github()` again later, or
2. Create a GitHub account (if you don't already have one) and set up a GitHub personal access token (PAT). *Note: this will change the environment on your computer!*
    - You can learn more about how to create a GitHub PAT in [this section](https://happygitwithr.com/github-pat.html) of happygitwithr.
