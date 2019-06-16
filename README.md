# Hypha Co-op: Minecraft Office

This repository is for experimenting with having a Minecraft server as
an office for our nacent worker co-operative.

## :sparkles: Goals

- Experiment with [using Minecraft as a shared memory palace][memory-palace].
- Allow us to more easily meet "in person".
- Provide us a digital space to invest intention into before
  we have funds for a meatspace.
- Allow us to better understand the best-in-class voxel softare
  (proprietary Minecraft), before hopefully experimenting with the open
  source Minetest.
- Create a space where privacy concerns around visual representations
  are less tangled.

   [memory-palace]: http://johnguycollick.com/minecraft-memory-palace/

## :crystal_ball: Bluesky

- Make digital office accessible over mesh network.
- Integrate dweb protocols (e.g., ipfs) into popular server mods.
- Build conference room for video calls in virtual office.
- Buy VR equipment and live in the future.
- Build a voxel pub to represent our future SSB pub.
- Set up our real meatspace office inspired by our digital prototype.

## :rocket: Deployment

1. Install Vagrant.
2. Prepare the environment by running these commands:
    ```
    vagrant plugin install vagrant-digitalocean
    vagrant plugin install vagrant-env
    cp sample.env .env
    ```
3. Edit your new `.env` file.
4. Run `vagrant up` to create a remote test server.
5. As you modify ansible config files, run `vagrant provision` to sync
   server to configuration in code.
6. When you're done experimenting, spin down the cloud server with
   `vagrant destroy`.

## :copyright: License

TBD
