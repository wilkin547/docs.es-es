---
title: Selección del sistema operativo de destino con contenedores de .NET
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Selección del sistema operativo de destino con contenedores de .NET
ms.date: 01/07/2019
ms.openlocfilehash: 8bcfa0212f84c575a63f76e05edec1e511cadc36
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "72772001"
---
# <a name="what-os-to-target-with-net-containers"></a><span data-ttu-id="c0d21-103">Selección del sistema operativo de destino con contenedores de .NET</span><span class="sxs-lookup"><span data-stu-id="c0d21-103">What OS to target with .NET containers</span></span>

<span data-ttu-id="c0d21-104">Teniendo en cuenta la diversidad de sistemas operativos compatibles con Docker y las diferencias entre .NET Framework y .NET Core, debe escoger un sistema operativo de destino específico y versiones específicas según el marco que utilice.</span><span class="sxs-lookup"><span data-stu-id="c0d21-104">Given the diversity of operating systems supported by Docker and the differences between .NET Framework and .NET Core, you should target a specific OS and specific versions depending on the framework you are using.</span></span>

<span data-ttu-id="c0d21-105">Para Windows, puede usar Windows Server Core o Nano Server de Windows.</span><span class="sxs-lookup"><span data-stu-id="c0d21-105">For Windows, you can use Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="c0d21-106">Estas versiones de Windows proporcionan diferentes características (IIS en Windows Server Core frente a un servidor web autohospedado, como Kestrel, en Nano Server) que .NET Framework o .NET Core, respectivamente, podrían necesitar.</span><span class="sxs-lookup"><span data-stu-id="c0d21-106">These Windows versions provide different characteristics (IIS in Windows Server Core versus a self-hosted web server like Kestrel in Nano Server) that might be needed by .NET Framework or .NET Core, respectively.</span></span>

<span data-ttu-id="c0d21-107">Para Linux, hay varias distribuciones disponibles y compatibles en imágenes oficiales del Docker de .NET (por ejemplo, Debian).</span><span class="sxs-lookup"><span data-stu-id="c0d21-107">For Linux, multiple distros are available and supported in official .NET Docker images (like Debian).</span></span>

<span data-ttu-id="c0d21-108">En la Figura 3-1 se puede ver la posible versión de sistema operativo en función de la versión de .NET Framework que se utilice.</span><span class="sxs-lookup"><span data-stu-id="c0d21-108">In Figure 3-1 you can see the possible OS version depending on the .NET framework used.</span></span>

![Al implementar aplicaciones heredadas de .NET Framework que tienen como destino Windows Server Core, compatible con aplicaciones heredadas e IIS, tiene una imagen más grande.](./media/image1.png)

<span data-ttu-id="c0d21-113">**Figura 3-1.**</span><span class="sxs-lookup"><span data-stu-id="c0d21-113">**Figure 3-1.**</span></span> <span data-ttu-id="c0d21-114">Sistemas operativos de destino en función de las versiones de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c0d21-114">Operating systems to target depending on versions of the .NET framework</span></span>

<span data-ttu-id="c0d21-115">También puede crear su propia imagen de Docker en los casos en que quiera utilizar una distribución de Linux diferente o que quiera una imagen con las versiones no proporcionadas por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c0d21-115">You can also create your own Docker image in cases where you want to use a different Linux distro or where you want an image with versions not provided by Microsoft.</span></span> <span data-ttu-id="c0d21-116">Por ejemplo, puede crear una imagen con ASP.NET Core ejecutándose en los tradicionales .NET Framework y Windows Server Core, que no sería un escenario tan habitual para Docker.</span><span class="sxs-lookup"><span data-stu-id="c0d21-116">For example, you might create an image with ASP.NET Core running on the traditional .NET Framework and Windows Server Core, which is a not-so-common scenario for Docker.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c0d21-117">Al usar imágenes de Windows Server Core, es posible que falten algunos archivos DLL cuando se comparan con Imágenes de Windows completas.</span><span class="sxs-lookup"><span data-stu-id="c0d21-117">When using Windows Server Core images, you might find that some DLLs are missing, when compared to full Windows images.</span></span> <span data-ttu-id="c0d21-118">Es posible que pueda resolver este problema mediante la creación de una imagen de Server Core personalizada, agregando los archivos que faltan en el momento de la compilación de la imagen, tal como se ja mencionado en este [comentario de GitHub](https://github.com/microsoft/dotnet-framework-docker/issues/299#issuecomment-511537448).</span><span class="sxs-lookup"><span data-stu-id="c0d21-118">You might be able to solve this problem by creating a custom Server Core image, adding the missing files at image build time, as mentioned in this [GitHub comment](https://github.com/microsoft/dotnet-framework-docker/issues/299#issuecomment-511537448).</span></span>

<span data-ttu-id="c0d21-119">Al agregar el nombre de imagen al archivo Dockerfile, puede seleccionar el sistema operativo y la versión dependiendo de la etiqueta que utilice, como en los ejemplos siguientes:</span><span class="sxs-lookup"><span data-stu-id="c0d21-119">When you add the image name to your Dockerfile file, you can select the operating system and version depending on the tag you use, as in the following examples:</span></span>

| <span data-ttu-id="c0d21-120">Imagen</span><span class="sxs-lookup"><span data-stu-id="c0d21-120">Image</span></span> | <span data-ttu-id="c0d21-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c0d21-121">Comments</span></span> |
|-------|----------|
| <span data-ttu-id="c0d21-122">mcr.microsoft.com/dotnet/core/runtime:2.2</span><span class="sxs-lookup"><span data-stu-id="c0d21-122">mcr.microsoft.com/dotnet/core/runtime:2.2</span></span> | <span data-ttu-id="c0d21-123">Arquitectura múltiple de .NET Core 2.2: es compatible con Linux y Windows Nano Server en función del host de Docker.</span><span class="sxs-lookup"><span data-stu-id="c0d21-123">.NET Core 2.2 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.</span></span> |
| <span data-ttu-id="c0d21-124">mcr.microsoft.com/dotnet/core/aspnet:2.2</span><span class="sxs-lookup"><span data-stu-id="c0d21-124">mcr.microsoft.com/dotnet/core/aspnet:2.2</span></span> | <span data-ttu-id="c0d21-125">Arquitectura múltiple de .NET Core 2.2: es compatible con Linux y Windows Nano Server en función del host de Docker.</span><span class="sxs-lookup"><span data-stu-id="c0d21-125">ASP.NET Core 2.2 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.</span></span> <br/> <span data-ttu-id="c0d21-126">La imagen de aspnetcore tiene algunas optimizaciones para ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="c0d21-126">The aspnetcore image has a few optimizations for ASP.NET Core.</span></span> |
| <span data-ttu-id="c0d21-127">mcr.microsoft.com/dotnet/core/aspnet:2.2-alpine</span><span class="sxs-lookup"><span data-stu-id="c0d21-127">mcr.microsoft.com/dotnet/core/aspnet:2.2-alpine</span></span> | <span data-ttu-id="c0d21-128">.NET Core 2.2 solo en tiempo de ejecución en una distribución de Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="c0d21-128">.NET Core 2.2 runtime-only on Linux Alpine distro</span></span> |
| <span data-ttu-id="c0d21-129">mcr.microsoft.com/dotnet/core/aspnet:2.2-nanoserver-1803</span><span class="sxs-lookup"><span data-stu-id="c0d21-129">mcr.microsoft.com/dotnet/core/aspnet:2.2-nanoserver-1803</span></span> | <span data-ttu-id="c0d21-130">.NET Core 2.2 solo en tiempo de ejecución en Windows Nano Server (Windows Server 1803)</span><span class="sxs-lookup"><span data-stu-id="c0d21-130">.NET Core 2.2 runtime-only on Windows Nano Server (Windows Server version 1803)</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="c0d21-131">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="c0d21-131">Additional resources</span></span>

- <span data-ttu-id="c0d21-132">**Se produce un error en BitmapDecoder debido a que falta WindowsCodecsExt.dll (incidencia de GitHub)** .</span><span class="sxs-lookup"><span data-stu-id="c0d21-132">**BitmapDecoder fails due to missing WindowsCodecsExt.dll (GitHub issue)**</span></span>  
  <https://github.com/microsoft/dotnet-framework-docker/issues/299>

> [!div class="step-by-step"]
> <span data-ttu-id="c0d21-133">[Anterior](container-framework-choice-factors.md)
> [Siguiente](official-net-docker-images.md)</span><span class="sxs-lookup"><span data-stu-id="c0d21-133">[Previous](container-framework-choice-factors.md)
[Next](official-net-docker-images.md)</span></span>
