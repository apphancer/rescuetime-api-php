### Getting Started (Vagrant Setup)

1. Install Git
2. Install VirtualBox: https://www.virtualbox.org/wiki/Downloads
3. Install Vagrant: http://www.vagrantup.com/ (version 1.2.2+ or later)
4. Open a terminal
5. Clone the project: `git clone https://github.com/borivojevic/rescuetime-api-php.git`
6. Enter the project directory: `cd rescuetime-api-php`

### Using Vagrant

When you're ready to start working, boot the VM:

```
vagrant up
```

The first time you do this Vagrant will have to download and install VM image which can take ~15 minutes or more depending on internet connection speed.

When machine boots up ssh into it by typing:

```
vagrant ssh
# password: vagrant
```

**On Windows**: Use : ssh vagrant@127.0.0.1 -p 2222


### Making Changes

The application code is found in vagrant home directory at /home/vagrant

The very first time you'll have to install application dependencies:

```
sudo composer self-update
composer install
```

Basic Workflow: Run vagrant machine >> Update repository >> Edit >> Send GitHub pull request

1. Update repository
 1. `cd /home/vagrant`
 1. `git checkout master`
 1. `git pull`
1. Make changes to RescueTime API
 1. `cd /home/vagrant`
 1. (Make changes)
 1. `git commit ...`
 1. (Make sure all tests pass. See [testing](#testing))
 1. `git push`
1. Submit pull request to master repository
 1. [Using pull requests](https://help.github.com/articles/using-pull-requests)
 1. [Creating a pull request](https://help.github.com/articles/creating-a-pull-request)

### <a id="testing"></a>Testing

To run unit test suite type:

```
phpunit
```

To run coding standard tests type:

```
phpcs --standard=PSR2 src/
phpcs --standard=PSR2 tests/
```
