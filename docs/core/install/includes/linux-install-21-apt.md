---
ms.openlocfilehash: f7cd60f02a51516b8e35cdb9014fa8b96a188ae2
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506979"
---

### <a name="install-the-sdk"></a><span data-ttu-id="f129d-101">Instalación del SDK</span><span class="sxs-lookup"><span data-stu-id="f129d-101">Install the SDK</span></span>

<span data-ttu-id="f129d-102">El SDK de .NET Core permite desarrollar aplicaciones con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f129d-102">The .NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="f129d-103">Si instala el SDK de .NET Core, no necesita instalar el entorno de ejecución correspondiente.</span><span class="sxs-lookup"><span data-stu-id="f129d-103">If you install the .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="f129d-104">Para instalar el SDK de .NET Core, ejecute los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f129d-104">To install the .NET Core SDK, run the following commands:</span></span>

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y dotnet-sdk-2.1
```

> [!IMPORTANT]
> <span data-ttu-id="f129d-105">Si recibe un mensaje de error similar a **No se puede encontrar el paquete dotnet-sdk-2.1**, consulte la sección [Solución de problemas de APT](#apt-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="f129d-105">If you receive an error message similar to **Unable to locate package dotnet-sdk-2.1**, see the [APT troubleshooting](#apt-troubleshooting) section.</span></span>

### <a name="install-the-runtime"></a><span data-ttu-id="f129d-106">Instalación de la instancia en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="f129d-106">Install the runtime</span></span>

<span data-ttu-id="f129d-107">.NET Core Runtime le permite ejecutar aplicaciones que se realizaron con .NET Core que no incluían el entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f129d-107">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="f129d-108">Los comandos siguientes instalan el entorno de ejecución de ASP.NET Core, el más compatible con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f129d-108">The following commands install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="f129d-109">En el terminal, ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="f129d-109">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y aspnetcore-runtime-2.1
```

> [!IMPORTANT]
> <span data-ttu-id="f129d-110">Si recibe un mensaje de error similar a **No se puede encontrar el paquete aspnetcore-runtime-2.1**, consulte la sección [Solución de problemas de APT](#apt-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="f129d-110">If you receive an error message similar to **Unable to locate package aspnetcore-runtime-2.1**, see the [APT troubleshooting](#apt-troubleshooting) section.</span></span>

<span data-ttu-id="f129d-111">Una alternativa al entorno de ejecución de ASP.NET Core es instalar el de .NET Core, que no incluye compatibilidad con ASP.NET Core; en el comando anterior, reemplace `aspnetcore-runtime-2.1` por `dotnet-runtime-2.1`.</span><span class="sxs-lookup"><span data-stu-id="f129d-111">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime, which doesn't include ASP.NET Core support: replace `aspnetcore-runtime-2.1` in the previous command with `dotnet-runtime-2.1`.</span></span>

```bash
sudo apt-get install -y dotnet-runtime-2.1
```
