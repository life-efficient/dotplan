# 🧠 WiFi Misconfiguration: Losing Hotspot Access on the Pi (2025-06-26)

Today I ran into a frustrating issue while trying to switch my Raspberry Pi's WiFi from my phone's hotspot to my office network. My goal was to have the Pi connect to my office WiFi if my hotspot was off, but ideally, it would always connect to my hotspot first if it was available.

To do this, I added a new `wpa_supplicant.conf` file with my office network's WiFi credentials. I thought this would allow the Pi to automatically connect to the office network when my hotspot wasn't present. However, after rebooting the Pi with my hotspot turned off, I found that it didn't connect to the office WiFi as expected. Worse, when I turned my hotspot back on, the Pi still didn't connect to it.

Now, the Pi doesn't seem to connect to either network, and I can't access it over my hotspot anymore. I suspect that the presence of the office WiFi credentials in `wpa_supplicant.conf` is interfering with the Pi's ability to prioritize or fall back to the hotspot network.

My next step is to take the Pi out of range of the office WiFi and see if it will reconnect to my hotspot. This should help determine whether the Pi is getting "stuck" trying to connect to the office network when both are available, or if there's a deeper configuration issue preventing any WiFi connection at all. 