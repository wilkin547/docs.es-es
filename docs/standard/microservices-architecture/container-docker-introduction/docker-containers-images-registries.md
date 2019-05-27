---
title: Contenedores, imágenes y registros de Docker
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Contenedores, imágenes y registros de Docker
ms.date: 08/31/2018
ms.openlocfilehash: 520f8d4d54f1fdd227ff9a1e88660b62e75f927f
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65639908"
---
# <a name="docker-containers-images-and-registries"></a><span data-ttu-id="cc034-103">Contenedores, imágenes y registros de Docker</span><span class="sxs-lookup"><span data-stu-id="cc034-103">Docker containers, images, and registries</span></span>

<span data-ttu-id="cc034-104">Al usar Docker, un desarrollador crea una aplicación o un servicio y lo empaqueta, junto con sus dependencias, en una imagen de contenedor.</span><span class="sxs-lookup"><span data-stu-id="cc034-104">When using Docker, a developer creates an app or service and packages it and its dependencies into a container image.</span></span> <span data-ttu-id="cc034-105">Una imagen es una representación estática de la aplicación o el servicio y de su configuración y las dependencias.</span><span class="sxs-lookup"><span data-stu-id="cc034-105">An image is a static representation of the app or service and its configuration and dependencies.</span></span>

<span data-ttu-id="cc034-106">Para ejecutar la aplicación o el servicio, se crea una instancia de la imagen de la aplicación para crear un contenedor, que se ejecutará en el host de Docker.</span><span class="sxs-lookup"><span data-stu-id="cc034-106">To run the app or service, the app's image is instantiated to create a container, which will be running on the Docker host.</span></span> <span data-ttu-id="cc034-107">Inicialmente, los contenedores se prueban en un entorno de desarrollo o un PC.</span><span class="sxs-lookup"><span data-stu-id="cc034-107">Containers are initially tested in a development environment or PC.</span></span>

<span data-ttu-id="cc034-108">Los desarrolladores deben almacenar las imágenes en un registro, que actúa como una biblioteca de imágenes y es necesario cuando se implementa en orquestadores de producción.</span><span class="sxs-lookup"><span data-stu-id="cc034-108">Developers should store images in a registry, which acts as a library of images and is needed when deploying to production orchestrators.</span></span> <span data-ttu-id="cc034-109">Docker mantiene un registro público a través de [Docker Hub](https://hub.docker.com/); otros proveedores ofrecen registros para distintas colecciones de imágenes, incluido [Azure Container Registry](https://azure.microsoft.com/services/container-registry/).</span><span class="sxs-lookup"><span data-stu-id="cc034-109">Docker maintains a public registry via [Docker Hub](https://hub.docker.com/); other vendors provide registries for different collections of images, including [Azure Container Registry](https://azure.microsoft.com/services/container-registry/).</span></span> <span data-ttu-id="cc034-110">Como alternativa, las empresas pueden tener un registro privado local para sus propias imágenes de Docker.</span><span class="sxs-lookup"><span data-stu-id="cc034-110">Alternatively, enterprises can have a private registry on-premises for their own Docker images.</span></span>

<span data-ttu-id="cc034-111">En la figura 2-4 se muestra cómo se relacionan las imágenes y los registros de Docker con otros componentes.</span><span class="sxs-lookup"><span data-stu-id="cc034-111">Figure 2-4 shows how images and registries in Docker relate to other components.</span></span> <span data-ttu-id="cc034-112">También se muestran las diversas ofertas de registro de los proveedores.</span><span class="sxs-lookup"><span data-stu-id="cc034-112">It also shows the multiple registry offerings from vendors.</span></span>

![Taxonomía básica en Docker: el registro es como una estantería donde las imágenes se almacenan y están disponibles para extraerlas con el fin de compilar contenedores que ejecuten servicios o aplicaciones web.](./media/image5.PNG)

<span data-ttu-id="cc034-117">**Figura 2-4**.</span><span class="sxs-lookup"><span data-stu-id="cc034-117">**Figure 2-4**.</span></span> <span data-ttu-id="cc034-118">Taxonomía de términos de Docker y conceptos</span><span class="sxs-lookup"><span data-stu-id="cc034-118">Taxonomy of Docker terms and concepts</span></span>

<span data-ttu-id="cc034-119">Colocar imágenes en un registro le permite almacenar fragmentos de la aplicación que son estáticos e inmutables, incluidas todas sus dependencias a nivel de marco.</span><span class="sxs-lookup"><span data-stu-id="cc034-119">Putting images in a registry lets you store static and immutable application bits, including all their dependencies at a framework level.</span></span> <span data-ttu-id="cc034-120">Después, esas imágenes se pueden versionear e implementar en varios entornos y, por tanto, proporcionar una unidad de implementación coherente.</span><span class="sxs-lookup"><span data-stu-id="cc034-120">Those images can then be versioned and deployed in multiple environments and therefore provide a consistent deployment unit.</span></span>

<span data-ttu-id="cc034-121">Los registros de imágenes privados, ya sean hospedados localmente o en la nube, se recomiendan cuando:</span><span class="sxs-lookup"><span data-stu-id="cc034-121">Private image registries, either hosted on-premises or in the cloud, are recommended when:</span></span>

- <span data-ttu-id="cc034-122">Las imágenes no deben compartirse públicamente por motivos de confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="cc034-122">Your images must not be shared publicly due to confidentiality.</span></span>

- <span data-ttu-id="cc034-123">Quiere tener una latencia de red mínima entre las imágenes y el entorno de implementación elegido.</span><span class="sxs-lookup"><span data-stu-id="cc034-123">You want to have minimum network latency between your images and your chosen deployment environment.</span></span> <span data-ttu-id="cc034-124">Por ejemplo, si el entorno de producción es la nube de Azure, probablemente quiera almacenar las imágenes en [Azure Container Registry](https://azure.microsoft.com/services/container-registry/), para que la latencia de red sea mínima.</span><span class="sxs-lookup"><span data-stu-id="cc034-124">For example, if your production environment is Azure cloud, you probably want to store your images in [Azure Container Registry](https://azure.microsoft.com/services/container-registry/) so that network latency will be minimal.</span></span> <span data-ttu-id="cc034-125">De forma similar, si el entorno de producción es local, puede tener un registro de confianza de Docker local disponible dentro de la misma red local.</span><span class="sxs-lookup"><span data-stu-id="cc034-125">In a similar way, if your production environment is on-premises, you might want to have an on-premises Docker Trusted Registry available within the same local network.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="cc034-126">[Anterior](docker-terminology.md)
>[Siguiente](../net-core-net-framework-containers/index.md)</span><span class="sxs-lookup"><span data-stu-id="cc034-126">[Previous](docker-terminology.md)
[Next](../net-core-net-framework-containers/index.md)</span></span>
