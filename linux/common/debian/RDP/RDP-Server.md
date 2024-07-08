Install xrdp server:

```bash
sudo apt install xrdp -y
```

Check status:

```bash
sudo systemctl status xrdp
```

Enable and start xrdp if not enabled or started:

```bash
sudo systemctl enable --now xrdp
```