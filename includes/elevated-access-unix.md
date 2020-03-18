---
ms.openlocfilehash: 85f50b221e7ecb1ebd6fa539894ab7aabed8d362
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "67540124"
---
### <a name="install-the-global-tool"></a>Instalación de la herramienta global

Los recursos de paquete deben instalarse en una ubicación protegida con la opción `--tool-path`. Con esta separación se pretende aislar un entorno de usuario con privilegios restringidos de un entorno con privilegios elevados.

```bash
sudo dotnet tool install PACKAGEID --tool-path /usr/local/share/dotnet-tools
```

Se creará `/usr/local/share/dotnet-tools` con permiso `drwxr-xr-x`. Si ya existe el directorio, use el comando `ls -l` para comprobar que los usuarios restringidos no tienen permiso para editar el directorio. Si es así, use el comando `sudo chmod o-w -R /usr/share/dotnet-tools` para quitar el acceso.

### <a name="run-the-global-tool"></a>Ejecución de la herramienta global

**Opción 1** Use la ruta de acceso completa con sudo:

```bash
sudo /usr/local/share/dotnet-tools/TOOLCOMMAND
```

**Opción 2** Agregue el vínculo del símbolo de la herramienta, una vez por cada herramienta:

```bash
sudo ln -s /usr/local/share/dotnet-tools/TOOLCOMMAND /usr/local/bin/TOOLCOMMAND
```

Y ejecute con:

```bash
sudo TOOLCOMMAND
```

### <a name="uninstall-the-global-tool"></a>Desinstalación de la herramienta global

```bash
sudo dotnet tool uninstall PACKAGEID --tool-path /usr/local/share/dotnet-tools
```

Si ha realizado un vínculo de símbolo, también deberá quitarlo:

```bash
sudo rm /usr/local/bin/TOOLCOMMAND
```
