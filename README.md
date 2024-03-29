# ansible-role-logrotate

Ansible role to manage basic log rotation with Logrotate.

## Usage

```yaml
- hosts: all
  tasks:
    - include\_role:
        name: logrotate
      vars:
      # ...
```
  
### Available variables

| Name | Description | Type | Default | Required |
|------|-------------|:----:|:-----:|:-----:|
| logs\_dir\_path | The path of the directory where to rotate logs | string | | yes |
| logs\_path\_pattern | The pattern to match log files in 'logs\_dir\_path' | string | *.log | no |
| logrotate\_file\_name | The name of the logrotate configuration file | string | | yes |
| rotation\_interval | The interval of the log rotation | string | daily | no |
| retention\_period | Interval count of logs retention | int | 7 | no |
| compress | Old versions of log files are compressed with gzip | bool | yes | no |
| copytruncate | Truncate the original log file in place after creating a copy | bool | yes | no |
| create | Immediately after rotation the log file is created | bool | no | no |
| create_mode | The mode for the created log file in octal | string | | no |
| create_owner | The user name who will own the created log file | string | | no |
| create_group | The group the created log file will belong to | string | | no |
| delay\_compress | Postpone compression of the previous log file to the next rotation cycle | bool | no | no |
| missingok | If the log file is missing, go on to the next one without issuing an error message | bool | yes | no |
| notifempty | Do not rotate the log if it is empty | bool | yes | no |
| rotation\_user | The user that will rotate the logs | string | root | no |
| rotation\_group | The group that will rotate the logs | string | root | no |
| sharedscripts | The scripts are only run once, instead of for each log which is rotated | bool | yes | no 
| postrotate_script | The script that will be executed after the log file is rotated | string | | no |
