# Cards

## 1 PSICK Installation

#### TOW 1 - https://www.example42.com/2017/01/01/one-liner-to-install-puppet4/
#### Tags: setup
#### Attack: 1 - Defense: 2 - Cost: 1
#### Cat: TRY

Try PSICK anytime on your on Linux or Mac with:

    git clone https://github.com/example42/psick
    cd psick

PSICK needs Puppet you can install it, using upstream repos, with:

    bin/puppet_install.sh
    bin/puppet_install4.sh # Installs Puppet 4

Next install necessary gems and modules listed in Puppetfile

    bin/puppet_setup.sh

Good! Ready for next steps!

## 2 TRY Play with PSICK on Vagrant
TOW 19 - https://www.example42.com/2017/05/08/a-psick-vagrant-experience/
Tags: setup, vagrant

Setup PSICK as in Card=>1 then install Vagrant with:

    bin/vagrant_setup.sh

Move to any of the available Vagrant environments:

    cd vagrant/environment/ostest

Show available Vagrant boxes and start one of them

    vagrant status
    vagrant up centos7.ostest.psick.io

VM is provisioned using PSICK's default Puppet code and data.


## 3 DEVEL Build your Puppet control-repo
TOW 19 - https://www.example42.com/2017/05/08/a-psick-vagrant-experience/

## 4 INFO The lab environment

## 5 INFO Understand psick control-repo
2 https://www.example42.com/2017/01/09/anatomy-of-a-puppet-control-repo/

## 6 TRY Test your Puppet code on any OS https://www.example42.com/2017/09/04/testing-any-role-on-any-os-with-a-psick-control-repo/
## 7 MOD Classification with psick module
## 7 MOD Base profiles
## 7 MOD TP profiles
## 7 MOD Hardened setup
## 8 TRY tp commands
## 8 TRY Docker

## XX DEVEL Setup your develstation
26 https://www.example42.com/2017/06/26/psick-developer-environment-setup/

## XX DEVEL Setup your develstation

## XX DEVEL Hiera design
3 https://www.example42.com/2017/01/16/the-optimal-hiera-yaml/

## XX PROD Puppet server setup
21 https://www.example42.com/2017/05/22/automated-puppet-infrastructure-setup/

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

## XX MOD Base - Manage Users
## XX MOD Configuring Windows
## XX MOD Psick and bolt https://www.example42.com/2017/10/23/bolt_and_tasks_with_psick/

