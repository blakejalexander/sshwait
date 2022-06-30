# sshwait
Do you frequently reboot devices and want to execute a command (or open a shell) once it reboots?

Then use `sshwait`!

`sshwait` is a transparent wrapper for `ssh` which will wait (indefinitely) for the host to be available before executing `ssh` itself.

## Usage
Once the host can be reached via ssh, `sshwait` will execute `ssh` with the *exact* arguments that `sshwait` was provided. This means you can reboot a device and execute a command the moment sshd comes back up.
```
sshwait user@example.com -p 10022 echo "Hello, World!"
```
or you can start an interactive shell as usual
```
sshwait user@example.com -p 10022
```
If you've already specified the user and port for `example.com` in `$HOME/.ssh/config` then you don't need to specify them. Since `sshwait` simply calls `ssh`, your local configuration will be used if you don't provide a user or port, just like normal.
```
sshwait example.com
```

## Installation
No dependencies other than `python3` are needed. To install the script, simply copy `sshwait` to somewhere on your local or global `$PATH` and ensure it's marked as executable. I personally have mine located in `$HOME/.local/bin`.
