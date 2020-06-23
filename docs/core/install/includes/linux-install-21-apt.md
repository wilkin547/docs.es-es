---
ms.openlocfilehash: 164d7a8277cf985735b959c73eb87391944e795b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602679"
---

### <a name="install-the-sdk"></a><span data-ttu-id="f2965-101">Instalación del SDK</span><span class="sxs-lookup"><span data-stu-id="f2965-101">Install the SDK</span></span>

<span data-ttu-id="f2965-102">El SDK de .NET Core permite desarrollar aplicaciones con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f2965-102">.NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="f2965-103">Si instala el SDK de .NET Core, no necesita instalar el entorno de ejecución correspondiente.</span><span class="sxs-lookup"><span data-stu-id="f2965-103">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="f2965-104">Para instalar el SDK de .NET Core, ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="f2965-104">To install .NET Core SDK, run the following commands:</span></span>

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y dotnet-sdk-2.1
```

> [!IMPORTANT]
> <span data-ttu-id="f2965-105">Si recibe un mensaje de error similar a **No se puede encontrar el paquete dotnet-sdk-2.1**, consulte la sección [Solución de problemas de APT](#apt-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="f2965-105">If you receive an error message similar to **Unable to locate package dotnet-sdk-2.1**, see the [APT troubleshooting](#apt-troubleshooting) section.</span></span>

### <a name="install-the-runtime"></a><span data-ttu-id="f2965-106">Instalación de la instancia en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="f2965-106">Install the runtime</span></span>

<span data-ttu-id="f2965-107">.NET Core Runtime le permite ejecutar aplicaciones que se realizaron con .NET Core que no incluían el entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f2965-107">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="f2965-108">Los siguientes comandos instalan el entorno de ejecución de ASP.NET Core, que es el entorno de ejecución más compatible con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f2965-108">The commands below install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="f2965-109">En el terminal, ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="f2965-109">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y aspnetcore-runtime-2.1
```

> [!IMPORTANT]
> <span data-ttu-id="f2965-110">Si recibe un mensaje de error similar a **No se puede encontrar el paquete aspnetcore-runtime-2.1**, consulte la sección [Solución de problemas de APT](#apt-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="f2965-110">If you receive an error message similar to **Unable to locate package aspnetcore-runtime-2.1**, see the [APT troubleshooting](#apt-troubleshooting) section.</span></span>

<span data-ttu-id="f2965-111">Una alternativa al entorno de ejecución de ASP.NET Core es instalar la instancia de .NET Core Runtime que no incluye compatibilidad con ASP.NET Core. Reemplace `aspnetcore-runtime-2.1` en los comandos anteriores por `dotnet-runtime-2.1`.</span><span class="sxs-lookup"><span data-stu-id="f2965-111">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime that doesn't include ASP.NET Core support: replace `aspnetcore-runtime-2.1` in the command above with `dotnet-runtime-2.1`.</span></span>

```bash
sudo apt-get install -y dotnet-runtime-2.1
```
