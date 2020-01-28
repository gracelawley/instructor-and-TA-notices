# WiFi Troubleshooting

__Problem:__

Can connect to the conference wifi successfully, but webpages won't load. 


__Verify the Problem:__

Go to [speedtest.net](https://www.speedtest.net) and click "go".
If your upload and download speeds are << 0.5 Mbps, your problem is, in fact, related to your connection to the internet or the WiFi.


__Things to try:__

(These are really just wild guesses of what might work and what *seemed* to have worked for some people. Correlation != causation, etc.)

1. Disable any virtual private network (VPN) that might be running your computer and interfering with the connection.
    (This may reduce the security of your network connection.)
2. Get a new IP address for your computer on the WiFi.
    To do so:
    - Disable your WiFi (or enable airplane mode) for ~30 seconds and then reconnect to the wifi.
    - Renew your DHCP lease
        - on macOS: *System Preferences*, *Network*, select WiFi, *Advanced*, *TCP/IP*, *Renew DHCP Lease*
3. Remove the conference SSID (`rstudio20`) from your known networks, and then add it again after ~30 seconds.
    - on macOS: *System Preferences*, *Network*, select WiFi, *Advanced*, *WiFi*, select `rstudio20` and delete it.
        Then join the WiFi again.
4. Try a different web browser.
5. Power cycle your computer.
6. It appears that the connectivity is better in different areas of the hotel; you might want to try downloading necessary material somewhere else.


# RStudio.cloud Troubleshooting

__Problem:__

Your RStudio Server Pro instance is stuck loading.

__Things to try:__

1. Delete your browser cache. 
    There's *no* need to delete cookies, history, autocomplete suggestions etc.
    Then restart your browser.
2. If you can get to the overview of your RStudio Server Pro instances, quit the instance that isn't loading and add a new one.
   This will delete any *unsaved* changes in your files.


# Package Installation Troubleshooting

__Problem:__

When running `remotes::install_github()` you get:

> `Error: HTTP error 403. API rate limit exceeded for` ...


__Things to try:__

This problem is likely caused by many conference attendees sharing the same external IP address.
As GitHub.com notices a lot of these anonymous requests from the same IP address, we collectively hit a rate limit that GitHub.com has implemented for security reasons.

To solve this problem you need a GitHub.com account, and then save some credentials (a personal access token, or PAT) on your machine.
Notice that this will change the environment on your computer.

The {usethis} package has a convenience function [`usethis::browse_github_token()`](https://usethis.r-lib.org/reference/browse_github_token.htm) that you can run from your R console to guide you through the process.
You can learn more about the GitHub authentication [here](https://happygitwithr.com/github-pat.html).