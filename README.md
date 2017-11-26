# My personal mac setup

As we sometimes have to format our computer, I decided to automated this
process and let my life less boring.

> That is my personal Mac set up and there are a lot of like this one outside
> there.

## Running it

> **Recommended:** after formatting, it is better first to update the OS
> throught the App Store application.

Follow the next steps to get your MacBook set up.

1. Run the `bootstrap` script using the following command on the Terminal and it
   will install XCode, Homebrew, Ansible and Git and will clone this repository:

   ```shell
   $ curl -fsSL https://raw.githubusercontent.com/fefas/mac-setup/master/bootstrap | /bin/sh 
   ```

2. After that, the script `install` will run the
   [install.yml](ansible/install.yml) playbook:

   ```shell
   $ cd ~/Downloads/mac-setup
   $ ./install
   ```

3. This is a manually step for configuring desktop applications that can not be
   automated, like _1Password_, _Dropbox_ and so on. I may want do it before the
   following steps...

4. Import the RSA and GPG keys from external USB drive (do I have to write that
   the USB drive MUST be pluged?):

   ```shell
   $ cd ~/Downloads/mac-setup/ansible
   $ ansible-playbook -i hosts.ini import-keys.yml
   ```

5. Finally, the environment has to be configured:

   ```shell
   $ cd ~/Downloads/mac-setup/ansible
   $ ansible-playbook -i hosts.ini configure.yml
   ```
