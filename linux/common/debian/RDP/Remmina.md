## Add Remmina-Next PPA


```zsh
sudo apt-add-repository ppa:remmina-ppa-team/remmina-next
sudo apt update
```

## Install Remmina with plugins
Then install the following packages:

```zsh
sudo apt-get install libfreerdp-plugins-standard remmina remmina-plugin-rdp
```

To list available plugins execute the following:

```zsh
sudo apt search remmina-plugin
```

The output will look like this:

```zsh
s3tupw1zard@manuel-laptop:~$ sudo apt search remmina-plugin
p   remmina-plugin-exec             - GTK+-Client für Sitzungen auf entfernten R
p   remmina-plugin-kiosk            - Kiosk plugin for Remmina                  
p   remmina-plugin-kwallet          - KWallet plugin for Remmina                
p   remmina-plugin-python           - Python support for Remmina                
i A remmina-plugin-rdp              - RDP plugin for Remmina                    
i A remmina-plugin-secret           - Secret plugin for Remmina                 
p   remmina-plugin-spice            - Spice plugin for Remmina                  
i A remmina-plugin-vnc              - VNC plugin for Remmina                    
p   remmina-plugin-www              - WWW plugin for Remmina                    
p   remmina-plugin-x2go             - X2Go plugin for Remmina                   
s3tupw1zard@manuel-laptop:~$ 
```