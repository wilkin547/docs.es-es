---
title: Contenedores, imágenes y registros de Docker
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 43b76f738fa4b7c89423a5b9fac7ef91f40880c5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33568737"
---
# <a name="docker-containers-images-and-registries"></a><span data-ttu-id="1d606-103">Contenedores, imágenes y registros de Docker</span><span class="sxs-lookup"><span data-stu-id="1d606-103">Docker containers, images, and registries</span></span>

<span data-ttu-id="1d606-104">Al utilizar Docker, cree una aplicación o servicio y paquete y sus dependencias en una imagen de contenedor.</span><span class="sxs-lookup"><span data-stu-id="1d606-104">When using Docker, you create an app or service and package it and its dependencies into a container image.</span></span> <span data-ttu-id="1d606-105">Una imagen es una representación estática de la aplicación o el servicio y de su configuración y las dependencias.</span><span class="sxs-lookup"><span data-stu-id="1d606-105">An image is a static representation of the app or service and its configuration and dependencies.</span></span>

<span data-ttu-id="1d606-106">Para ejecutar la aplicación o servicio, se crea una instancia de imagen de la aplicación para crear un contenedor, que se ejecutarán en el host Docker.</span><span class="sxs-lookup"><span data-stu-id="1d606-106">To run the app or service, the app's image is instantiated to create a container, which will be running on the Docker host.</span></span> <span data-ttu-id="1d606-107">Inicialmente, los contenedores se prueban en un entorno de desarrollo o un PC.</span><span class="sxs-lookup"><span data-stu-id="1d606-107">Containers are initially tested in a development environment or PC.</span></span>

<span data-ttu-id="1d606-108">Almacenar imágenes en un registro, que actúa como una biblioteca de imágenes.</span><span class="sxs-lookup"><span data-stu-id="1d606-108">You store images in a registry, which acts as a library of images.</span></span> <span data-ttu-id="1d606-109">Necesita un registro cuando se implementa en orchestrators de producción.</span><span class="sxs-lookup"><span data-stu-id="1d606-109">You need a registry when deploying to production orchestrators.</span></span> <span data-ttu-id="1d606-110">Docker mantiene un registro público a través de [Docker Hub](https://hub.docker.com/); otros proveedores ofrecen registros para distintas colecciones de imágenes.</span><span class="sxs-lookup"><span data-stu-id="1d606-110">Docker maintains a public registry via [Docker Hub](https://hub.docker.com/); other vendors provide registries for different collections of images.</span></span> <span data-ttu-id="1d606-111">Como alternativa, las empresas pueden tener un registro privado local para sus propias imágenes de Docker.</span><span class="sxs-lookup"><span data-stu-id="1d606-111">Alternatively, enterprises can have a private registry on-premises for their own Docker images.</span></span>

<span data-ttu-id="1d606-112">Figura 1-4 se muestra cómo se relacionan las imágenes y los registros en Docker con otros componentes.</span><span class="sxs-lookup"><span data-stu-id="1d606-112">Figure 1-4 shows how images and registries in Docker relate to other components.</span></span> <span data-ttu-id="1d606-113">También se muestran las diversas ofertas de registro de los proveedores.</span><span class="sxs-lookup"><span data-stu-id="1d606-113">It also shows the multiple registry offerings from vendors.</span></span>

![](./media/image4.png)

<span data-ttu-id="1d606-114">Figura 1-4: taxonomía de términos de Docker y conceptos</span><span class="sxs-lookup"><span data-stu-id="1d606-114">Figure 1-4: Taxonomy of Docker terms and concepts</span></span>

<span data-ttu-id="1d606-115">Al colocar imágenes en un registro, puede almacenar fragmentos de la aplicación estáticos e inmutable, incluidas todas sus dependencias, en un nivel de marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1d606-115">By putting images in a registry, you can store static and immutable application bits, including all of their dependencies, at a framework level.</span></span> <span data-ttu-id="1d606-116">, A continuación, puede versión e implementar imágenes en varios entornos y, por tanto, proporcionar una unidad de implementación coherente.</span><span class="sxs-lookup"><span data-stu-id="1d606-116">You then can version and deploy images in multiple environments and thus provide a consistent deployment unit.</span></span>

<span data-ttu-id="1d606-117">Registros de imagen privada, hospedado en local o en la nube, se recomienda en las siguientes situaciones:</span><span class="sxs-lookup"><span data-stu-id="1d606-117">Private image registries, either hosted on-premises or in the cloud, are recommended for the following situations:</span></span>

-   <span data-ttu-id="1d606-118">Las imágenes no deben compartirse públicamente por motivos de confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="1d606-118">Your images must not be shared publicly due to confidentiality.</span></span>

-   <span data-ttu-id="1d606-119">Quiere tener una latencia de red mínima entre las imágenes y el entorno de implementación elegido.</span><span class="sxs-lookup"><span data-stu-id="1d606-119">You want to have minimum network latency between your images and your chosen deployment environment.</span></span> <span data-ttu-id="1d606-120">Por ejemplo, si el entorno de producción es Azure, probablemente desee almacenar las imágenes en el registro de contenedor de Azure para que la latencia de red será mínima.</span><span class="sxs-lookup"><span data-stu-id="1d606-120">For example, if your production environment is Azure, you probably want to store your images in Azure Container Registry so that network latency will be minimal.</span></span> <span data-ttu-id="1d606-121">De forma similar, si el entorno de producción es local, puede tener un registro de confianza de Docker local disponible dentro de la misma red local.</span><span class="sxs-lookup"><span data-stu-id="1d606-121">In a similar way, if your production environment is on-premises, you might want to have an on-premises Docker Trusted Registry available within the same local network.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="1d606-122">[Anterior] (docker-terminology.md) [siguiente] (Docker-aplicaciones-ciclo de vida/index.md)</span><span class="sxs-lookup"><span data-stu-id="1d606-122">[Previous] (docker-terminology.md) [Next] (Docker-application-lifecycle/index.md)</span></span>
