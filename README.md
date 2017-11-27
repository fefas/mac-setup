# My personal Mac setup

As we sometimes have to format our computer, I've decided to create this
repository that aims to automate my Mac setup process and let my life less
boring.

> **Recommended:** after formatting, it is better to update the OS throught the
> App Store application before running the steps.

## Steps

Follow the steps to get your Mac set up:

1. Run the `bootstrap` script using the following command on the Terminal and it
   will install XCode, Homebrew, Ansible and Git and will clone this repository:

   ```shell
   $ sh -c (curl -fsSL https://raw.githubusercontent.com/fefas/mac-setup/master/bootstrap)
   ```

2. After that, the script `install` will run the
   [install.yml](ansible/install.yml) playbook:

   ```shell
   $ cd ~/Downloads/mac-setup
   $ ./install
   ```

3. This is a manually step for configuring desktop applications that can not be
   automated (or are very hard to), like _1Password_, _Dropbox_ and so on. You
   may want to do it before the following steps...

4. Import the RSA keys from external USB drive (requires USB drive pluged):

   ```shell
   $ cd ~/Downloads/mac-setup
   $ ./import-keys
   ```

5. Finally, the environment has to be configured:

   ```shell
   $ cd ~/Downloads/mac-setup
   $ ./configure
   ```

## TODO

What I still want to automate:

* [ ] Monitor
  - [ ] Screen resolution
  - [ ] Night Shift
* [ ] Dock
  - [ ] Add the applications I use and remove the other ones
* [ ] Configure iTerm2
* [ ] Wallpapers
* [ ] ...
