# hd-idle

hd-idle is a utility program for spinning-down external disks after a period
of idle time. Since most external IDE disk enclosures don't support setting
the IDE idle timer, a program like hd-idle is required to spin down idle
disks automatically.

A word of caution: hard disks don't like spinning up too often. Laptop disks
are more robust in this respect than desktop disks but if you set your disks
to spin down after a few seconds you may damage the disk over time due to the
stress the spin-up causes on the spindle motor and bearings. It seems that
manufacturers recommend a minimum idle time of 3-5 minutes, the default in
hd-idle is 10 minutes.

One more word of caution: hd-idle will spin down any disk accessible via the
SCSI layer (USB, IEEE1394, ...) but it will NOT work with real SCSI disks
because they don't spin up automatically. Thus it's not called scsi-idle and
I don't recommend using it on a real SCSI system unless you have a kernel
patch that automatically starts the SCSI disks after receiving a sense buffer
indicating the disk has been stopped. Without such a patch, real SCSI disks
won't start again and you can as well pull the plug.

You have been warned...
