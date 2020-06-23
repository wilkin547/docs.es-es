---
ms.openlocfilehash: db89539982c1afe0df374027d54826f3265f0fee
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602775"
---

### <a name="install-the-sdk"></a><span data-ttu-id="4f79e-101">Instalación del SDK</span><span class="sxs-lookup"><span data-stu-id="4f79e-101">Install the SDK</span></span>

<span data-ttu-id="4f79e-102">El SDK de .NET Core permite desarrollar aplicaciones con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4f79e-102">The .NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="4f79e-103">Para instalar el SDK de .NET Core, ejecute los siguientes comandos.</span><span class="sxs-lookup"><span data-stu-id="4f79e-103">To install the .NET Core SDK, run the following commands.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

### <a name="install-the-runtime"></a><span data-ttu-id="4f79e-104">Instalación de la instancia en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="4f79e-104">Install the runtime</span></span>

<span data-ttu-id="4f79e-105">.NET Core Runtime le permite ejecutar aplicaciones que se realizaron con .NET Core que no incluían el entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4f79e-105">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="4f79e-106">Los siguientes comandos instalan el entorno de ejecución de ASP.NET Core, que es el entorno de ejecución más compatible con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4f79e-106">The commands below install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="4f79e-107">En el terminal, ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="4f79e-107">In your terminal, run the following commands.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

<span data-ttu-id="4f79e-108">Una alternativa al entorno de ejecución de ASP.NET Core es instalar la instancia de .NET Core Runtime que no incluye compatibilidad con ASP.NET Core. Reemplace `aspnetcore-runtime-2.1` en los comandos anteriores por `dotnet-runtime-3.1`.</span><span class="sxs-lookup"><span data-stu-id="4f79e-108">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime that doesn't include ASP.NET Core support: replace `aspnetcore-runtime-2.1` in the command above with `dotnet-runtime-3.1`.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```
