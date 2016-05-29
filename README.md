# g810-led

Linux led controller for the Logitech G810 Keyboard

This is first short... Wait for a more polished version...

At this time, work on only at root or with sudo.

Dependencies :
- Python2
- pyusb

Use :
g810-led {key} {color}
g810-led {profilefile}

Samples :
g810-led F1 ff0000
g810-led /etc/g810/profile1


Install (Copy g810-led in /usr/bin) :
cp g810-led /usr/bin


Profiles :
mkdir /etc/g810
cp profile1 /etc/g810


SystemD unit in Arch Linux (For set profile at boot time) :
cat << EOF > /usr/lib/systemd/system/g810-led.service
[Unit]
Description=Set Logitech G810 Led Profile

[Service]
ExecStart=/bin/g810-led /etc/g810/profile1

[Install]
WantedBy=multi-user.target
EOF

systemctl start g810-led
systemctl enable g810-led
