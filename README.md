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
```
$ ./pms_db_backup
-rw-r--r--  1 ladmin  wheel  1101755 Oct 24 01:20 /var/tmp/devicemgr_v2m0_pg_dump_20171024-012013.gz
$
```

- pms_get_dblist

    Show list of databases.
```
$ ./pms_get_dblist
                                   List of databases
      Name      |   Owner    | Encoding | Collate | Ctype |      Access privileges      
----------------+------------+----------+---------+-------+-----------------------------
 devicemgr_v2m0 | _devicemgr | UTF8     | C       | C     | =T/_devicemgr              +
                |            |          |         |       | _devicemgr=CTc/_devicemgr  +
                |            |          |         |       | devicemgrd=Tc/_devicemgr   +
                |            |          |         |       | webadmin=Tc/_devicemgr     +
                |            |          |         |       | deviceservice=Tc/_devicemgr+
                |            |          |         |       | dmscepservice=Tc/_devicemgr
 postgres       | _devicemgr | UTF8     | C       | C     |
 template0      | _devicemgr | UTF8     | C       | C     | =c/_devicemgr              +
                |            |          |         |       | _devicemgr=CTc/_devicemgr
 template1      | _devicemgr | UTF8     | C       | C     | =c/_devicemgr              +
                |            |          |         |       | _devicemgr=CTc/_devicemgr
(4 rows)
```

- pms_get_tablelist

    Show list of tables in databse "devicemgr_v2m0".
```
    $ ./pms_get_tablelist
                                     List of relations
 Schema |                       Name                       |       Type        |   Owner    
--------+--------------------------------------------------+-------------------+------------
 public | _scmv_depth_order                                | materialized view | _devicemgr
 public | _scmv_rel_deps                                   | materialized view | _devicemgr
 public | _scmv_rel_deps_flat                              | materialized view | _devicemgr
 public | _scv_invalidate_matviews_by_dependent_relations  | view              | _devicemgr
 public | _scv_our_mvs                                     | view              | _devicemgr
 public | _scv_refresh_mvs_by_dep_rels                     | view              | _devicemgr
 public | _scv_refresh_mvs_by_depth_order                  | view              | _devicemgr
 public | _scv_refresh_mvs_by_rels                         | view              | _devicemgr
 public | _view_all_user_groups_users_complete             | view              | _devicemgr
 public | abstract_asm_library_items                       | table             | _devicemgr
 public | abstract_asm_users                               | table             | _devicemgr
 public | active_locales                                   | table             | _devicemgr
 public | active_locales_id_seq                            | sequence          | _devicemgr
 public | app_configurations                               | table             | _devicemgr
 public | asset_metadata                                   | table             | _devicemgr
 public | asset_metadata_id_seq                            | sequence          | _devicemgr
 public | assets                                           | table             | _devicemgr
 public | assets_id_seq                                    | sequence          | _devicemgr
 public | assets_localized_data                            | table             | _devicemgr
 public | assets_localized_data_id_seq                     | sequence          | _devicemgr
 public | auto_join_profile_usage                          | table             | _devicemgr
 public | auto_join_profile_usage_id_seq                   | sequence          | _devicemgr
 public | auto_join_profiles                               | table             | _devicemgr
 public | auto_join_profiles_device_groups                 | table             | _devicemgr
 public | auto_join_profiles_device_groups_id_seq          | sequence          | _devicemgr
 public | auto_join_profiles_id_seq                        | sequence          | _devicemgr
 public | certificates                                     | table             | _devicemgr
 public | certificates_id_seq                              | sequence          | _devicemgr
 public | class_beacon_seq                                 | sequence          | _devicemgr
 public | client_certificates                              | table             | _devicemgr
 public | client_certificates_id_seq                       | sequence          | _devicemgr
 public | completed_tasks                                  | table             | _devicemgr
 public | data_files                                       | table             | _devicemgr
 public | db_deferred_int_functions                        | table             | _devicemgr
 public | db_deferred_int_functions_1                      | table             | _devicemgr
 public | db_deferred_int_functions_2                      | table             | _devicemgr
 public | db_deferred_int_functions_id_seq                 | sequence          | _devicemgr
 public | db_deferred_void_functions                       | table             | _devicemgr
 public | db_deferred_void_functions_1                     | table             | _devicemgr
 public | db_deferred_void_functions_2                     | table             | _devicemgr
 public | db_deferred_void_functions_id_seq                | sequence          | _devicemgr
 public | db_notifications                                 | table             | _devicemgr
 public | db_notifications_id_seq                          | sequence          | _devicemgr
 public | db_notifications_p1                              | table             | _devicemgr
 public | db_notifications_p2                              | table             | _devicemgr
 public | db_notifications_p3                              | table             | _devicemgr
 public | deleted_media                                    | table             | _devicemgr
 public | deleted_objects                                  | table             | _devicemgr
 public | device_enrollment_settings                       | table             | _devicemgr
 public | device_enrollment_settings_id_seq                | sequence          | _devicemgr
 public | device_group_memberships                         | table             | _devicemgr
 public | device_groups                                    | table             | _devicemgr
 public | device_groups_devices                            | table             | _devicemgr
 public | devices                                          | table             | _devicemgr
 public | devices_local_users                              | table             | _devicemgr
 public | devices_local_users_id_seq                       | sequence          | _devicemgr
 public | dm_schema_information                            | table             | _devicemgr
 public | dynamic_attributes_defaults                      | table             | _devicemgr
 public | dynamic_attributes_defaults_id_seq               | sequence          | _devicemgr
 public | ebooks                                           | table             | _devicemgr
 public | edu_classes                                      | table             | _devicemgr
 public | edu_classes_device_groups                        | table             | _devicemgr
 public | edu_classes_unused_beacon_ids                    | table             | _devicemgr
 public | edu_classes_user_groups                          | table             | _devicemgr
 public | edu_classes_users                                | table             | _devicemgr
 public | enterprise_apps                                  | table             | _devicemgr
 public | installed_applications                           |
 :
```
