# CodeAlpha Network Intrusion Detection System

## Project Overview

This project demonstrates the implementation of a simple Network Intrusion Detection System (NIDS) using Snort++ on Kali Linux.

The purpose of this project is to monitor network traffic, create custom detection rules, and identify suspicious activities by generating security alerts.

## Objectives

* Install and configure Snort++.
* Monitor network traffic on a selected interface.
* Create custom IDS rules.
* Detect ICMP ping activity.
* Generate alerts for detected traffic.

## Tools and Technologies

* Kali Linux
* Snort++ 3.12.2.0
* VMware
* Snort Rules

## Network Interface

The monitored network interface:

```
eth0
```

## Custom Detection Rule

A custom ICMP detection rule was created in:

```
/etc/snort/rules/local.rules
```

Rule:

```
alert icmp any any -> any any (msg:"ICMP Ping Detected"; sid:1000001; rev:1;)
```

This rule detects ICMP packets such as ping requests and generates an alert.

## Running Snort

Snort was started using the following command:

```
sudo snort -c /etc/snort/snort.lua -R /etc/snort/rules/local.rules -i eth0 -A alert_fast
```

## Testing the IDS

A ping test was performed to generate ICMP traffic:

```
ping -c 4 8.8.8.8
```

## Detection Result

Snort successfully detected ICMP traffic and generated alerts:

```
[1:1000001:1] "ICMP Ping Detected"
```

Example:

```
{ICMP} 192.168.141.135 -> 142.251.208.142
```

## Project Structure

```
CodeAlpha_NetworkIDS
│
├── README.md
├── local.rules
└── screenshots
    └── snort_alert.png
```

## Conclusion

This project shows the basic concepts of Network Intrusion Detection Systems and demonstrates how Snort++ can be used to monitor network traffic and detect suspicious activities using custom rules.

## Author

CodeAlpha Cyber Security Internship Project
