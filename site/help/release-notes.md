---
title: Release Notes
authors: 
- name: Tim Murphy
  email: tim@26tp.com
---
# Release Notes

## 24th December 2014, 14:46 AEST

- Changed web hosting company to [Microsoft Azure](http://azure.microsoft.com/en-us/).
- Added [site monitoring](http://uptimerobot.com/) to alert me if the site goes down.
- Previously the site would "go to sleep" if it wasn't used for 20 minutes. That resulted in a very slow startup experience for first user after 20 minutes. That site now always remains "awake".
- Fixed confirmation email sent on successful registration.
- Many improved internal procedures:
    - Improved & simplified deployment system.
    - More automated tests.
    - Improved test system.
    - Shaved 1.8 seconds off application startup.
    - Updated library dependencies.
    - Added [load testing](https://loader.io/s/iEeyH). Load testing simulates how the site will respond with a number of connected users.