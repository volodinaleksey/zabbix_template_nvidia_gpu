# Zabbix Template Nvidia SMI monitoring

## Overview

This template integrates Nvidia SMI for a single graphics card with Zabbix.


The template adds monitoring of:


* Clocks Graphics, Memory, SM, Video

* Fan Sped in %

* GPU Current Temp, Slowdown Temp, utilization in %


* Memory free, total, used, utilization in %

* Power Default Limit, Draw, Max Limit


The following agent parameters can be used to add the metrics into Zabbix.

UserParameter=nvidia.gpu.discovery,nvidia-smi --query-gpu=uuid,name --format=csv,noheader,nounits
UserParameter=nvidia.gpu.getalldata[*],nvidia-smi -q -i $1

## Author

Aleksey Volodin

## Macros used

There are no macros links in this template.

## Template links

There are no template links in this template.

## Discovery rules

nvidia.gpu.discovery

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