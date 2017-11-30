---
title: "¿Qué sistema operativo al destino con contenedores de .NET"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | ¿Qué sistema operativo al destino con contenedores de .NET"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 828ccb5e7a76f9419e80793b6cb3a6ba24f358cf
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="what-os-to-target-with-net-containers"></a><span data-ttu-id="c9cda-104">¿Qué sistema operativo al destino con contenedores de .NET</span><span class="sxs-lookup"><span data-stu-id="c9cda-104">What OS to target with .NET containers</span></span>

<span data-ttu-id="c9cda-105">Teniendo en cuenta la diversidad de sistemas operativos compatibles con Docker y las diferencias entre .NET Framework y .NET Core, debe tener como destino un sistema operativo específico y las versiones específicas según el marco de trabajo que usa.</span><span class="sxs-lookup"><span data-stu-id="c9cda-105">Given the diversity of operating systems supported by Docker and the differences between .NET Framework and .NET Core, you should target a specific OS and specific versions depending on the framework you are using.</span></span> 

<span data-ttu-id="c9cda-106">Para Windows, puede usar Windows Server Core o Nano Server de Windows.</span><span class="sxs-lookup"><span data-stu-id="c9cda-106">For Windows, you can use Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="c9cda-107">Estas versiones de Windows proporcionan diferentes características (IIS en Windows Server Core frente a un servidor web hospedado por sí mismo como Kestrel en Nano Server) que podrían ser necesarios en .NET Framework o .NET Core, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="c9cda-107">These Windows versions provide different characteristics (IIS in Windows Server Core versus a self-hosted web server like Kestrel in Nano Server) that might be needed by .NET Framework or .NET Core, respectively.</span></span> 

<span data-ttu-id="c9cda-108">Para Linux, varias distribuciones están disponibles y sea compatible con imágenes de Docker .NET oficiales (por ejemplo, Debian).</span><span class="sxs-lookup"><span data-stu-id="c9cda-108">For Linux, multiple distros are available and supported in official .NET Docker images (like Debian).</span></span>

<span data-ttu-id="c9cda-109">En la figura 3-1 puede ver la versión del SO posibles dependiendo de .NET framework que utiliza.</span><span class="sxs-lookup"><span data-stu-id="c9cda-109">In Figure 3-1 you can see the possible OS version depending on the .NET framework used.</span></span>

![](./media/image1.png)

<span data-ttu-id="c9cda-110">**Figura 3-1.**</span><span class="sxs-lookup"><span data-stu-id="c9cda-110">**Figure 3-1.**</span></span> <span data-ttu-id="c9cda-111">Sistemas operativos en función de las versiones de .NET framework de destino</span><span class="sxs-lookup"><span data-stu-id="c9cda-111">Operating systems to target depending on versions of the .NET framework</span></span>

<span data-ttu-id="c9cda-112">También puede crear su propia imagen de Docker en los casos donde desea utilizar una distribución de Linux diferente o donde quiere una imagen con las versiones no proporcionadas por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c9cda-112">You can also create your own Docker image in cases where you want to use a different Linux distro or where you want an image with versions not provided by Microsoft.</span></span> <span data-ttu-id="c9cda-113">Por ejemplo, podría crear una imagen con ASP.NET Core que se ejecutan en .NET Framework y Windows Server Core, que es un escenario no tan comunes para Docker tradicional.</span><span class="sxs-lookup"><span data-stu-id="c9cda-113">For example, you might create an image with ASP.NET Core running on the traditional .NET Framework and Windows Server Core, which is a not-so-common scenario for Docker.</span></span>

<span data-ttu-id="c9cda-114">Cuando se agrega el nombre de imagen en el archivo Dockerfile, puede seleccionar el sistema operativo y la versión en función de la etiqueta que se utiliza, como en los ejemplos siguientes:</span><span class="sxs-lookup"><span data-stu-id="c9cda-114">When you add the image name to your Dockerfile file, you can select the operating system and version depending on the tag you use, as in the following examples:</span></span>

-   <span data-ttu-id="c9cda-115">Microsoft /**dotnet:2.0.0-tiempo de ejecución-jessie**</span><span class="sxs-lookup"><span data-stu-id="c9cda-115">microsoft/**dotnet:2.0.0-runtime-jessie**</span></span>

        .NET Core 2.0 runtime-only on Linux

-   <span data-ttu-id="c9cda-116">Microsoft /**dotnet:2.0.0-tiempo de ejecución-nanoserver-1709**</span><span class="sxs-lookup"><span data-stu-id="c9cda-116">microsoft/**dotnet:2.0.0-runtime-nanoserver-1709**</span></span> 

        .NET Core 2.0 runtime-only on Windows Nano Server (Windows Server 2016 Fall Creators Update version 1709)

-   <span data-ttu-id="c9cda-117">Microsoft /**aspnetcore:2.0**</span><span class="sxs-lookup"><span data-stu-id="c9cda-117">microsoft/**aspnetcore:2.0**</span></span>
    
        .NET Core 2.0 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.
        The aspnetcore image has a few optimizations for ASP.NET Core. 





>[!div class="step-by-step"]
<span data-ttu-id="c9cda-118">[Anterior] (contenedor-framework-elección-factors.md) [siguiente] (oficial-net-docker-images.md)</span><span class="sxs-lookup"><span data-stu-id="c9cda-118">[Previous] (container-framework-choice-factors.md) [Next] (official-net-docker-images.md)</span></span>
