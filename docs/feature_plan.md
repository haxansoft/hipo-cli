# feature plan

Hipo-cli is a CLI tool for interacting with a Hipodocs instance. Hipo-cli is primarily for server administration and operation tasks. 

v0.1.0

Proof of concept release features

- hipo server start: starts a hipo instance
  - requires some environment variables be set:
    - bind address
    - host
    - port
    - repo path

- hipo server stop: gracefully stops a hipo instance
- think about logging, might need some type of log setup or log level flag

Stuff to research

- Viper and Cobra together: historically not a great idea due to issues with order of preference for environment variables 
  - going to try the technique outlined here: https://github.com/carolynvs/stingoftheviper
  - preferred load order: flag, then env vars, then defaults or config files
  - if this doesn't work I'll remove viper and research the best way to set up for systemd/unitd
    - i think that is possible loading via file on a path specified in the unit file but not sure if there is another built-in order of load preference 