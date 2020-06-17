# TripleO-VxFlexOS

This repository holds all configuration files needed to deploy VxFlexOS with TripleO

## VxFlexOS services layout

| Service Name | Description                                                                                                                                                                                                                                               | Deployed on            |
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------|
| VxFlexMDM    | The Metadata Manager (MDM) configures and monitors the VxFlexOS system.  It contains all the metadata required for system operation.  MDM is responsible for data migration, rebuilds, and all system-related functions. No user data passes thru the MDM | Controller             |
| VxFlexLIA    | This is the agent that is installed on all nodes (both MDM, SDC, SDS) in the VxFlexOS system.  This agent is used when you want to do something on the endpoints, ie. collect logs or upgrade the system to a newer release.                              | Controller, ComputeHCI |
| VxFlexSDS    | A lightweight block device driver that gives the capability to access VxFlexOS shared block volumes to applications.  This service is need on both controllers (Glance) and ComputeHCI (Cinder)                                                           | Controller, ComputeHCI |
| VxFlexSDC    | A software daemon that enables a server in the VxFlexOS cluster to contribute its local storage to ScaleIO Storage.  An instance of the SDS runs on every server that contributes some or all of its local storage space                                  | ComputeHCI             |
