---
ms.openlocfilehash: dece035f443ff827a250ca1c1233b7651df7d108
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/28/2019
ms.locfileid: "67424703"
---
### <a name="install-the-global-tool"></a><span data-ttu-id="e661a-101">Instalación de la herramienta global</span><span class="sxs-lookup"><span data-stu-id="e661a-101">Install the global tool</span></span>

<span data-ttu-id="e661a-102">Los recursos de paquete deben instalarse en una ubicación protegida con la opción `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="e661a-102">Package assets should be installed in a protected location using the `--tool-path` option.</span></span> <span data-ttu-id="e661a-103">Con esta separación se pretende aislar un entorno de usuario con privilegios restringidos de un entorno con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="e661a-103">This separation avoids sharing a restricted user environment with an elevated environment.</span></span>

```bash
sudo dotnet tool install PACKAGEID --tool-path /usr/local/share/dotnet-tools
```

<span data-ttu-id="e661a-104">Se creará `/usr/local/share/dotnet-tools` con permiso `drwxr-xr-x`.</span><span class="sxs-lookup"><span data-stu-id="e661a-104">`/usr/local/share/dotnet-tools` will be created with permission `drwxr-xr-x`.</span></span> <span data-ttu-id="e661a-105">Si ya existe el directorio, use el comando `ls -l` para comprobar que los usuarios restringidos no tienen permiso para editar el directorio.</span><span class="sxs-lookup"><span data-stu-id="e661a-105">If the directory already exists, use the `ls -l` command to verify the restricted user doesn't have permission to edit the directory.</span></span> <span data-ttu-id="e661a-106">Si es así, use el comando `sudo chmod o-w -R /usr/share/dotnet-tools` para quitar el acceso.</span><span class="sxs-lookup"><span data-stu-id="e661a-106">If so, use the `sudo chmod o-w -R /usr/share/dotnet-tools` command to remove the access.</span></span>

### <a name="run-the-global-tool"></a><span data-ttu-id="e661a-107">Ejecución de la herramienta global</span><span class="sxs-lookup"><span data-stu-id="e661a-107">Run the global tool</span></span>

<span data-ttu-id="e661a-108">**Opción 1** Use la ruta de acceso completa con sudo:</span><span class="sxs-lookup"><span data-stu-id="e661a-108">**Option 1** Use the full path with sudo:</span></span>

```bash
sudo /usr/local/share/dotnet-tools/TOOLCOMMAND
```

<span data-ttu-id="e661a-109">**Opción 2** Agregue el vínculo del símbolo de la herramienta, una vez por cada herramienta:</span><span class="sxs-lookup"><span data-stu-id="e661a-109">**Option 2** Add the symbol link of the tool, once per tool:</span></span>

```bash
sudo ln -s /usr/local/share/dotnet-tools/TOOLCOMMAND /usr/local/bin/TOOLCOMMAND
```

<span data-ttu-id="e661a-110">Y ejecute con:</span><span class="sxs-lookup"><span data-stu-id="e661a-110">And run with:</span></span>

```bash
sudo TOOLCOMMAND
```

### <a name="uninstall-the-global-tool"></a><span data-ttu-id="e661a-111">Desinstalación de la herramienta global</span><span class="sxs-lookup"><span data-stu-id="e661a-111">Uninstall the global tool</span></span>

```bash
sudo dotnet tool uninstall PACKAGEID --tool-path /usr/local/share/dotnet-tools
```

<span data-ttu-id="e661a-112">Si ha realizado un vínculo de símbolo, también deberá quitarlo:</span><span class="sxs-lookup"><span data-stu-id="e661a-112">If you made a symbol link, you also need to remove it:</span></span>

```bash
sudo rm /usr/local/bin/TOOLCOMMAND
```