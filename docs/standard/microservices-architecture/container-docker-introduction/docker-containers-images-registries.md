---
title: "Registros, imágenes y contenedores de docker"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Registros, imágenes y contenedores de docker"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 224fed34f06d10760b14aa9ecbae6c0e912915cf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="docker-containers-images-and-registries"></a><span data-ttu-id="df4b3-104">Registros, imágenes y contenedores de docker</span><span class="sxs-lookup"><span data-stu-id="df4b3-104">Docker containers, images, and registries</span></span>

<span data-ttu-id="df4b3-105">Al usar Docker, un desarrollador crea una aplicación o servicio y paquetes y sus dependencias en una imagen de contenedor.</span><span class="sxs-lookup"><span data-stu-id="df4b3-105">When using Docker, a developer creates an app or service and packages it and its dependencies into a container image.</span></span> <span data-ttu-id="df4b3-106">Una imagen es una representación estática de la aplicación o el servicio y su configuración y las dependencias.</span><span class="sxs-lookup"><span data-stu-id="df4b3-106">An image is a static representation of the app or service and its configuration and dependencies.</span></span>

<span data-ttu-id="df4b3-107">Para ejecutar la aplicación o servicio, se crea una instancia de imagen de la aplicación para crear un contenedor, que se ejecutarán en el host Docker.</span><span class="sxs-lookup"><span data-stu-id="df4b3-107">To run the app or service, the app’s image is instantiated to create a container, which will be running on the Docker host.</span></span> <span data-ttu-id="df4b3-108">Inicialmente se admiten los contenedores en un entorno de desarrollo o PC.</span><span class="sxs-lookup"><span data-stu-id="df4b3-108">Containers are initially tested in a development environment or PC.</span></span>

<span data-ttu-id="df4b3-109">Los desarrolladores deben almacenar imágenes en un registro, que actúa como una biblioteca de imágenes y es necesario cuando se implementa en orchestrators de producción.</span><span class="sxs-lookup"><span data-stu-id="df4b3-109">Developers should store images in a registry, which acts as a library of images and is needed when deploying to production orchestrators.</span></span> <span data-ttu-id="df4b3-110">Mantiene un registro público a través de docker [Docker Hub](https://hub.docker.com/); otros proveedores ofrecen registros para las diferentes colecciones de imágenes.</span><span class="sxs-lookup"><span data-stu-id="df4b3-110">Docker maintains a public registry via [Docker Hub](https://hub.docker.com/); other vendors provide registries for different collections of images.</span></span> <span data-ttu-id="df4b3-111">Como alternativa, las empresas pueden tener un registro privado local para sus propias imágenes de Docker.</span><span class="sxs-lookup"><span data-stu-id="df4b3-111">Alternatively, enterprises can have a private registry on-premises for their own Docker images.</span></span>

<span data-ttu-id="df4b3-112">Figura 2-4 muestra cómo se relacionan las imágenes y los registros en Docker con otros componentes.</span><span class="sxs-lookup"><span data-stu-id="df4b3-112">Figure 2-4 shows how images and registries in Docker relate to other components.</span></span> <span data-ttu-id="df4b3-113">También muestra las varias ofertas de registro de proveedores.</span><span class="sxs-lookup"><span data-stu-id="df4b3-113">It also shows the multiple registry offerings from vendors.</span></span>

![](./media/image5.PNG)

<span data-ttu-id="df4b3-114">**Figura 2-4**.</span><span class="sxs-lookup"><span data-stu-id="df4b3-114">**Figure 2-4**.</span></span> <span data-ttu-id="df4b3-115">Taxonomía de términos de Docker y conceptos</span><span class="sxs-lookup"><span data-stu-id="df4b3-115">Taxonomy of Docker terms and concepts</span></span>

<span data-ttu-id="df4b3-116">Colocar imágenes en un registro le permite almacenar fragmentos de la aplicación estáticos e inmutable, incluidas todas sus dependencias en un nivel de marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="df4b3-116">Putting images in a registry lets you store static and immutable application bits, including all their dependencies at a framework level.</span></span> <span data-ttu-id="df4b3-117">Esas imágenes pueden ser, a continuación, con control de versiones e implementado en varios entornos y, por tanto, proporcionar una unidad de implementación coherente.</span><span class="sxs-lookup"><span data-stu-id="df4b3-117">Those images can then be versioned and deployed in multiple environments and therefore provide a consistent deployment unit.</span></span>

<span data-ttu-id="df4b3-118">Registros de imagen privada, hospedado en local o en la nube, se recomienda cuando:</span><span class="sxs-lookup"><span data-stu-id="df4b3-118">Private image registries, either hosted on-premises or in the cloud, are recommended when:</span></span>

-   <span data-ttu-id="df4b3-119">Las imágenes no deben compartirse públicamente debido a la confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="df4b3-119">Your images must not be shared publicly due to confidentiality.</span></span>

-   <span data-ttu-id="df4b3-120">Desea tener una latencia de red mínimas entre las imágenes y el entorno de implementación elegido.</span><span class="sxs-lookup"><span data-stu-id="df4b3-120">You want to have minimum network latency between your images and your chosen deployment environment.</span></span> <span data-ttu-id="df4b3-121">Por ejemplo, si el entorno de producción es la nube de Azure, probablemente desee almacenar las imágenes en el registro de contenedor de Azure para que la latencia de red será mínima.</span><span class="sxs-lookup"><span data-stu-id="df4b3-121">For example, if your production environment is Azure cloud, you probably want to store your images in Azure Container Registry so that network latency will be minimal.</span></span> <span data-ttu-id="df4b3-122">De forma similar, si el entorno de producción es local, puede tener un local Docker registro de confianza disponibles dentro de la misma red local.</span><span class="sxs-lookup"><span data-stu-id="df4b3-122">In a similar way, if your production environment is on-premises, you might want to have an on-premises Docker Trusted Registry available within the same local network.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="df4b3-123">[Anterior] (docker-terminology.md) [siguiente] (.. /NET-Core-NET-Framework-Containers/index.MD)</span><span class="sxs-lookup"><span data-stu-id="df4b3-123">[Previous] (docker-terminology.md) [Next] (../net-core-net-framework-containers/index.md)</span></span>
