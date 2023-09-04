# Create a User with Limited Permissions on Red Hat Enterprise Linux (RHEL) 7.9

This tutorial will guide you through the steps to create a user with limited permissions in RHEL 7.9. We will create a user named `user1` and add it to a group named `workshop`.

## Prerequisites

- Log in as `root` or a superuser with `sudo` access.

## Steps

### Step 1: Create a Group (if it doesn't exist)

If the `workshop` group doesn't already exist, create it with the following command:

```bash
groupadd workshop
```

To verify that the group was created successfully, run:

```bash
getent group workshop
```

### Step 2: Create the User

Create a new user named `user1` and add it to the `workshop` group using the following command:

```bash
useradd -G workshop user1
```

By default, this user will have limited permissions and will be a member of its own primary group (`user1`) as well as the secondary group `workshop`.

### Step 3: Set a Password for the New User

To set a password for `user1`, use the `passwd` command:

```bash
passwd user1
```

Follow the prompts to enter and confirm the new password.

### Step 4: Verify User Creation

To ensure that `user1` was successfully added to the `workshop` group, you can use the `id` command:

```bash
id user1
```

## Conclusion

You have successfully created a user with limited permissions and added it to a group on RHEL 7.9. Feel free to adjust the permissions and groups as needed for your specific requirements.
