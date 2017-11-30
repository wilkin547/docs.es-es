---
title: "Registros, imágenes y contenedores de docker"
description: "Ciclo de vida de aplicación de Docker en contenedores con herramientas y plataforma de Microsoft"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: b115b25d8ae335aafbe41bac0d694170be7e3c49
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="docker-containers-images-and-registries"></a><span data-ttu-id="cb1a6-104">Registros, imágenes y contenedores de docker</span><span class="sxs-lookup"><span data-stu-id="cb1a6-104">Docker containers, images, and registries</span></span>

<span data-ttu-id="cb1a6-105">Al utilizar Docker, cree una aplicación o servicio y paquete y sus dependencias en una imagen de contenedor.</span><span class="sxs-lookup"><span data-stu-id="cb1a6-105">When using Docker, you create an app or service and package it and its dependencies into a container image.</span></span> <span data-ttu-id="cb1a6-106">Una imagen es una representación estática de la aplicación o el servicio y su configuración y las dependencias.</span><span class="sxs-lookup"><span data-stu-id="cb1a6-106">An image is a static representation of the app or service and its configuration and dependencies.</span></span>

<span data-ttu-id="cb1a6-107">Para ejecutar la aplicación o servicio, se crea una instancia de imagen de la aplicación para crear un contenedor, que se ejecutarán en el host Docker.</span><span class="sxs-lookup"><span data-stu-id="cb1a6-107">To run the app or service, the app's image is instantiated to create a container, which will be running on the Docker host.</span></span> <span data-ttu-id="cb1a6-108">Inicialmente se admiten los contenedores en un entorno de desarrollo o PC.</span><span class="sxs-lookup"><span data-stu-id="cb1a6-108">Containers are initially tested in a development environment or PC.</span></span>

<span data-ttu-id="cb1a6-109">Almacenar imágenes en un registro, que actúa como una biblioteca de imágenes.</span><span class="sxs-lookup"><span data-stu-id="cb1a6-109">You store images in a registry, which acts as a library of images.</span></span> <span data-ttu-id="cb1a6-110">Necesita un registro cuando se implementa en orchestrators de producción.</span><span class="sxs-lookup"><span data-stu-id="cb1a6-110">You need a registry when deploying to production orchestrators.</span></span> <span data-ttu-id="cb1a6-111">Mantiene un registro público a través de docker [Docker Hub](https://hub.docker.com/); otros proveedores ofrecen registros para las diferentes colecciones de imágenes.</span><span class="sxs-lookup"><span data-stu-id="cb1a6-111">Docker maintains a public registry via [Docker Hub](https://hub.docker.com/); other vendors provide registries for different collections of images.</span></span> <span data-ttu-id="cb1a6-112">Como alternativa, las empresas pueden tener un registro privado local para sus propias imágenes de Docker.</span><span class="sxs-lookup"><span data-stu-id="cb1a6-112">Alternatively, enterprises can have a private registry on-premises for their own Docker images.</span></span>

<span data-ttu-id="cb1a6-113">Figura 1-4 se muestra cómo se relacionan las imágenes y los registros en Docker con otros componentes.</span><span class="sxs-lookup"><span data-stu-id="cb1a6-113">Figure 1-4 shows how images and registries in Docker relate to other components.</span></span> <span data-ttu-id="cb1a6-114">También muestra las varias ofertas de registro de proveedores.</span><span class="sxs-lookup"><span data-stu-id="cb1a6-114">It also shows the multiple registry offerings from vendors.</span></span>

![](./media/image4.png)

<span data-ttu-id="cb1a6-115">Figura 1-4: taxonomía de términos de Docker y conceptos</span><span class="sxs-lookup"><span data-stu-id="cb1a6-115">Figure 1-4: Taxonomy of Docker terms and concepts</span></span>

<span data-ttu-id="cb1a6-116">Al colocar imágenes en un registro, puede almacenar fragmentos de la aplicación estáticos e inmutable, incluidas todas sus dependencias, en un nivel de marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="cb1a6-116">By putting images in a registry, you can store static and immutable application bits, including all of their dependencies, at a framework level.</span></span> <span data-ttu-id="cb1a6-117">, A continuación, puede versión e implementar imágenes en varios entornos y, por tanto, proporcionar una unidad de implementación coherente.</span><span class="sxs-lookup"><span data-stu-id="cb1a6-117">You then can version and deploy images in multiple environments and thus provide a consistent deployment unit.</span></span>

<span data-ttu-id="cb1a6-118">Registros de imagen privada, hospedado en local o en la nube, se recomienda en las siguientes situaciones:</span><span class="sxs-lookup"><span data-stu-id="cb1a6-118">Private image registries, either hosted on-premises or in the cloud, are recommended for the following situations:</span></span>

-   <span data-ttu-id="cb1a6-119">Las imágenes no deben compartirse públicamente debido a la confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="cb1a6-119">Your images must not be shared publicly due to confidentiality.</span></span>

-   <span data-ttu-id="cb1a6-120">Desea tener una latencia de red mínimas entre las imágenes y el entorno de implementación elegido.</span><span class="sxs-lookup"><span data-stu-id="cb1a6-120">You want to have minimum network latency between your images and your chosen deployment environment.</span></span> <span data-ttu-id="cb1a6-121">Por ejemplo, si el entorno de producción es Azure, probablemente desee almacenar las imágenes en el registro de contenedor de Azure para que la latencia de red será mínima.</span><span class="sxs-lookup"><span data-stu-id="cb1a6-121">For example, if your production environment is Azure, you probably want to store your images in Azure Container Registry so that network latency will be minimal.</span></span> <span data-ttu-id="cb1a6-122">De forma similar, si el entorno de producción es local, puede tener un local Docker registro de confianza disponibles dentro de la misma red local.</span><span class="sxs-lookup"><span data-stu-id="cb1a6-122">In a similar way, if your production environment is on-premises, you might want to have an on-premises Docker Trusted Registry available within the same local network.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="cb1a6-123">[Anterior] (docker-terminology.md) [siguiente] (Docker-aplicaciones-ciclo de vida/index.md)</span><span class="sxs-lookup"><span data-stu-id="cb1a6-123">[Previous] (docker-terminology.md) [Next] (Docker-application-lifecycle/index.md)</span></span>
