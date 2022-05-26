# RouteMon

RouteMon is a python daemon that runs on Arista EOS to monitor route changes and perform actions when a  change is noticed.

## Installation

1. Download latest release from Release page
2. Install swix file
    #### Manually
    1. ```copy scp:user@10.1.2.3/home/user/RouteMon-x.x-x.noarch.swix extension:```
    2. ```extension RouteMon-x.x-x.noarch.swix```
    #### CVP
    1. Create image bundle under Provisioning > Image Management
    2. Upload RouteMon-x.x-x.noarch.swix and add to image bundle
    3. Use Provisioning > Network Provisioning to assign image bundle to devices
    * TODO: Add screenshots of CVP process
3. *Optional -* Configure flash:RouteMon.cmd with desired show commands
    * ```bash nano /mnt/flash/RouteMon.cmd```
    * TODO: Describe CVP process for pushing RouteMon.cmd changes to all devices

## Usage

Configure a daemon on the switch with the vrf and route to monitor
```python
daemon RouteMonDefault0
   exec /mnt/flash/RouteMon
   option route value 0.0.0.0/0
   option vrf value default
   no shutdown
!
```

## Contributing
Pull requests are welcome for this project. For major changes please open an issue first to discuss.
