# Atomic-KDE-Saigon &nbsp; [![build-ublue](https://github.com/blue-build/template/actions/workflows/build.yml/badge.svg)](https://github.com/blue-build/template/actions/workflows/build.yml)

This the setup for my customized ublue-kinoite image, using the BlueBuild toolkit, based on Fedora Kinoite 40.

For more information i refer to their website at https://universal-blue.org/. You can find a large number of other specific images there as well.

A specific part of their toolkit is the Tinkerers Guide to building your own images. That has now been spun-off to BlueBuild at https://blue-build.org/. 

It's a work in progress, but as they mention it is 'the easiest way to build your own desktop Linux images'.


## Idea

In 2022 I already made a number of adapted images, but that got shelved and discontinued by me after some time.

Now, with the availability of KDE Plasma 6, it is time to revive it and remake that slimmed down image. 

This image will deliver an atomic KDE Plasma 6 desktop, with all Ublue tooling and tweaks included, but with the applications brought back to a bare minimum.


## What's in & What's out

All tooling added by the Ublue project remains pristine. Suffice to say I don't run the DX (developers) or Nvidia images here; it is the 'standard' version of their and Fedora's Kinoite image that I'm adjusting here.

This means software like distrobox, Konsole, Dolphin, Spectacle and htop have already been included in the base image.

KDE has done an extensive job to make most other applications available through a flatpak as well, like Gnome did. So, no need to include Gwenview, Okular or Elisa etc. etc. in the image. 

I've only included Krusader and KDE Print manager (I use those and they have not (yet) been flatpak'ed), plus some cli tools that i use. Can't live without my Midnight Commander!

One flatpak is installed ootb; the Floorp browser is a cool project and it gives the end-user at least a browser upon startup.


      What has been added:                        What has been removed:      
      
      - fastfetch                                    - firefox (rpm)
      - fzf                                          - firefox-langpacks
      - kde-print-manager                            - kcharselect 
      - krusader                                     - kfind 
      - lsd                                          - kde-connect 
      - mc                                           - kde-connect-libs 
      - micro                                        - kdeconnectd
                                                     - kmousetool
                                                     - krfb 
                                                     - krfb-libs 
                                                     - nvtop 
                                                     - plasma-discover-notifier 
                                                     - plasma-welcome  
                                                      
      
      
## How do you get it?

Start with any Fedora Atomic image and install it. Then follow these instructions:

Rebase to the unsigned variant of the base image by running the following commands:

      rpm-ostree rebase ostree-unverified-registry:ghcr.io/thesaigoneer/atomic-kde-saigon:latest

* Reboot: systemctl reboot

Rebase to the signed variant of the image: 

      rpm-ostree rebase ostree-image-signed:docker://ghcr.io/thesaigoneer/atomic-kde-saigon:latest

* Reboot: systemctl reboot

Login to your new KDE Plasma Atomic from Saigon!

## WIP

* This is a work-in-progress, so expect some changes over time (although nothing fundamental). 
      
* At a certain moment i'd like to get rid of Discover altogether, but for now I've just disabled the nagging notifier
                         
## Current Quirks:

None

## Nota bene

Feel free to use these builds and dots. I do not, however, offer or imply any form of support or ongoing maintenance. 

And of course, you use them entirely at your own risk. 

Have fun!
