# fix-fullload-oom

```bash
sudo mkdir -p /etc/systemd/oomd.conf.d
sudo tee /etc/systemd/oomd.conf.d/99-override.conf << 'EOF'
[OOM]
DefaultMemoryPressureLimit=90%
DefaultMemoryPressureDurationSec=120s
EOF

sudo systemctl restart systemd-oomd

oomctl   
```

# Revert

```bash
sudo rm /etc/systemd/oomd.conf.d/99-override.conf
sudo systemctl restart systemd-oomd   
```


