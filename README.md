# Vagrant rails box with Ansible
Ready to use vagrant box with all the typical dependencies that most Ruby on Rails projects need.
## Whats inside?
> Ubuntu 14.04 64-bit

> Ruby  2.1.2 + Rails 4.2 - versions defined in config files

> rbenv

> Postgres 9.3

> Node.js

> Mailcatcher

> Cool dev stuff: oh-my-zsh, htop, tig


### Version
1.0

### How to

1. Install Vagrant and Ansible
2. In catalog run: 'vagrant up' and wait some time...
3. If something goes wrong use: 'vagrant provision'
4. type: vagrant ssh and go to makerschannel
5. generate your app, bundle install and run 'rails s'
6. For development use: makerschannel.dev:3011
7. Have fun and built another awesome app :)

License
----

MIT
