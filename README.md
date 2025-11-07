# VexAPI

[![Java](https://img.shields.io/badge/Java-21-orange)](https://www.oracle.com/java/)
[![Minecraft](https://img.shields.io/badge/Minecraft-1.21-green)](https://www.minecraft.net/)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

VexAPI is an API plugin for Paper 1.21 servers that connects and extends functionality across the Vex ecosystem, including VexOptimizator. It provides hooks, events and runtime metrics for developers who need reliable access to optimization systems.

## Overview
VexAPI exposes performance data, events and integration points so other plugins can register hooks, subscribe to optimization events and read live statistics. It is built for stability and low overhead and is intended to be used alongside VexOptimizator for full optimization control.

## Features
Dynamic AI optimization for adaptive behavior  
Tick balancing to reduce lag spikes  
Smart chunk suspension and loading control  
Automated item and entity cleanup management  
Custom events for TPS drops, AFK detection and optimization triggers  
Simple hook registration for third party plugins  
Real time TPS, MSPT and entity statistics  
Command interface for analysis and control

## Installation
Prerequisites
- Paper 1.21 or newer
- VexOptimizator installed and enabled

Steps
1. Download the latest VexAPI.jar from the releases page  
2. Place VexAPI.jar into the server plugins folder  
3. Restart the server  
4. Edit plugins/VexAPI/config.yml if you need custom settings

The plugin will create default configuration files on first run.

## Commands
/vexapi stats — show current optimization statistics  
/vexapi analyze — run a performance analysis of loaded chunks and entities  
/vexapi clearlag — trigger manual cleanup operations  
/vexapi reload — reload configuration

Permissions
vexapi.admin — full access to commands  
vexapi.admin.clearlag — allow clearlag command

## Developer integration
Example usage to get stats and register hooks

```java
import com.vexapi.api.VexAPI;
import com.vexapi.api.OptimizationStats;

VexAPI api = VexAPI.getInstance();

if (api.isVexOptimizatorAvailable()) {
    api.registerHook("myPluginHook", () -> {
        // custom logic
    });

    api.subscribeToEvent("tpsDrop", () -> {
        // handle TPS drop
    });

    OptimizationStats stats = api.getOptimizationStats();
    System.out.println("Current TPS: " + stats.getTps());
}
````

Example plugin integration

```java
package com.example.myplugin;

import com.vexapi.api.VexAPI;
import org.bukkit.plugin.java.JavaPlugin;

public class MyPlugin extends JavaPlugin {

    @Override
    public void onEnable() {
        VexAPI api = VexAPI.getInstance();

        api.registerHook("myOptimization", () -> {
            getLogger().info("Running custom optimization");
        });

        api.subscribeToEvent("optimizationApplied", () -> {
            getLogger().info("Optimization applied by VexAPI");
        });
    }
}
```

## Support

Report issues on GitHub at [https://github.com/VeX4eto4777/VexAPI/issues](https://github.com/VeX4eto4777/VexAPI/issues)
Include server version, Java version, config.yml and relevant logs.

Join the community on Discord for support and announcements: 
(https://img.shields.io/badge/Discord-Join%20Now-5865F2?logo=discord&logoColor=white)](https://discord.gg/EH7afrRCQv)



## Integration with VexOptimizator

VexAPI works best with VexOptimizator. Install VexOptimizator first if you want full optimization control.
VexOptimizator repository: [https://github.com/VeX4eto4777/VexOptimizator](https://github.com/VeX4eto4777/VexOptimizator)

## License

This project is licensed under the MIT License. See the LICENSE file for details.

Developed by VexDevelopment

