---
ms.openlocfilehash: 85f50b221e7ecb1ebd6fa539894ab7aabed8d362
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "67540124"
---
### <a name="install-the-global-tool"></a><span data-ttu-id="4b6e3-101">Instalación de la herramienta global</span><span class="sxs-lookup"><span data-stu-id="4b6e3-101">Install the global tool</span></span>

<span data-ttu-id="4b6e3-102">Los recursos de paquete deben instalarse en una ubicación protegida con la opción `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="4b6e3-102">Package assets should be installed in a protected location using the `--tool-path` option.</span></span> <span data-ttu-id="4b6e3-103">Con esta separación se pretende aislar un entorno de usuario con privilegios restringidos de un entorno con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="4b6e3-103">This separation avoids sharing a restricted user environment with an elevated environment.</span></span>

```bash
sudo dotnet tool install PACKAGEID --tool-path /usr/local/share/dotnet-tools
```

<span data-ttu-id="4b6e3-104">Se creará `/usr/local/share/dotnet-tools` con permiso `drwxr-xr-x`.</span><span class="sxs-lookup"><span data-stu-id="4b6e3-104">`/usr/local/share/dotnet-tools` will be created with permission `drwxr-xr-x`.</span></span> <span data-ttu-id="4b6e3-105">Si ya existe el directorio, use el comando `ls -l` para comprobar que los usuarios restringidos no tienen permiso para editar el directorio.</span><span class="sxs-lookup"><span data-stu-id="4b6e3-105">If the directory already exists, use the `ls -l` command to verify the restricted user doesn't have permission to edit the directory.</span></span> <span data-ttu-id="4b6e3-106">Si es así, use el comando `sudo chmod o-w -R /usr/share/dotnet-tools` para quitar el acceso.</span><span class="sxs-lookup"><span data-stu-id="4b6e3-106">If so, use the `sudo chmod o-w -R /usr/share/dotnet-tools` command to remove the access.</span></span>

### <a name="run-the-global-tool"></a><span data-ttu-id="4b6e3-107">Ejecución de la herramienta global</span><span class="sxs-lookup"><span data-stu-id="4b6e3-107">Run the global tool</span></span>

<span data-ttu-id="4b6e3-108">**Opción 1** Use la ruta de acceso completa con sudo:</span><span class="sxs-lookup"><span data-stu-id="4b6e3-108">**Option 1** Use the full path with sudo:</span></span>

```bash
sudo /usr/local/share/dotnet-tools/TOOLCOMMAND
```

<span data-ttu-id="4b6e3-109">**Opción 2** Agregue el vínculo del símbolo de la herramienta, una vez por cada herramienta:</span><span class="sxs-lookup"><span data-stu-id="4b6e3-109">**Option 2** Add the symbol link of the tool, once per tool:</span></span>

```bash
sudo ln -s /usr/local/share/dotnet-tools/TOOLCOMMAND /usr/local/bin/TOOLCOMMAND
```

<span data-ttu-id="4b6e3-110">Y ejecute con:</span><span class="sxs-lookup"><span data-stu-id="4b6e3-110">And run with:</span></span>

```bash
sudo TOOLCOMMAND
```

### <a name="uninstall-the-global-tool"></a><span data-ttu-id="4b6e3-111">Desinstalación de la herramienta global</span><span class="sxs-lookup"><span data-stu-id="4b6e3-111">Uninstall the global tool</span></span>

```bash
sudo dotnet tool uninstall PACKAGEID --tool-path /usr/local/share/dotnet-tools
```

<span data-ttu-id="4b6e3-112">Si ha realizado un vínculo de símbolo, también deberá quitarlo:</span><span class="sxs-lookup"><span data-stu-id="4b6e3-112">If you made a symbol link, you also need to remove it:</span></span>

```bash
sudo rm /usr/local/bin/TOOLCOMMAND
```
