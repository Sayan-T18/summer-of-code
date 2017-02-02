# Idea: AOSP Firewall / dynamic internet permission

Extend AOSP by a per-app Firewall, allowing to restrict internet access, including a user-friendly UI.

## Background

Since Android 6.0, the user is able to deny applications the permission to access privacy-sensitive
information on the device like contact database or device identifiers. However, in the same step,
the permission to access the internet (e.g. to upload sensitive information or track the user) was
hidden from the installation UI and there is no way to restrict internet access to applications.

Many users seek a certain level of privacy. There are root-based solutions to block network access to
applications, but they often lack a proper integration with the Android internal Firewall (which is
used to restrict internet access to background apps if requested). 
Some users also block specific hosts they deem to infringe their privacy by adding rules to the hosts-file
located at `/system/etc/hosts`. This has become so popular that custom ROMs started to preserve this file
over updates of the operating system (which would normally reset it because `/system`-partition is meant
to be read-only.

## Expected Results

As part of this project, the student should develop a firewalling solution that is deeply integrated with
the AOSP operating system. This might include:

- Ability to "deny the internet permission", by blocking all incoming and outgoing packets to the app,
  provided directly in the permission UI of the Android system settings.
- DNS blocking rules (blacklist), that globally or per-application block certain hosts by not
  resolving them or misleadingly resolve to `127.0.0.1`.
- App specific rules (whitelist), that restrict access to certain hosts. ex: allow the Twitter app to
  access hosts from Twitter, but nothing else. This could further be extended to let apps define a list
  of hosts they require access to (via a `meta-data` block in the `AndroidManifest.xml`) and restrict
  to this list if present, allowing the user to analyze the list of contacted hosts before install.
- (Properly protected) extended API for applications to create new firewall rules. ex: a privacy app
  should be able to update the DNS blocking rules regularly or the Tor client should be able to create
  a rule that restricts internet access in a way that all traffic must be routed through the Tor network.

Submitting the source code for review to custom ROMs or upstream and/or passing the review is a plus,
but not a requirement.

## Required Skills

This project will require understanding of the following, but missing knowledge can be gathered in the
community bonding period:

- Android Java development
- Basic C/C++ development
- Background knowledge of android service (and their management)
- Firewall on Linux (iptables)

## Mentor(s)

MaR-V-iN

## Difficulty Level

Medium / Moderate

## XDA Handle

MaR-V-iN
