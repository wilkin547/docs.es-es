---
title: Contenedores, imágenes y registros de Docker
description: Obtenga información sobre el papel fundamental que los registros de reproducirán generales de la manera de Docker de la implementación de aplicaciones.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: e69490734a03cf58bf8534bc9e31110a11d44c58
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61795335"
---
# <a name="docker-containers-images-and-registries"></a><span data-ttu-id="4fa13-103">Contenedores, imágenes y registros de Docker</span><span class="sxs-lookup"><span data-stu-id="4fa13-103">Docker containers, images, and registries</span></span>

<span data-ttu-id="4fa13-104">Cuando se usa Docker, cree una aplicación o el servicio y el paquete y sus dependencias en una imagen de contenedor.</span><span class="sxs-lookup"><span data-stu-id="4fa13-104">When using Docker, you create an app or service and package it and its dependencies into a container image.</span></span> <span data-ttu-id="4fa13-105">Una imagen es una representación estática de la aplicación o el servicio y de su configuración y las dependencias.</span><span class="sxs-lookup"><span data-stu-id="4fa13-105">An image is a static representation of the app or service and its configuration and dependencies.</span></span>

<span data-ttu-id="4fa13-106">Para ejecutar la aplicación o el servicio, se crea una instancia de la imagen de la aplicación para crear un contenedor, que se ejecutará en el host de Docker.</span><span class="sxs-lookup"><span data-stu-id="4fa13-106">To run the app or service, the app's image is instantiated to create a container, which will be running on the Docker host.</span></span> <span data-ttu-id="4fa13-107">Inicialmente, los contenedores se prueban en un entorno de desarrollo o un PC.</span><span class="sxs-lookup"><span data-stu-id="4fa13-107">Containers are initially tested in a development environment or PC.</span></span>

<span data-ttu-id="4fa13-108">Almacenar imágenes en un registro, que actúa como una biblioteca de imágenes.</span><span class="sxs-lookup"><span data-stu-id="4fa13-108">You store images in a registry, that acts as a library of images.</span></span> <span data-ttu-id="4fa13-109">Necesita un registro cuando se implementa en orquestadores de producción.</span><span class="sxs-lookup"><span data-stu-id="4fa13-109">You need a registry when deploying to production orchestrators.</span></span> <span data-ttu-id="4fa13-110">Docker mantiene un registro público a través de [Docker Hub](https://hub.docker.com/); otros proveedores ofrecen registros para distintas colecciones de imágenes, incluido [Azure Container Registry](https://azure.microsoft.com/services/container-registry/).</span><span class="sxs-lookup"><span data-stu-id="4fa13-110">Docker maintains a public registry via [Docker Hub](https://hub.docker.com/); other vendors provide registries for different collections of images, including [Azure Container Registry](https://azure.microsoft.com/services/container-registry/).</span></span> <span data-ttu-id="4fa13-111">Como alternativa, las empresas pueden tener un registro privado local para sus propias imágenes de Docker.</span><span class="sxs-lookup"><span data-stu-id="4fa13-111">Alternatively, enterprises can have a private registry on-premises for their own Docker images.</span></span>

<span data-ttu-id="4fa13-112">Figura 1-4 se muestra cómo se relacionan las imágenes y los registros de Docker a otros componentes.</span><span class="sxs-lookup"><span data-stu-id="4fa13-112">Figure 1-4 shows how images and registries in Docker relate to other components.</span></span> <span data-ttu-id="4fa13-113">También se muestran las diversas ofertas de registro de los proveedores.</span><span class="sxs-lookup"><span data-stu-id="4fa13-113">It also shows the multiple registry offerings from vendors.</span></span>

![Taxonomía básica en Docker: El registro es similar a una estantería donde las imágenes se almacenan y están disponibles para extraer para la creación de contenedores para ejecutar servicios o aplicaciones web.](./media/image4.png)

<span data-ttu-id="4fa13-118">**Figura 1-4**.</span><span class="sxs-lookup"><span data-stu-id="4fa13-118">**Figure 1-4**.</span></span> <span data-ttu-id="4fa13-119">Taxonomía de términos de Docker y conceptos</span><span class="sxs-lookup"><span data-stu-id="4fa13-119">Taxonomy of Docker terms and concepts</span></span>

<span data-ttu-id="4fa13-120">Al colocar imágenes en un registro, puede almacenar fragmentos de la aplicación estáticos e inmutables, incluidas todas sus dependencias en un nivel de marco.</span><span class="sxs-lookup"><span data-stu-id="4fa13-120">By putting images in a registry, you can store static and immutable application bits, including all of their dependencies, at a framework level.</span></span> <span data-ttu-id="4fa13-121">, A continuación, puede versión e implementar imágenes en varios entornos y, por tanto, proporcionar una unidad de implementación coherente.</span><span class="sxs-lookup"><span data-stu-id="4fa13-121">You then can version and deploy images in multiple environments and thus provide a consistent deployment unit.</span></span>

<span data-ttu-id="4fa13-122">Los registros de imágenes privados, ya sean hospedados localmente o en la nube, se recomiendan cuando:</span><span class="sxs-lookup"><span data-stu-id="4fa13-122">Private image registries, either hosted on-premises or in the cloud, are recommended when:</span></span>

- <span data-ttu-id="4fa13-123">Las imágenes no deben compartirse públicamente por motivos de confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="4fa13-123">Your images must not be shared publicly due to confidentiality.</span></span>

- <span data-ttu-id="4fa13-124">Quiere tener una latencia de red mínima entre las imágenes y el entorno de implementación elegido.</span><span class="sxs-lookup"><span data-stu-id="4fa13-124">You want to have minimum network latency between your images and your chosen deployment environment.</span></span> <span data-ttu-id="4fa13-125">Por ejemplo, si su entorno de producción es Azure, probablemente desea almacenar las imágenes en [Azure Container Registry](https://azure.microsoft.com/services/container-registry/) para que la latencia de red es mínima.</span><span class="sxs-lookup"><span data-stu-id="4fa13-125">For example, if your production environment is Azure, you probably want to store your images in [Azure Container Registry](https://azure.microsoft.com/services/container-registry/) so that network latency is minimal.</span></span> <span data-ttu-id="4fa13-126">De forma similar, si el entorno de producción es local, puede tener un registro de confianza de Docker local disponible dentro de la misma red local.</span><span class="sxs-lookup"><span data-stu-id="4fa13-126">In a similar way, if your production environment is on-premises, you might want to have an on-premises Docker Trusted Registry available within the same local network.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="4fa13-127">[Anterior](docker-terminology.md)
>[Siguiente](road-to-modern-applications-based-on-containers.md)</span><span class="sxs-lookup"><span data-stu-id="4fa13-127">[Previous](docker-terminology.md)
[Next](road-to-modern-applications-based-on-containers.md)</span></span>
