---
ms.openlocfilehash: dece035f443ff827a250ca1c1233b7651df7d108
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/28/2019
ms.locfileid: "67424703"
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