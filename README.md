goss-cis-benchmark
===

This project validates level 1 CIS Controls Benchmarks with [Goss](https://github.com/aelsabbahy/goss).

Currently supports versions 16.04, 18.04, and 20.04 of Ubuntu Server, as well as Amazon Linux 2.

The tests aim for validating compliance with the following CIS Benchmark versions:

  * Ubuntu 16.04 - v2.0.0
  * Ubuntu 18.04 - v2.1.0
  * Ubuntu 20.04 - v1.1.0
  * Amazon Linux 2 - v2.0.0

## Items not implemented

### Section 1

  * 1.1.19 thru 1.1.21 set appropriate options on removable media partitions:
  * 1.2 Configure Software Updates (Manual)
  * 1.4.2 Ensure bootloader password is set
  * 1.4.4 Ensure authentication required for single user mode

### Section 3

  * 3.5.1.4 Ensure loopback traffic is configured (Automated)
  * 3.5.1.5 Ensure outbound connections are configured (Manual)
  * 3.5.1.6 Ensure firewall rules exist for all open ports (Manual)
  * 3.5.1.7 Ensure default deny firewall policy (Automated)

### Section 4

  * 4.2.1.3 Ensure logging is configured (Manual)
  * 4.2.1.5 Ensure rsyslog is configured to send logs to a remote log host
  * 4.2.3 Ensure permissions on all logfiles are configured
  * 4.3 Ensure logrotate is configured (Manual)
  * 4.4 Ensure logrotate assigns appropriate permissions

### Section 5

  * 5.3.4 Ensure SSH access is limited
  * 5.4.2 Ensure lockout for failed password attempts is configured (Automated)
  * 5.5.2 Ensure system accounts are secured (Automated)
  * 5.5.5 Ensure default user shell timeout is 900 seconds or less (Automated)
  * 5.6 Ensure root login is restricted to system console (Manual)
  * 5.7 Ensure access to the su command is restricted (Automated)

### Section 6

  * 6.1.1 Audit system file permissions (Manual)
  * 6.1.13 Audit SUID executables (Manual)
  * 6.1.14 Audit SGID executables (Manual)

## Requirements

* [Goss](https://github.com/everops-mikem/goss-cis-benchmark)
* Bash

## Usage

### Clone this repository

```shell
git clone https://github.com/NeowayLabs/goss-cis-benchmark
```

### Execute all tests

```shell
cd goss-cis-benchmark
goss -g goss.yaml --vars (ubuntu_vars.yaml|amazon_linux_vars.yaml) validate
```

### Execute tests for specific CIS section
```shell
cd goss-cis-benchmark
goss -g section1.yaml --vars (ubuntu_vars.yaml|amazon_linux_vars.yaml) validate
goss -g section6.yaml --vars (ubuntu_vars.yaml|amazon_linux_vars.yaml) validate
```
