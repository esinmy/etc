# Size of a directory

List top 10 most heavy folders:

```
sudo du -h | sort -n -r | head -n 10
```
s - Display only the total size of the specified directory, do not display file size totals for subdirectories.
Reference:
- [How to Get the Size of a Directory in Linux](https://linuxize.com/post/how-get-size-of-file-directory-linux/)
- [Linux commands: du and the options you should be using](https://www.redhat.com/sysadmin/du-command-options)


# Services
List All Units in systemctl:
```
systemctl --type=service
```

Reference:
- [List All Units in systemctl](https://www.tecmint.com/list-all-running-services-under-systemd-in-linux/)