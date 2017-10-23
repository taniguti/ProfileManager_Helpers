# ProfileManager_Helpers
Small tools for Apple ProfileManager deployment.

# Common configuration file
- pms_tool.conf

    configuration file which used by following scripts.

# Scripts
## Device group handling
- pms_add_device_to_devicegroup

    Add a device to a device group.
```
./pms_add_device_to_devicegroup groupname HWSerialNumber
```
- pms_auto_add_device_to_group
```
./pms_auto_add_device_to_group
```
It will looking for the file, '/tmp/order.txt'.
If it will be find and read it and call pms_add_device_to_devicegroup.
'/tmp/order.txt' must be like this.
```
# hostname,HWSerialNumber,groupname
mac01,HW1234567MAC,DEVGROUP01
mac02,HW1234568MAC,DEVGROUP01
mac02,HW1234568MAC,DEVGROUP02
```

- pms_get_device_id

- pms_get_device_info

- pms_get_device_name

- pms_get_devicegroup_id

- pms_get_devicegrouplist

- pms_get_devicelist

- pms_get_devicemembers_of_group

- pms_delete_device_from_devicegroup


## device manager service handling
- pms_auto_restart

- pms_full_restart

- pms_check_apspd_apsd_process

- pms_log_ctrl

## Postgres DB handling
- pms_db_backup

    Creaet data base backup archive.

- pms_get_dblist

    Show list of databases.

- pms_get_tablelist

    Show list of tables in databse "devicemgr_v2m0".
