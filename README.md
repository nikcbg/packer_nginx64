# packer_nginx64

### Description 

#### List of files in the repository

- `http/preseed.cfg` - script that installs Ubuntu
- `scripts/provision.sh` - script that installs `nginx`
- `template.json` - template with code for `packer` to create the image we want

### How to use this repository.
- Install `packer` by following this [instructions](https://www.packer.io/intro/getting-started/install.html)
- Clone the repository to your local computer: `git@github.com:nikcbg/packer_nginx64.git`
- Go to the cloned repo in your computer: `cd packer_nginx64`
- execute `packer validate template.json` - validates `template.json` file, after executing the command it shoudl return `Template validated successfully` message 
- execute `packer build template.json` - to start building the virtual machine 

### TO DO:

