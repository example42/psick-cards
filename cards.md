# Cards

## 1 - PSICK Installation

##### TOW 1 - https://www.example42.com/2017/01/01/one-liner-to-install-puppet4/
##### Tags: setup
##### Attack: 1 - Defense: 2 - Cost: 1
##### Cat: 2-TRY

Install PSICK by git cloning the
official repo on GitHub:

    git clone https://github.com/example42/psick
    cd psick

PSICK needs Puppet you can install it, using upstream repos, with:

    bin/puppet_install.sh

Install required gems and modules listed in Puppetfile:

    bin/puppet_setup.sh

Good! You are ready for next steps!


## 2 - Play with PSICK on Vagrant
##### TOW 19 - https://www.example42.com/2017/05/08/a-psick-vagrant-experience/
##### Tags: setup, vagrant
##### Attack: 2 - Defense: 1 - Cost: 1
##### Cat: 2-TRY

Setup PSICK as in Card[1] then install Vagrant with:

    bin/vagrant_setup.sh

Move to any of the available Vagrant environments:

    cd vagrant/environment/ostest

Show available Vagrant boxes and start one of them

    vagrant status
    vagrant up centos7.ostest.psick.io

VM is provisioned using PSICK's local Puppet code and data.


## 3 - Build your Puppet control-repo
##### TOW 19 - https://www.example42.com/2017/05/08/a-psick-vagrant-experience/
##### Tags: setup, devel
##### Attack: 3 - Defense: 2 - Cost: 2
##### Cat: 3-DEV

Create your control-repo based on PSICK (Setup in Card=>1):

    ./psick create

Choose the repo name and path.

Select 1 for a full psick clone and 2 for a minimal control-repo skeleton.

Select if you make the first commit on the new repo.

    cd /path/to/your-control-repo

Start to develop your Puppet Infrastructure!


## 4 The PSICK lab environment
##### TOW 
##### Tags: demo
##### Attack: 4 - Defense: 1 - Cost: 2
##### Cat: 1-INF

Check http://lab.psick.io for a LIVE, PSICK based lab environment
with Puppet Enteprise, GitLab integration and various managed
services on different Vagrant VMs.

The vagrant environment in under:

    vagrant/environments/lab

The relevant Hiera data is in (in Hierarchical order):

    hieradata/nodes/$hostname.lab.psick.io.yaml
    hieradata/role/$role.yaml
    hieradata/zone/lab.yaml
    hieradata/common.yaml


## 5 PSICK control-repo layout

##### TOW 2 - https://www.example42.com/2017/01/09/anatomy-of-a-puppet-control-repo/
##### Tags: basics
##### Attack: 1 - Defense: 4 - Cost: 2
##### Cat: 1-INF

Standard Puppet control-repo dirs and files:

  - **manifests/** - The main manifests directory
  - **hieradata/** - The dir with Hiera data files
  - **Puppetfile** - The file with the list of extra modules to deploy
  - **modules/** - The dir where modules are deployed 
  - **environment.conf** - The Environment configuration file
  - **hiera.yaml** - The Environment Hiera configuration file

PSICK additional dirs:

  - **bin/** - Scripts and tools used in development and CI
  - **docs/** - PSICK docs
  - **vagrant/** - Several different Vagrant environments
  - **fabfile/** - Fabric scripts
  - **spec/** - Control repo spec tests
  - **.gitlab-ci.yaml**, **Jenkinsfile** - CI automation configs


## 6 Test your Puppet code on any OS

##### TOW 36 - https://www.example42.com/2017/09/04/testing-any-role-on-any-os-with-a-psick-control-repo/ 
##### Tags: test, vagrant
##### Attack: 1 - Defense: 4 - Cost: 2
##### Cat: 3-DEV


Run the VMs with your OS of choice:

    cd vagrant/environment/ostest
    vagrant up <os>.ostest.psick.io

Check what role is linked by the special ostest.yaml symlink

    cd ../../../
    ls -l hieradata/role/ostest.yaml

Change the role to test on your VMs:

    hieradata/role/vpn.yaml hieradata/role/ostest.yaml

Run Puppet on your VMs testing the new role

    cd vagrant/environment/ostest
    vagrant provision 


## 7 The psick module

Psick is composed of:

  - a sample control-repo
  - a reusable Puppet module

Install the Puppet module with one of:

    puppet module install example42-psick
    git clone https://github.com/example42/puppet-psick

Psick module provides:

  - Structured and ordered classification
  - Base profiles for common OS management operations
  - TP profiles for common applications


## 8 MOD Classification with psick module

## 9 OPS tp commands

## 10 OPS Docker

## 11 PROD Puppet server setup
21 https://www.example42.com/2017/05/22/automated-puppet-infrastructure-setup/

## 12 PROD Puppet CI

PSICK supports CI/CD of Puppet code using different tools.

  - Jenkins pipeline is configured in ```Jenkinsfile```
  - GitLab CI is configured in ```.gitlab-ci.yml```
  - Travis integration is configured in ```.travis.yaml```

In many CI steps are used scripts under the ```bin/``` dir.

Puppet CI involve:

  - lint, syntax, unit, integrations tests.
  - Puppet code deployment and progressive rollout
  - Canary runs in noop and no-noop mode
  - Git commit automatic feedback and docs generation


## XX DEVEL Setup your develstation
26 https://www.example42.com/2017/06/26/psick-developer-environment-setup/

## XX DEVEL Hiera design
3 https://www.example42.com/2017/01/16/the-optimal-hiera-yaml/

## XX PROD Puppet Enterprise Gitlab Integration

## XX PROD OSS setup with Jenkins

## XX PROD Noop operations
52 https://www.example42.com/2017/12/27/noop-no-noop-and-the-path-to-safe-puppet-deployments/


## XX INFO Control repo documentation
25 https://www.example42.com/2017/06/19/control-repo-documentation/

## XX INFO Class parameters on Hiera
38 https://www.example42.com/2017/09/18/when-to-place-data-in-hiera/

## XX INFO Hiera 5
16 https://www.example42.com/2017/04/17/hiera-5/

## XX MOD TP profiles
## XX MOD Hardened setup
## XX MOD Base profiles
## XX MOD Base - Manage Users
## XX MOD Configuring Windows
## XX MOD Psick and bolt https://www.example42.com/2017/10/23/bolt_and_tasks_with_psick/

## OPS Fabric operations
## OPS Bolt operations
## OPS Puppet deployment
