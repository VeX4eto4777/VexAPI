# VexAPI

[![Java](https://img.shields.io/badge/Java-21-orange)](https://www.oracle.com/java/)
[![Minecraft](https://img.shields.io/badge/Minecraft-1.21-green)](https://www.minecraft.net/)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

An advanced API plugin for Minecraft servers designed to integrate and extend functionality of Vex-related plugins, particularly VexOptimizator. Built with performance optimization and developer extensibility in mind.

## Overview

VexAPI serves as a powerful bridge between Minecraft plugins and optimization systems. It provides a comprehensive API for developers to hook into server optimization features, monitor performance metrics, and extend functionality across the Vex ecosystem. The plugin is built on Paper API 1.21 and offers seamless integration with VexOptimizator for enhanced server performance.

## Features

- **Dynamic AI Optimization**: Intelligent server optimization using machine learning algorithms
- **Tick Balancer**: Automatic distribution of server ticks to prevent lag spikes
- **Chunk Suspension Manager**: Smart chunk loading/unloading for memory efficiency
- **Clear Lag Manager**: Automated entity and item cleanup to maintain server performance
- **Event System**: Custom events for AFK detection, TPS drops, and optimization applications
- **Hook System**: Easy integration points for external plugins
- **Real-time Statistics**: Comprehensive performance monitoring and reporting
- **Command Interface**: In-game commands for stats, analysis, and management

## Installation

### Prerequisites
- Minecraft Server running Paper 1.21 or higher
- VexOptimizator plugin (required dependency)

### Steps
1. Download the latest `VexAPI.jar` from the releases page
2. Place the jar file in your server's `plugins` folder
3. Ensure VexOptimizator is installed and enabled
4. Restart your server
5. Configure settings in `plugins/VexAPI/config.yml` if needed

The plugin will automatically create configuration files on first startup.

## Usage

### In-Game Commands
```
/vexapi stats     - View current optimization statistics
/vexapi analyze   - Run performance analysis
/vexapi reload    - Reload plugin configuration
/vexapi clearlag  - Manually trigger clear lag
```

### Permissions
- `vexapi.admin` - Full access to all commands (default: op)
- `vexapi.admin.clearlag` - Access to clearlag command (default: op)

## Integration

VexAPI provides a simple API for developers to integrate with optimization systems:

```java
import com.vexapi.api.VexAPI;
import com.vexapi.api.OptimizationStats;

// Get the API instance
VexAPI api = VexAPI.getInstance();

// Check if VexOptimizator is available
if (api.isVexOptimizatorAvailable()) {
    // Register a hook
    api.registerHook("myPluginHook", () -> {
        // Your custom logic here
    });

    // Subscribe to events
    api.subscribeToEvent("tpsDrop", () -> {
        // Handle TPS drop event
    });

    // Get optimization statistics
    OptimizationStats stats = api.getOptimizationStats();
    System.out.println("Current TPS: " + stats.getTps());
}
```

## Example Code

### Basic Plugin Integration
```java
package com.example.myplugin;

import com.vexapi.api.VexAPI;
import org.bukkit.plugin.java.JavaPlugin;

public class MyPlugin extends JavaPlugin {

    @Override
    public void onEnable() {
        VexAPI api = VexAPI.getInstance();

        // Register a custom optimization hook
        api.registerHook("myOptimization", () -> {
            // Implement your optimization logic
            getLogger().info("Running custom optimization...");
        });

        // Subscribe to optimization events
        api.subscribeToEvent("optimizationApplied", () -> {
            getLogger().info("Optimization applied by VexAPI!");
        });
    }
}
```

### Accessing Performance Metrics
```java
import com.vexapi.api.OptimizationStats;

public class PerformanceMonitor {

    public void logPerformance() {
        OptimizationStats stats = VexAPI.getInstance().getOptimizationStats();

        getLogger().info("=== VexAPI Performance Stats ===");
        getLogger().info("TPS: " + stats.getTps());
        getLogger().info("MSPT: " + stats.getMspt());
        getLogger().info("Loaded Chunks: " + stats.getLoadedChunks());
        getLogger().info("Active Entities: " + stats.getActiveEntities());
    }
}
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

**Developed by VexDevelopment** | *Optimizing Minecraft, One Tick at a Time*
