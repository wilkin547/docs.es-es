---
ms.openlocfilehash: 36f1ee26def82d426b6637ae96f382fc89791a2f
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2020
ms.locfileid: "93135950"
---

### <a name="install-the-sdk"></a><span data-ttu-id="e2132-101">Instalación del SDK</span><span class="sxs-lookup"><span data-stu-id="e2132-101">Install the SDK</span></span>

<span data-ttu-id="e2132-102">El SDK de .NET Core permite desarrollar aplicaciones con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e2132-102">The .NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="e2132-103">Para instalar el SDK de .NET Core, ejecute los siguientes comandos.</span><span class="sxs-lookup"><span data-stu-id="e2132-103">To install the .NET Core SDK, run the following commands.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

### <a name="install-the-runtime"></a><span data-ttu-id="e2132-104">Instalación de la instancia en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="e2132-104">Install the runtime</span></span>

<span data-ttu-id="e2132-105">.NET Core Runtime le permite ejecutar aplicaciones que se realizaron con .NET Core que no incluían el entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e2132-105">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="e2132-106">Los comandos siguientes instalan el entorno de ejecución de ASP.NET Core, el más compatible con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e2132-106">The following commands install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="e2132-107">En el terminal, ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="e2132-107">In your terminal, run the following commands.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

<span data-ttu-id="e2132-108">Una alternativa al entorno de ejecución de ASP.NET Core es instalar la instancia del de .NET Core, que no incluye compatibilidad con ASP.NET Core; en el comando anterior, reemplace `aspnetcore-runtime-2.1` por `dotnet-runtime-3.1`.</span><span class="sxs-lookup"><span data-stu-id="e2132-108">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime that doesn't include ASP.NET Core support: replace `aspnetcore-runtime-2.1` in the previous command with `dotnet-runtime-3.1`.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```
