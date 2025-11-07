# VexAPI

[![Java](https://img.shields.io/badge/Java-21-orange)](https://www.oracle.com/java/)
[![Minecraft](https://img.shields.io/badge/Minecraft-1.21-green)](https://www.minecraft.net/)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

An advanced API plugin for Minecraft servers that integrates and extends functionality across the VexDevelopment ecosystem, especially for VexOptimizator.  
Built with performance, extensibility, and developer usability in mind.

---

## Overview
VexAPI acts as a powerful bridge between Minecraft plugins and optimization systems.  
It provides hooks, events, and real-time performance tracking for developers to create optimized, scalable server integrations.  
Designed for Paper 1.21+ and seamlessly compatible with [VexOptimizator](https://github.com/VeX4eto4777/VexOptimizator).

---

## Features
- Dynamic AI-based optimization framework  
- Tick balancer to prevent lag spikes  
- Smart chunk suspension and loading control  
- Automated entity and item cleanup system  
- Custom events for TPS drops and optimization triggers  
- Developer-friendly hook and event API  
- Real-time TPS and MSPT performance tracking  
- Command suite for management and monitoring  

---

## Installation
1. Download the latest `VexAPI.jar` from [Releases](https://github.com/VeX4eto4777/VexAPI/releases)  
2. Place it in your server’s `/plugins/` directory  
3. Make sure VexOptimizator is installed and enabled  
4. Restart the server  
5. Edit `config.yml` for advanced settings  

---

## Commands
| Command | Description |
|----------|-------------|
| `/vexapi stats` | Shows optimization statistics |
| `/vexapi analyze` | Runs performance analysis |
| `/vexapi clearlag` | Manually triggers ClearLag |
| `/vexapi reload` | Reloads configuration |

---

## Permissions
| Permission | Description |
|-------------|-------------|
| `vexapi.admin` | Full administrative access |
| `vexapi.admin.clearlag` | Allows ClearLag command |

---

## Developer Integration
Easily connect your plugin with VexAPI:

```java
import com.vexapi.api.VexAPI;
import com.vexapi.api.OptimizationStats;
import org.bukkit.plugin.java.JavaPlugin;

public class MyPlugin extends JavaPlugin {

    @Override
    public void onEnable() {
        VexAPI api = VexAPI.getInstance();

        if (api.isVexOptimizatorAvailable()) {
            api.registerHook("myOptimization", () -> {
                getLogger().info("Running custom optimization...");
            });

            api.subscribeToEvent("optimizationApplied", () -> {
                getLogger().info("Optimization event triggered!");
            });

            OptimizationStats stats = api.getOptimizationStats();
            getLogger().info("TPS: " + stats.getTps());
            getLogger().info("MSPT: " + stats.getMspt());
````markdown
# VexAPI

[![Java](https://img.shields.io/badge/Java-21-orange)](https://www.oracle.com/java/)
[![Minecraft](https://img.shields.io/badge/Minecraft-1.21-green)](https://www.minecraft.net/)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

An advanced API plugin for Minecraft servers that integrates and extends functionality across the VexDevelopment ecosystem, especially for VexOptimizator.  
Built with performance, extensibility, and developer usability in mind.

---

## Overview
VexAPI acts as a powerful bridge between Minecraft plugins and optimization systems.  
It provides hooks, events, and real-time performance tracking for developers to create optimized, scalable server integrations.  
Designed for Paper 1.21+ and seamlessly compatible with [VexOptimizator](https://github.com/VeX4eto4777/VexOptimizator).

---

## Features
- Dynamic AI-based optimization framework  
- Tick balancer to prevent lag spikes  
- Smart chunk suspension and loading control  
- Automated entity and item cleanup system  
- Custom events for TPS drops and optimization triggers  
- Developer-friendly hook and event API  
- Real-time TPS and MSPT performance tracking  
- Command suite for management and monitoring  

---

## Installation
1. Download the latest `VexAPI.jar` from [Releases](https://github.com/VeX4eto4777/VexAPI/releases)  
2. Place it in your server’s `/plugins/` directory  
3. Make sure VexOptimizator is installed and enabled  
4. Restart the server  
5. Edit `config.yml` for advanced settings  

---

## Commands
| Command | Description |
|----------|-------------|
| `/vexapi stats` | Shows optimization statistics |
| `/vexapi analyze` | Runs performance analysis |
| `/vexapi clearlag` | Manually triggers ClearLag |
| `/vexapi reload` | Reloads configuration |

---

## Permissions
| Permission | Description |
|-------------|-------------|
| `vexapi.admin` | Full administrative access |
| `vexapi.admin.clearlag` | Allows ClearLag command |

---

## Developer Integration
Easily connect your plugin with VexAPI:

```java
import com.vexapi.api.VexAPI;
import com.vexapi.api.OptimizationStats;
import org.bukkit.plugin.java.JavaPlugin;

public class MyPlugin extends JavaPlugin {

    @Override
    public void onEnable() {
        VexAPI api = VexAPI.getInstance();

        if (api.isVexOptimizatorAvailable()) {
            api.registerHook("myOptimization", () -> {
                getLogger().info("Running custom optimization...");
            });

            api.subscribeToEvent("optimizationApplied", () -> {
                getLogger().info("Optimization event triggered!");
            });

            OptimizationStats stats = api.getOptimizationStats();
            getLogger().info("TPS: " + stats.getTps());
            getLogger().info("MSPT: " + stats.getMspt());
        }
    }
}
````

---

## Support & Community

Join our official Discord for help, development discussions, and updates:
👉 [**Join VexDevelopment Discord**](https://discord.gg/EH7afrRCQv)

---

## License

This project is licensed under the MIT License.
See the [LICENSE](LICENSE) file for full details.

---

**Developed by VexDevelopment**
A dedicated team focused on building efficient, high-performance Minecraft plugins for modern servers.
Delivering stability, optimization, and innovation — one tick at a time.

```
```
}
    }
}
````

---

## Support & Community

Join our official Discord for help, development discussions, and updates:
👉 [**Join VexDevelopment Discord**](https://discord.gg/EH7afrRCQv)

---

## License

This project is licensed under the MIT License.
See the [LICENSE](LICENSE) file for full details.

---

**Developed by VexDevelopment**
A dedicated team focused on building efficient, high-performance Minecraft plugins for modern servers.
Delivering stability, optimization, and innovation — one tick at a time.

```
```

