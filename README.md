# packer_nginx64

### Purpose of the repository 
- The repository should have the minimal code for creating Ubuntu xenial64 box with Packer and should also install nginx.

#### List of files in the repository

- `http/preseed.cfg` - script that installs Ubuntu.
- `scripts/provision.sh` - script that installs `nginx`.
- `template.json` - template with code for `packer` to create the image we want.
- `test/integration/default/check_pkg.rb` - script that isntalls various packages for `ruby` development environmnet.
- `test/integration/default/gen.sh` - script that installs `wget` package
- `.gitignore` - which files and directories to ignore
- `.kitchen.yml` - testing framework used by `ruby`
- `Gemfile` - used for `ruby` dependencies

### How to use this repository.
- Install `virtualbox` by following this [instructions](https://www.virtualbox.org/wiki/Downloads)
- Install `vagrant` by following this [instructions](https://www.vagrantup.com/docs/installation/)
- Install `packer` by following this [instructions](https://www.packer.io/intro/getting-started/install.html).
- Clone the repository to your local computer: `git@github.com:nikcbg/packer_nginx64.git`.
- Go to the cloned repo in your computer: `cd packer_nginx64`.
- execute `packer validate template.json` - validates `template.json` file, after executing the command it shoudl return `Template validated successfully` message. 
- execute `packer build template.json` - to start building the virtual machine. 
- after that you should see this message `nginx64-vbox: 'virtualbox' provider box: nginx64-vbox.box` which means that the VM box was build successfull.
- execute `vagrant box list` – shows list of `vagrant` boxes
- execute `vagrant box add --name nginx64 nginx64-vbox.box`  - add the newly created `packer` box 
- execute `vagrant init nginx64` – create Vagrantfile 
- next you execute `vagrant up` command to power up the VM.
- then execute `vagrant ssh` to log in to the VM.
- execute `exit` to exit the VM to test with `kitchen`

### Setting up `ruby` environment
- before testing with `kitchen` you need to install and prepare `ruby` environment 
- execute `brew install rbenv` - installs `ruby` environment
- execute `echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bash_profile` - accessing `ruby` management tool
- execute `source ~/.bash_profile` to reload `bash` profile 
- execute `rbenv init` to enable `rbenv` in `shell`
- execute `rbenv install 2.3.1` to install `ruby` 
- execute `rbenv local 2.3.1` to change to the `ruby` version
- execute `rbenv versions` to make sure you have the correct version
- execute `gem install bundler` to install `gem`whuch is package manager for `ruby` 
- execute `bundle install` to install all `gem` dependencies

### Commands needed to test with `kitchen`
- execute `bundle exec kitchen list` to list `kitchen` instances 
- execute `bundle exec kitchen converge` to create `kitchen` environment 
- execute `bundle exec kitchen verify` command to execute `kitchen` test
- execute `bundle exec kitchen destroy` to destroy `kitchen` environment 

### TO DO:
- Check if `nginx` is installed on the xenial64 box.
