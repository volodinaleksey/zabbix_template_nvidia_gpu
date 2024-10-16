# Zabbix Template NVIDIA GPU monitoring

## Overview
For Zabbix version: 5.0 and higher.
The NVIDIA System Management Interface ([nvidia-smi](https://developer.nvidia.com/nvidia-system-management-interface)) utility used.

The template is developed for monitoring singe or multiply NVIDIA GPUs and provides the following information
* Clocks Graphics, Memory, SM, Video
* Fan Sped in %
* GPU Current Temp, Slowdown Temp, utilization in %
* Memory free, total, used, utilization in %
* Power Default Limit, Draw, Max Limit

LLD using for GPUs discovery and items creation.

This template was tested on:
* Windows 10
* Single and multiply NVIDIA GPUs

## Setup
Install Zabbix agent on Windows OS according to Zabbix documentation.

Copy `nvidia_gpu_template.conf` into the folder with Zabbix agent configuration (`C:\Program Files\Zabbix Agent\zabbix_agentd.d` by default). Don't forget to restart Zabbix agent.

For RHEK based distro you may see this error

Failed to initialize NVML: Insufficient Permissions

To fix this run following command

usermod -a -G vglusers zabbix

And restart Zabbix Agent in order to apply changes

systemctl restart zabbix-agent2.service

## Author

Aleksey Volodin

## UserParameters
UserParameter=nvidia.gpu.discovery,nvidia-smi --query-gpu=uuid,name --format=csv,noheader,nounits
UserParameter=nvidia.gpu.getalldata[*],nvidia-smi -q -i $1

## Macros used

There are no macros links in this template.

## Template links

There are no template links in this template.

## Discovery rules

|Name|Description|Type|Key and additional info|
|----|-----------|----|----|
|NVIDIA GPUs discovery |<p>Parse nvidia-smi output fro UUID and GPUs names.</p> |ZABBIX_PASSIVE |nvidia.gpu.discovery<p>**Preprocessing**:</p>- JAVASCRIPT |

## Items collected

* Clocks Graphics
* Clocks Graphics
* Clocks Memory
* Clocks SM
* Clocks Video
* Fan Sped in %
* GPU Current Temp
* GPU Slowdown Temp
* GPU utilization in %
* Memory free
* Memory total
* Memory used
* Memory utilization in %
* Power Default Limit
* Power Draw
* Power Max Limit


## Triggers

There are no triggers in this template.
