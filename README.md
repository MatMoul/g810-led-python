# g810-led

Please check for the latest here: https://github.com/MatMoul/g810-led

Linux led controller for the Logitech G810 Keyboard

This is a first short... Wait for a more polished version...

At this time, work only as root or with sudo.

Dependencies :
- Python2
- pyusb make sure you install PyUSB v1.0.0:

On Debian / Ubuntu derivatives:

apt-get install python-pip

pip install pyusb # (PyUSB-1.0.0.tar.gz)

Use :<br />
g810-led {key} {color}<br />
g810-led {profilefile}

Samples :<br />
g810-led F1 ff0000<br />
g810-led /etc/g810-led/profile1<br />
g810-led sampleprofile1
g810-led sampleprofile2


Install (Copy g810-led in /usr/bin) :<br />
cp g810-led /usr/bin


Profiles :<br />
mkdir /etc/g810-led<br />
cp sampleprofile1 /etc/g810-led/profile


SystemD unit in Arch Linux (For set profile at boot time) :<br />
cat << EOF > /usr/lib/systemd/system/g810-led.service<br />
[Unit]<br />
Description=Set Logitech G810 Led Profile

[Service]<br />
ExecStart=/bin/g810-led /etc/g810-led/profile

[Install]<br />
WantedBy=multi-user.target<br />
EOF

systemctl start g810-led<br />
systemctl enable g810-led
