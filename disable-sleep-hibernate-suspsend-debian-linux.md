Taken from: https://gitlab.com/-/snippets/2515869

# Disable Sleep, Hibernate, Suspend on Debian Linux

The following describes how you can disable suspended state without having to login to your graphical user interface.

## Disable Suspend via Terminal

Issue the following command to disable suspend state on Debian Linux:

```bash
sudo systemctl mask sleep.target suspend.target hibernate.target hybrid-sleep.target
```

## Check the Status of Suspend via Terminal

Issue the following command to verify the status of suspend state modes on Debian Linux:

```bash
sudo systemctl status sleep.target suspend.target hibernate.target hybrid-sleep.target
```

A system with suspend state disabled should show the following:

```bash
○ sleep.target
     Loaded: masked (Reason: Unit sleep.target is masked.)
     Active: inactive (dead)

Mar 17 11:28:58 nosreme systemd[1]: Reached target sleep.target - Sleep.
Mar 17 11:30:13 nosreme systemd[1]: Stopped target sleep.target - Sleep.
Mar 17 11:50:13 nosreme systemd[1]: Reached target sleep.target - Sleep.
Mar 17 11:55:06 nosreme systemd[1]: Stopped target sleep.target - Sleep.

○ suspend.target
     Loaded: masked (Reason: Unit suspend.target is masked.)
     Active: inactive (dead)

Mar 17 11:30:13 nosreme systemd[1]: Reached target suspend.target - Suspend.
Mar 17 11:30:13 nosreme systemd[1]: Stopped target suspend.target - Suspend.
Mar 17 11:55:06 nosreme systemd[1]: Reached target suspend.target - Suspend.
Mar 17 11:55:06 nosreme systemd[1]: Stopped target suspend.target - Suspend.

○ hibernate.target
     Loaded: masked (Reason: Unit hibernate.target is masked.)
     Active: inactive (dead)

○ hybrid-sleep.target
     Loaded: masked (Reason: Unit hybrid-sleep.target is masked.)
     Active: inactive (dead)
```

You may or may not find a smaller/larger/non-existing log of system suspensions - Note that accordingly for your system.

## Enable Suspend via Terminal
Issue the following command to re-enable suspend state on Debian Linux:

```bash
sudo systemctl unmask sleep.target suspend.target hibernate.target hybrid-sleep.target
```
