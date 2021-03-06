+++
date = "2017-04-15T14:39:04+02:00"
title = "User Management"
url = "user-management"

[menu.install]
  weight = 3
  identifier = "user-management"
  parent = "install_access"
+++

You can manually manage user registration using the command line utility. Please see the command line documentation for installing and configuring the command line utility.

Use the `ls` command to list all active users:

```nohighlight
drone user ls
```

Use the `add` command to add users to the system by login:

```nohighlight
drone user add octocat
```

Use the `rm` command to remove users from the system by login:

```nohighlight
drone user rm octocat
```

Please note that only drone administrators can manage users. Please see the below example to configure one or many administrators, separated by a comma, using the designated environment variable.

```diff
services:
  drone-server:
    image: drone/drone:{{% version %}}
    environment:
+     - DRONE_ADMIN=janedoe,johnsmith
```
