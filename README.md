# vdr-addon-atwakeup
A VDR wakeup that uses the "at" instead of acpi. Good for running on a server.

If you run VDR headless on a server you might still want to use it's auto shutdown feature.
It is desirable to shutdown the VDR to save power. Especially when it could cause power consumption outside the server.
A SAT connection with an LNB would not know that it can turn off itself to save power.
In my case there is a Digital Devices Octopus S8 that feeds power to the LNB when there are open streams.
If all VDR instances are off, then the Octopus removes power from the LNB and could go into some sleep state.

There is the acpiwakeup addon. But that writes directly to the RTC and expects the machine shuts down soon.
In a server, the VDR can be off while the rest of the system still runs, so there is no way to start the vdr (except reboot).

That is the reason why this addon uses the "at" to start the vdr on time.

Most servers run 7/24, then this addon is sufficient already.
If you are like me and want to turn off the server at night, this is TBD.
One way could be to additionally use the acpiwakeup, but ensure that nobody else touches the RTC.
In my case I use an auto shutdown script (I published to Ubuntu users some years ago - https://wiki.ubuntuusers.de/Skripte/Auto_OFF/). 
For the VDR I hacked it a bit, but will need some review.

Note: I wrote this addon a few years ago and now adjust to modern requirements (systemd, ansible).
So the current status is unstable. Use it at your own risk.

You can reach me in the VDR portal, my user name is Dieter.
