---
ms.openlocfilehash: cc394741e399f4fc54dd67f1736f7027badf4c7d
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2020
ms.locfileid: "94507105"
---

### <a name="install-the-sdk"></a><span data-ttu-id="f97f0-101">Instalación del SDK</span><span class="sxs-lookup"><span data-stu-id="f97f0-101">Install the SDK</span></span>

<span data-ttu-id="f97f0-102">El SDK de .NET permite desarrollar aplicaciones con .NET.</span><span class="sxs-lookup"><span data-stu-id="f97f0-102">The .NET SDK allows you to develop apps with .NET.</span></span> <span data-ttu-id="f97f0-103">Si instala el SDK de .NET, no necesita instalar el entorno de ejecución correspondiente.</span><span class="sxs-lookup"><span data-stu-id="f97f0-103">If you install the .NET SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="f97f0-104">Para instalar el SDK de .NET, ejecute los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f97f0-104">To install the .NET SDK, run the following commands:</span></span>

```bash
sudo yum install dotnet-sdk-5.0
```

### <a name="install-the-runtime"></a><span data-ttu-id="f97f0-105">Instalación de la instancia en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="f97f0-105">Install the runtime</span></span>

<span data-ttu-id="f97f0-106">El entorno de ejecución de ASP.NET Core le permite ejecutar aplicaciones creadas con .NET en las que no se ha proporcionado el entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f97f0-106">The ASP.NET Core Runtime allows you to run apps that were made with .NET that didn't provide the runtime.</span></span> <span data-ttu-id="f97f0-107">Los comandos siguientes instalan el entorno de ejecución de ASP.NET Core, el más compatible con .NET.</span><span class="sxs-lookup"><span data-stu-id="f97f0-107">The following commands install the ASP.NET Core Runtime, which is the most compatible runtime for .NET.</span></span> <span data-ttu-id="f97f0-108">En el terminal, ejecute los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f97f0-108">In your terminal, run the following commands:</span></span>

```bash
sudo yum install aspnetcore-runtime-5.0
```

<span data-ttu-id="f97f0-109">Una alternativa al entorno de ejecución de ASP.NET Core es instalar el de .NET, que no incluye compatibilidad con ASP.NET Core; en el comando anterior, reemplace `aspnetcore-runtime-5.0` por `dotnet-runtime-5.0`:</span><span class="sxs-lookup"><span data-stu-id="f97f0-109">As an alternative to the ASP.NET Core Runtime, you can install the .NET Runtime, which doesn't include ASP.NET Core support: replace `aspnetcore-runtime-5.0` in the previous command with `dotnet-runtime-5.0`:</span></span>

```bash
sudo yum install dotnet-runtime-5.0
```
