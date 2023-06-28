# Users

To create a new user:

```
sudo adduser new_username
```

To ensure that the user has sudo privileges, run the whoami command:
```
sudo whoami
```

# Groups

List user's groups:

```
groups new_username # or id username
```

Add user to group (for example, in the case of sudo group):
```
sudo usermod -aG sudo new_username
```