# Droid Module: droid/user

Create Unix user accounts and enable SSH key authentication. For more
information on Droid, please see [droidphp.com](http://droidphp.com).

The steps involved are:-

1. Add a standard Unix user account.
2. Create a `.ssh` directory and `authorized_keys` file with recommended access
   modes.
3. Append ssh public key data to the `authorized_keys` file.


## Assumptions

1. The platform is Debian-based.


## Limitations

1. The user is created using the `adduser` command with the user argument and
   zero options.


## Information required by the module

1. A list of one or more users to create, as follows:-

        mod_droid_user_users:
          -
            username: <string>
            homedir: <string> # path to the user's home directory (see note below)
            pubkey: <string> # SSH public key file content (or an @path to a
                             # public key file)
   Note that the `homedir` field doesn't currently affect where the user's home
   is created and so should be set to the usual debian-style home for the user.


## Optional information

None.
