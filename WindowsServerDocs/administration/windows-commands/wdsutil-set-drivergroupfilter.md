---
title: Subcommand set-DriverGroupFilter
description: Reference article for Subcommand set-DriverGroupFilter, which adds or removes an existing driver group filter from a driver group.
ms.topic: reference
ms.assetid: 829ab1f0-4514-421e-9cc0-767b238da69c
ms.author: roharwoo
author: robinharwood
manager: mtillman
ms.date: 10/16/2017
---

# Subcommand: set-DriverGroupFilter

Adds or removes an existing driver group filter from a driver group.

## Syntax

```
wdsutil /Set-DriverGroupFilter /DriverGroup:<Group Name> [/Server:<Server name>] /FilterType:<Filter Type> [/Policy:{Include | Exclude}] [/AddValue:<Value> [/AddValue:<Value> ...]] [/RemoveValue:<Value> [/RemoveValue:<Value> ...]]
```

### Parameters

|         Parameter          |                                                                                                                                                                                                                                                                                                                                                                                                                                                                               Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
|----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| /DriverGroup:\<Group Name> |                                                                                                                                                                                                                                                                                                                                                                                                                                                                 Specifies the name of the driver group.                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|  [/Server:\<Server name>]  |                                                                                                                                                                                                                                                                                                                                                                                                                Specifies the name of the server. This can be the NetBIOS name or the FQDN. If a server name is not specified, the local server is used.                                                                                                                                                                                                                                                                                                                                                                                                                 |
| /FilterType:\<FilterType>  |                                                                                                                                                                                                                                                                       Specifies the type of driver group filter to add or remove. You can specify multiple filters in a single command. For each **/FilterType**, you can add or remove multiple values using **/RemoveValue** and **/AddValue**. \<FilterType> can be one of the following:</br>**BiosVendor**</br>**BiosVersion**</br>**ChassisType**</br>**Manufacturer**</br>**Uuid**</br>**OsVersion**</br>**OsEdition**</br>**OsLanguage**                                                                                                                                                                                                                                                                        |
|     [/Policy:{Include      |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                Exclude}]                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
|    [/AddValue:\<Value>]    | Specifies the new client value to add to the filter. You can specify multiple values for a single filter type. See the following list for valid attribute values for **ChassisType**. For information about obtaining the values for all other filter types, see [Driver Group Filters](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd759191(v=ws.11)) (<https://go.microsoft.com/fwlink/?LinkID=155158>).</br>**Other**</br>**UnknownChassis**</br>**Desktop**</br>**LowProfileDesktop**</br>**PizzaBox**</br>**MiniTower**</br>**Tower**</br>**Portable**</br>**Laptop**</br>**Notebook**</br>**Handheld**</br>**DockingStation**</br>**AllInOne**</br>**SubNotebook**</br>**SpaceSaving**</br>**LunchBox**</br>**MainSystemChassis**</br>**ExpansionChassis**</br>**SubChassis**</br>**BusExpansionChassis**</br>**PeripheralChassis**</br>**StorageChassis**</br>**RackMountChassis**</br>**SealedCaseComputer**</br>**MultiSystemChassis**</br>**CompactPci**</br>**AdvancedTca** |
|  [/RemoveValue:\<Value>]   |                                                                                                                                                                                                                                                                                                                                                                                                                                     Specifies the existing client value to remove from the filter as specified with **/AddValue**.                                                                                                                                                                                                                                                                                                                                                                                                                                      |

## Examples

To remove a filter, type one of the following:
```
wdsutil /Set-DriverGroupFilter /DriverGroup:PrinterDrivers /FilterType:Manufacturer /Policy:Include /AddValue:Name1 /RemoveValue:Name2
```
```
wdsutil /Set-DriverGroupFilter /DriverGroup:PrinterDrivers /FilterType:Manufacturer /Policy:Include /RemoveValue:Name1 /FilterType:ChassisType /Policy:Exclude /AddValue:Tower /AddValue:MiniTower
```

## Related links

- [Command-Line Syntax Key](command-line-syntax-key.md)
