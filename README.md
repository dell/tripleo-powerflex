# TripleO-PowerFlex

This repository holds all configuration files needed to deploy PowerFlex with TripleO

## PowerFlex services layout

| Service Name | Description                                                                                                                                                                                                                                               | Deployed on            |
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------|
| PowerFlexMDM    | The Metadata Manager (MDM) configures and monitors the PowerFlex system.  It contains all the metadata required for system operation.  MDM is responsible for data migration, rebuilds, and all system-related functions. No user data passes thru the MDM | Controller             |
| PowerFlexLIA    | This is the agent that is installed on all nodes (both MDM, SDC, SDS) in the PowerFlex system.  This agent is used when you want to do something on the endpoints, ie. collect logs or upgrade the system to a newer release.                              | Controller, Compute |
| PowerFlexSDC    | A lightweight block device driver that gives the capability to access PowerFlex shared block volumes to applications.  This service is need on both controllers (Glance) and ComputeHCI (Cinder)                                                           | Controller, Compute |
| PowerFlexSDS    | A software daemon that enables a server in the PowerFlex cluster to contribute its local storage to ScaleIO Storage.  An instance of the SDS runs on every server that contributes some or all of its local storage space                                  | Storage             |
