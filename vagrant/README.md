Using vagrant docker-images
=============

What's here:
* A vagrant-friendly Debian Wheezy image

To build these images:

    $ docker build -t my_image_name <path/to/Dockerfile>

To use a built image with vagrant:

    # -*- mode: ruby -*-
    # vi: set ft=ruby :

    # Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
    VAGRANTFILE_API_VERSION = "2"

    Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
      config.vm.provider "docker" do |d|
        d.image = "my_image_name"
        d.has_ssh = true # Required for provisioning and 'vagrant ssh' to work.
      end
    end

