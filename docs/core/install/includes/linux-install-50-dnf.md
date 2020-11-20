---
ms.openlocfilehash: 2cd5459ab7f2c8c96638bf27dd30980282036925
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506936"
---

### <a name="install-the-sdk"></a><span data-ttu-id="207e8-101">Instalación del SDK</span><span class="sxs-lookup"><span data-stu-id="207e8-101">Install the SDK</span></span>

<span data-ttu-id="207e8-102">El SDK de .NET permite desarrollar aplicaciones con .NET.</span><span class="sxs-lookup"><span data-stu-id="207e8-102">The .NET SDK allows you to develop apps with .NET.</span></span> <span data-ttu-id="207e8-103">Si instala el SDK de .NET, no necesita instalar el entorno de ejecución correspondiente.</span><span class="sxs-lookup"><span data-stu-id="207e8-103">If you install the .NET SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="207e8-104">Para instalar el SDK de .NET, ejecute los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="207e8-104">To install the .NET SDK, run the following commands:</span></span>

```bash
sudo dnf install dotnet-sdk-5.0
```

### <a name="install-the-runtime"></a><span data-ttu-id="207e8-105">Instalación de la instancia en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="207e8-105">Install the runtime</span></span>

<span data-ttu-id="207e8-106">El entorno de ejecución de ASP.NET Core le permite ejecutar aplicaciones creadas con .NET en las que no se ha proporcionado el entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="207e8-106">The ASP.NET Core Runtime allows you to run apps that were made with .NET that didn't provide the runtime.</span></span> <span data-ttu-id="207e8-107">Los comandos siguientes instalan el entorno de ejecución de ASP.NET Core, el más compatible con .NET.</span><span class="sxs-lookup"><span data-stu-id="207e8-107">The following commands install the ASP.NET Core Runtime, which is the most compatible runtime for .NET.</span></span> <span data-ttu-id="207e8-108">En el terminal, ejecute los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="207e8-108">In your terminal, run the following commands:</span></span>

```bash
sudo dnf install aspnetcore-runtime-5.0
```

<span data-ttu-id="207e8-109">Una alternativa al entorno de ejecución de ASP.NET Core es instalar el de .NET, que no incluye compatibilidad con ASP.NET Core; en el comando anterior, reemplace `aspnetcore-runtime-5.0` por `dotnet-runtime-5.0`:</span><span class="sxs-lookup"><span data-stu-id="207e8-109">As an alternative to the ASP.NET Core Runtime, you can install the .NET Runtime, which doesn't include ASP.NET Core support: replace `aspnetcore-runtime-5.0` in the previous command with `dotnet-runtime-5.0`:</span></span>

```bash
sudo dnf install dotnet-runtime-5.0
```
