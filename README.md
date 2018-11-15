# packer_nginx64

### Description 

#### List of files in the repository

- `http/preseed.cfg` - script that installs Ubuntu
- `scripts/provision.sh` - script that installs `nginx`
- `template.json` - template with code for `packer` to create the image we want

### How to use this repository.
- Clone the repository to your local computer: `git@github.com:nikcbg/packer_nginx64.git`
- Go to the cloned repo in your computer: `cd packer_nginx64`
- execute `packer init template.json` - to initiate the template for teh machine 
- execute `packer build template.json` - to start building the machine 

### TO DO:
* 
