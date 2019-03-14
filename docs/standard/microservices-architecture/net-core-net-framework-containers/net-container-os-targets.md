---
title: Selección del sistema operativo de destino con contenedores de .NET
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Selección del sistema operativo de destino con contenedores de .NET
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 01/07/2019
ms.openlocfilehash: 9e1d07e48d88376efb5fbdbdadc999c8dcd5082d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57374913"
---
# <a name="what-os-to-target-with-net-containers"></a><span data-ttu-id="55d78-103">Selección del sistema operativo de destino con contenedores de .NET</span><span class="sxs-lookup"><span data-stu-id="55d78-103">What OS to target with .NET containers</span></span>

<span data-ttu-id="55d78-104">Teniendo en cuenta la diversidad de sistemas operativos compatibles con Docker y las diferencias entre .NET Framework y .NET Core, debe escoger un sistema operativo de destino específico y versiones específicas según el marco que utilice.</span><span class="sxs-lookup"><span data-stu-id="55d78-104">Given the diversity of operating systems supported by Docker and the differences between .NET Framework and .NET Core, you should target a specific OS and specific versions depending on the framework you are using.</span></span>

<span data-ttu-id="55d78-105">Para Windows, puede usar Windows Server Core o Nano Server de Windows.</span><span class="sxs-lookup"><span data-stu-id="55d78-105">For Windows, you can use Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="55d78-106">Estas versiones de Windows proporcionan diferentes características (IIS en Windows Server Core frente a un servidor web autohospedado, como Kestrel, en Nano Server) que .NET Framework o .NET Core, respectivamente, podrían necesitar.</span><span class="sxs-lookup"><span data-stu-id="55d78-106">These Windows versions provide different characteristics (IIS in Windows Server Core versus a self-hosted web server like Kestrel in Nano Server) that might be needed by .NET Framework or .NET Core, respectively.</span></span>

<span data-ttu-id="55d78-107">Para Linux, hay varias distribuciones disponibles y compatibles en imágenes oficiales del Docker de .NET (por ejemplo, Debian).</span><span class="sxs-lookup"><span data-stu-id="55d78-107">For Linux, multiple distros are available and supported in official .NET Docker images (like Debian).</span></span>

<span data-ttu-id="55d78-108">En la Figura 3-1 se puede ver la posible versión de sistema operativo en función de la versión de .NET Framework que se utilice.</span><span class="sxs-lookup"><span data-stu-id="55d78-108">In Figure 3-1 you can see the possible OS version depending on the .NET framework used.</span></span>

![Al implementar aplicaciones heredadas de .NET Framework que tienen como destino Windows Server Core, compatible con aplicaciones heredadas e IIS, tiene una imagen más grande.](./media/image1.png)

<span data-ttu-id="55d78-113">**Figura 3-1.**</span><span class="sxs-lookup"><span data-stu-id="55d78-113">**Figure 3-1.**</span></span> <span data-ttu-id="55d78-114">Sistemas operativos de destino en función de las versiones de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="55d78-114">Operating systems to target depending on versions of the .NET framework</span></span>

<span data-ttu-id="55d78-115">También puede crear su propia imagen de Docker en los casos en que quiera utilizar una distribución de Linux diferente o que quiera una imagen con las versiones no proporcionadas por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="55d78-115">You can also create your own Docker image in cases where you want to use a different Linux distro or where you want an image with versions not provided by Microsoft.</span></span> <span data-ttu-id="55d78-116">Por ejemplo, puede crear una imagen con ASP.NET Core ejecutándose en los tradicionales .NET Framework y Windows Server Core, que no sería un escenario tan habitual para Docker.</span><span class="sxs-lookup"><span data-stu-id="55d78-116">For example, you might create an image with ASP.NET Core running on the traditional .NET Framework and Windows Server Core, which is a not-so-common scenario for Docker.</span></span>

<span data-ttu-id="55d78-117">Al agregar el nombre de imagen al archivo Dockerfile, puede seleccionar el sistema operativo y la versión dependiendo de la etiqueta que utilice, como en los ejemplos siguientes:</span><span class="sxs-lookup"><span data-stu-id="55d78-117">When you add the image name to your Dockerfile file, you can select the operating system and version depending on the tag you use, as in the following examples:</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="55d78-118">Imagen</span><span class="sxs-lookup"><span data-stu-id="55d78-118">Image</span></span></th>
<th><span data-ttu-id="55d78-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="55d78-119">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="55d78-120">microsoft/dotnet:2.2-runtime</span><span class="sxs-lookup"><span data-stu-id="55d78-120">microsoft/dotnet:2.2-runtime</span></span></td>
<td><span data-ttu-id="55d78-121">Arquitectura múltiple de .NET Core 2.2: es compatible con Linux y Windows Nano Server en función del host de Docker.</span><span class="sxs-lookup"><span data-stu-id="55d78-121">.NET Core 2.2 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="55d78-122">microsoft/dotnet:2.2-aspnetcore-runtime</span><span class="sxs-lookup"><span data-stu-id="55d78-122">microsoft/dotnet:2.2-aspnetcore-runtime</span></span></td>
<td><p><span data-ttu-id="55d78-123">Arquitectura múltiple de .NET Core 2.2: es compatible con Linux y Windows Nano Server en función del host de Docker.</span><span class="sxs-lookup"><span data-stu-id="55d78-123">ASP.NET Core 2.2 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.</span></span></p>
<p><span data-ttu-id="55d78-124">La imagen de aspnetcore tiene algunas optimizaciones para ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="55d78-124">The aspnetcore image has a few optimizations for ASP.NET Core.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="55d78-125">microsoft/dotnet:2.2-aspnetcore-runtime-alpine</span><span class="sxs-lookup"><span data-stu-id="55d78-125">microsoft/dotnet:2.2-aspnetcore-runtime-alpine</span></span></td>
<td><span data-ttu-id="55d78-126">.NET Core 2.2 solo en tiempo de ejecución en una distribución de Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="55d78-126">.NET Core 2.2 runtime-only on Linux Alpine distro</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="55d78-127">microsoft/dotnet:2.2-aspnetcore-runtime-nanoserver-1803</span><span class="sxs-lookup"><span data-stu-id="55d78-127">microsoft/dotnet:2.2-aspnetcore-runtime-nanoserver-1803</span></span></td>
<td><span data-ttu-id="55d78-128">.NET Core 2.2 solo en tiempo de ejecución en Windows Nano Server (Windows Server 1803)</span><span class="sxs-lookup"><span data-stu-id="55d78-128">.NET Core 2.2 runtime-only on Windows Nano Server (Windows Server version 1803)</span></span></td>
</tr>
</tbody>
</table>

> [!div class="step-by-step"]
> <span data-ttu-id="55d78-129">[Anterior](container-framework-choice-factors.md)
> [Siguiente](official-net-docker-images.md)</span><span class="sxs-lookup"><span data-stu-id="55d78-129">[Previous](container-framework-choice-factors.md)
[Next](official-net-docker-images.md)</span></span>