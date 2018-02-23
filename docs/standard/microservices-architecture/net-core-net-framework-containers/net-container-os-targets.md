---
title: "Selección del sistema operativo de destino con contenedores de .NET"
description: "Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Selección del sistema operativo de destino con contenedores de .NET"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ef7a21efa23be3a5181f08066a093abbb915c20f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="what-os-to-target-with-net-containers"></a><span data-ttu-id="1936d-104">Selección del sistema operativo de destino con contenedores de .NET</span><span class="sxs-lookup"><span data-stu-id="1936d-104">What OS to target with .NET containers</span></span>

<span data-ttu-id="1936d-105">Teniendo en cuenta la diversidad de sistemas operativos compatibles con Docker y las diferencias entre .NET Framework y .NET Core, debe escoger un sistema operativo de destino específico y versiones específicas según el marco que utilice.</span><span class="sxs-lookup"><span data-stu-id="1936d-105">Given the diversity of operating systems supported by Docker and the differences between .NET Framework and .NET Core, you should target a specific OS and specific versions depending on the framework you are using.</span></span> 

<span data-ttu-id="1936d-106">Para Windows, puede usar Windows Server Core o Nano Server de Windows.</span><span class="sxs-lookup"><span data-stu-id="1936d-106">For Windows, you can use Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="1936d-107">Estas versiones de Windows proporcionan diferentes características (IIS en Windows Server Core frente a un servidor web autohospedado, como Kestrel, en Nano Server) que .NET Framework o .NET Core, respectivamente, podrían necesitar.</span><span class="sxs-lookup"><span data-stu-id="1936d-107">These Windows versions provide different characteristics (IIS in Windows Server Core versus a self-hosted web server like Kestrel in Nano Server) that might be needed by .NET Framework or .NET Core, respectively.</span></span> 

<span data-ttu-id="1936d-108">Para Linux, hay varias distribuciones disponibles y compatibles en imágenes oficiales del Docker de .NET (por ejemplo, Debian).</span><span class="sxs-lookup"><span data-stu-id="1936d-108">For Linux, multiple distros are available and supported in official .NET Docker images (like Debian).</span></span>

<span data-ttu-id="1936d-109">En la Figura 3-1 se puede ver la posible versión de sistema operativo en función de la versión de .NET Framework que se utilice.</span><span class="sxs-lookup"><span data-stu-id="1936d-109">In Figure 3-1 you can see the possible OS version depending on the .NET framework used.</span></span>

![](./media/image1.png)

<span data-ttu-id="1936d-110">**Figura 3-1.**</span><span class="sxs-lookup"><span data-stu-id="1936d-110">**Figure 3-1.**</span></span> <span data-ttu-id="1936d-111">Sistemas operativos de destino en función de las versiones de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1936d-111">Operating systems to target depending on versions of the .NET framework</span></span>

<span data-ttu-id="1936d-112">También puede crear su propia imagen de Docker en los casos en que quiera utilizar una distribución de Linux diferente o que quiera una imagen con las versiones no proporcionadas por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1936d-112">You can also create your own Docker image in cases where you want to use a different Linux distro or where you want an image with versions not provided by Microsoft.</span></span> <span data-ttu-id="1936d-113">Por ejemplo, puede crear una imagen con ASP.NET Core ejecutándose en los tradicionales .NET Framework y Windows Server Core, que no sería un escenario tan habitual para Docker.</span><span class="sxs-lookup"><span data-stu-id="1936d-113">For example, you might create an image with ASP.NET Core running on the traditional .NET Framework and Windows Server Core, which is a not-so-common scenario for Docker.</span></span>

<span data-ttu-id="1936d-114">Al agregar el nombre de imagen al archivo Dockerfile, puede seleccionar el sistema operativo y la versión dependiendo de la etiqueta que utilice, como en los ejemplos siguientes:</span><span class="sxs-lookup"><span data-stu-id="1936d-114">When you add the image name to your Dockerfile file, you can select the operating system and version depending on the tag you use, as in the following examples:</span></span>

-   <span data-ttu-id="1936d-115">microsoft/**dotnet:2.0.0-runtime-jessie**</span><span class="sxs-lookup"><span data-stu-id="1936d-115">microsoft/**dotnet:2.0.0-runtime-jessie**</span></span>

        .NET Core 2.0 runtime-only on Linux

-   <span data-ttu-id="1936d-116">microsoft/**dotnet:2.0.0-runtime-nanoserver-1709**</span><span class="sxs-lookup"><span data-stu-id="1936d-116">microsoft/**dotnet:2.0.0-runtime-nanoserver-1709**</span></span> 

        .NET Core 2.0 runtime-only on Windows Nano Server (Windows Server 2016 Fall Creators Update version 1709)

-   <span data-ttu-id="1936d-117">microsoft/**aspnetcore:2.0**</span><span class="sxs-lookup"><span data-stu-id="1936d-117">microsoft/**aspnetcore:2.0**</span></span>
    
        .NET Core 2.0 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.
        The aspnetcore image has a few optimizations for ASP.NET Core. 





>[!div class="step-by-step"]
<span data-ttu-id="1936d-118">[Anterior] (container-framework-choice-factors.md) [Siguiente] (official-net-docker-images.md)</span><span class="sxs-lookup"><span data-stu-id="1936d-118">[Previous] (container-framework-choice-factors.md) [Next] (official-net-docker-images.md)</span></span>
