---
title: Contenedores, imágenes y registros de Docker
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Contenedores, imágenes y registros de Docker
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 02ee40ebab37ae1898dc46e215728cba512a23e0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33574091"
---
# <a name="docker-containers-images-and-registries"></a><span data-ttu-id="55589-103">Contenedores, imágenes y registros de Docker</span><span class="sxs-lookup"><span data-stu-id="55589-103">Docker containers, images, and registries</span></span>

<span data-ttu-id="55589-104">Al usar Docker, un desarrollador crea una aplicación o un servicio y lo empaqueta, junto con sus dependencias, en una imagen de contenedor.</span><span class="sxs-lookup"><span data-stu-id="55589-104">When using Docker, a developer creates an app or service and packages it and its dependencies into a container image.</span></span> <span data-ttu-id="55589-105">Una imagen es una representación estática de la aplicación o el servicio y de su configuración y las dependencias.</span><span class="sxs-lookup"><span data-stu-id="55589-105">An image is a static representation of the app or service and its configuration and dependencies.</span></span>

<span data-ttu-id="55589-106">Para ejecutar la aplicación o el servicio, se crea una instancia de la imagen de la aplicación para crear un contenedor, que se ejecutará en el host de Docker.</span><span class="sxs-lookup"><span data-stu-id="55589-106">To run the app or service, the app’s image is instantiated to create a container, which will be running on the Docker host.</span></span> <span data-ttu-id="55589-107">Inicialmente, los contenedores se prueban en un entorno de desarrollo o un PC.</span><span class="sxs-lookup"><span data-stu-id="55589-107">Containers are initially tested in a development environment or PC.</span></span>

<span data-ttu-id="55589-108">Los desarrolladores deben almacenar las imágenes en un registro, que actúa como una biblioteca de imágenes y es necesario cuando se implementa en orquestadores de producción.</span><span class="sxs-lookup"><span data-stu-id="55589-108">Developers should store images in a registry, which acts as a library of images and is needed when deploying to production orchestrators.</span></span> <span data-ttu-id="55589-109">Docker mantiene un registro público a través de [Docker Hub](https://hub.docker.com/); otros proveedores ofrecen registros para distintas colecciones de imágenes.</span><span class="sxs-lookup"><span data-stu-id="55589-109">Docker maintains a public registry via [Docker Hub](https://hub.docker.com/); other vendors provide registries for different collections of images.</span></span> <span data-ttu-id="55589-110">Como alternativa, las empresas pueden tener un registro privado local para sus propias imágenes de Docker.</span><span class="sxs-lookup"><span data-stu-id="55589-110">Alternatively, enterprises can have a private registry on-premises for their own Docker images.</span></span>

<span data-ttu-id="55589-111">En la figura 2-4 se muestra cómo se relacionan las imágenes y los registros de Docker con otros componentes.</span><span class="sxs-lookup"><span data-stu-id="55589-111">Figure 2-4 shows how images and registries in Docker relate to other components.</span></span> <span data-ttu-id="55589-112">También se muestran las diversas ofertas de registro de los proveedores.</span><span class="sxs-lookup"><span data-stu-id="55589-112">It also shows the multiple registry offerings from vendors.</span></span>

![](./media/image5.PNG)

<span data-ttu-id="55589-113">**Figura 2-4**.</span><span class="sxs-lookup"><span data-stu-id="55589-113">**Figure 2-4**.</span></span> <span data-ttu-id="55589-114">Taxonomía de términos de Docker y conceptos</span><span class="sxs-lookup"><span data-stu-id="55589-114">Taxonomy of Docker terms and concepts</span></span>

<span data-ttu-id="55589-115">Colocar imágenes en un registro le permite almacenar fragmentos de la aplicación que son estáticos e inmutables, incluidas todas sus dependencias a nivel de marco.</span><span class="sxs-lookup"><span data-stu-id="55589-115">Putting images in a registry lets you store static and immutable application bits, including all their dependencies at a framework level.</span></span> <span data-ttu-id="55589-116">Después, esas imágenes se pueden versionear e implementar en varios entornos y, por tanto, proporcionar una unidad de implementación coherente.</span><span class="sxs-lookup"><span data-stu-id="55589-116">Those images can then be versioned and deployed in multiple environments and therefore provide a consistent deployment unit.</span></span>

<span data-ttu-id="55589-117">Los registros de imágenes privados, ya sean hospedados localmente o en la nube, se recomiendan cuando:</span><span class="sxs-lookup"><span data-stu-id="55589-117">Private image registries, either hosted on-premises or in the cloud, are recommended when:</span></span>

-   <span data-ttu-id="55589-118">Las imágenes no deben compartirse públicamente por motivos de confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="55589-118">Your images must not be shared publicly due to confidentiality.</span></span>

-   <span data-ttu-id="55589-119">Quiere tener una latencia de red mínima entre las imágenes y el entorno de implementación elegido.</span><span class="sxs-lookup"><span data-stu-id="55589-119">You want to have minimum network latency between your images and your chosen deployment environment.</span></span> <span data-ttu-id="55589-120">Por ejemplo, si el entorno de producción es la nube de Azure, probablemente quiera almacenar las imágenes en Azure Container Registry, para que la latencia de red sea mínima.</span><span class="sxs-lookup"><span data-stu-id="55589-120">For example, if your production environment is Azure cloud, you probably want to store your images in Azure Container Registry so that network latency will be minimal.</span></span> <span data-ttu-id="55589-121">De forma similar, si el entorno de producción es local, puede tener un registro de confianza de Docker local disponible dentro de la misma red local.</span><span class="sxs-lookup"><span data-stu-id="55589-121">In a similar way, if your production environment is on-premises, you might want to have an on-premises Docker Trusted Registry available within the same local network.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="55589-122">[Previous] (docker-terminology.md) [Next] (../net-core-net-framework-containers/index.md)</span><span class="sxs-lookup"><span data-stu-id="55589-122">[Previous] (docker-terminology.md) [Next] (../net-core-net-framework-containers/index.md)</span></span>
