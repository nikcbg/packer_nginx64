# packer_nginx64

### Purpose of the repository 
- The repository should have the minimal code for creating Ubuntu xenial64 box with Packer and should also install nginx.

#### List of files in the repository

- `http/preseed.cfg` - script that installs Ubuntu.
- `scripts/provision.sh` - script that installs `nginx`.
- `template.json` - template with code for `packer` to create the image we want.

### How to use this repository.
- Install `packer` by following this [instructions](https://www.packer.io/intro/getting-started/install.html).
- Clone the repository to your local computer: `git@github.com:nikcbg/packer_nginx64.git`.
- Go to the cloned repo in your computer: `cd packer_nginx64`.
- execute `packer validate template.json` - validates `template.json` file, after executing the command it shoudl return `Template validated successfully` message. 
- execute `packer build template.json` - to start building the virtual machine. 
- after that you should see this message `nginx64-vbox: 'virtualbox' provider box: nginx64-vbox.box` which means that the VM box was build successfull.
- next you execute `vagrant up` command to power up the VM.
- then execute `vagrant ssh` to log in to the VM.
- you can delete the VM if you do not need it by executing `vagrant destroy`.

### TO DO:
- Check if `nginx` is running.
