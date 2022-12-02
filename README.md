# Welcome to the home-mini-cluster !

## 🚧 Construction site 🏗️ 🚧

In this project I'll plan and document the setup of my mini-cluster.

Why? Because I can. And I happen to have 5 chrome boxes.

Goal of the mini-cluster? is to be defined.

⚠️ *Much important:* whatever ideas you have -> send them to Discussions section!


## 🎯 Final Destination 1:
- VPN connectivity to cluster
- Docker swarm (k3s overkill? Final Destination 2?)
  - _mail server?_
  - _some crypto node?_
  - _google docs killer?_
  - _dropbox replacement?_
  - _???_
- Storage in Raid
  - //TODO _adding several flash/drives and setup "cluster-raid" vs dedicated NAS_


## 🚧 Next:
- [ ] Install Fedora server on all machines (most run Fedora Workspace)
- [ ] Setup SSH connections to machines
- [ ] Ansible script to setup basics
  - _what are the basics btw?_


# The HW

* 3x Asus Chromebox2 CN62
* 2x Asus Chromebox3 CN65

The Chromeboxes had to be "repurposed" because they were tied to an Enterprise account, which doesn't exist anymore, I don't have another one.

The way to go was to treat them as bricked and thus unbrick them. All the credit goes to Mr. Chromebox that is maintaining great documentation and tooling, albeit the page for unbricking is actually "hidden": https://wiki.mrchromebox.tech/Unbricking

## Notes 
On MrChromebox's [list of devices](https://wiki.mrchromebox.tech/Supported_Devices) Asus Chromebox3 (CN65) is mentioned as having the board TEEMO, but you won't find it in the [sources.sh](https://github.com/MrChromebox/scripts/blob/master/sources.sh), at least I didn't. I found accidentally somewhere that it's actually (or also) called FIZZ, and that can be found there. It worked for me.

The SPI flash chip is super easy to locate on Chromebox 3 - just open the bottom panel and it's there named "Winbond". On Chromebox 2 is tricker: 
1. Remove bottom cover
2. Remove screws holding the board
3. Remove small plastic thingie covering the Kensington slot
4. Remove the board
5. Remove the 2 screws on the fan and remove the fan (it's a tiny bit glued to the "exhaust" from CPU)
6. SPI flash chip is there!

# The SW

A good friend of mine recommended going with Fedora, so I went with Fedora 37 Server Edition. After the chromeboxes were unbricked, I created a bootable USB flash drive using Fedora Media Writer (I'm on a Mac) and installed it. Worked like a charm.

# Setup

1. SSH was already up
2. Changed host name with 

```bash
hostnamectl set-hostname {name}
```
3. Upload ssh key

```bash
ssh-copy-id username@remote_host
```

# Ideas, links

k3s on Raspberry Pis: https://www.youtube.com/watch?app=desktop&v=X9fSMGkjtug
(potentially overkill)
