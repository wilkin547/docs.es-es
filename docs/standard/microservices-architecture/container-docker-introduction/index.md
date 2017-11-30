---
title: "Introducción a Containers y Docker"
description: "Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Introducción a Containers y Docker"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: bb9466129287b0f10ace3c6d1129fb94b7a443e2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="introduction-to-containers-and-docker"></a><span data-ttu-id="e72f2-104">Introducción a Containers y Docker</span><span class="sxs-lookup"><span data-stu-id="e72f2-104">Introduction to Containers and Docker</span></span>

<span data-ttu-id="e72f2-105">La inclusión en contenedores es un enfoque de desarrollo de software en el que una aplicación o un servicio, sus dependencias y su configuración (extraídos como archivos de manifiesto de implementación) se empaquetan como una imagen de contenedor.</span><span class="sxs-lookup"><span data-stu-id="e72f2-105">Containerization is an approach to software development in which an application or service, its dependencies, and its configuration (abstracted as deployment manifest files) are packaged together as a container image.</span></span> <span data-ttu-id="e72f2-106">La aplicación en contenedor puede probarse como una unidad e implementarse como una instancia de imagen de contenedor en el sistema operativo (SO) host.</span><span class="sxs-lookup"><span data-stu-id="e72f2-106">The containerized application can be tested as a unit and deployed as a container image instance to the host operating system (OS).</span></span>

<span data-ttu-id="e72f2-107">Del mismo modo que los contenedores de mercancías permiten su transporte por barco, tren o camión independientemente de la carga de su interior, los contenedores de software actúan como una unidad estándar de software que puede contener diferentes dependencias y código.</span><span class="sxs-lookup"><span data-stu-id="e72f2-107">Just as shipping containers allow goods to be transported by ship, train, or truck regardless of the cargo inside, software containers act as a standard unit of software that can contain different code and dependencies.</span></span> <span data-ttu-id="e72f2-108">De esta manera, la inclusión del software en contenedor permite a los desarrolladores y los profesionales de TI implementarlo en entornos con pocas modificaciones o ninguna en absoluto.</span><span class="sxs-lookup"><span data-stu-id="e72f2-108">Containerizing software this way enables developers and IT professionals to deploy them across environments with little or no modification.</span></span>

<span data-ttu-id="e72f2-109">Los contenedores también aíslan las aplicaciones entre sí en un sistema operativo compartido.</span><span class="sxs-lookup"><span data-stu-id="e72f2-109">Containers also isolate applications from each other on a shared OS.</span></span> <span data-ttu-id="e72f2-110">Las aplicaciones en contenedor se ejecutan sobre un host de contenedor que a su vez se ejecuta en el sistema operativo (Linux o Windows).</span><span class="sxs-lookup"><span data-stu-id="e72f2-110">Containerized applications run on top of a container host that in turn runs on the OS (Linux or Windows).</span></span> <span data-ttu-id="e72f2-111">Por lo tanto, los contenedores tienen una superficie significativamente menor que las imágenes de máquina virtual (VM).</span><span class="sxs-lookup"><span data-stu-id="e72f2-111">Containers therefore have a significantly smaller footprint than virtual machine (VM) images.</span></span>

<span data-ttu-id="e72f2-112">Cada contenedor puede ejecutar una aplicación web o un servicio al completo, como se muestra en la figura 2-1.</span><span class="sxs-lookup"><span data-stu-id="e72f2-112">Each container can run a whole web application or a service, as shown in Figure 2-1.</span></span> <span data-ttu-id="e72f2-113">En este ejemplo, el host de Docker es un host de contenedor, y App 1, App 2, Svc 1 y Svc 2 son aplicaciones o servicios en contenedor.</span><span class="sxs-lookup"><span data-stu-id="e72f2-113">In this example, Docker host is a container host, and App1, App2, Svc 1, and Svc 2 are containerized applications or services.</span></span>

![](./media/image1.png)

<span data-ttu-id="e72f2-114">**Figura 2-1**.</span><span class="sxs-lookup"><span data-stu-id="e72f2-114">**Figure 2-1**.</span></span> <span data-ttu-id="e72f2-115">Varios contenedores ejecutándose en un host de contenedor.</span><span class="sxs-lookup"><span data-stu-id="e72f2-115">Multiple containers running on a container host</span></span>

<span data-ttu-id="e72f2-116">Otra ventaja de la inclusión en contenedores es la escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="e72f2-116">Another benefit of containerization is scalability.</span></span> <span data-ttu-id="e72f2-117">La creación de contenedores para tareas a corto plazo permite escalar horizontalmente con gran rapidez.</span><span class="sxs-lookup"><span data-stu-id="e72f2-117">You can scale out quickly by creating new containers for short-term tasks.</span></span> <span data-ttu-id="e72f2-118">Desde el punto de vista de la aplicación, la creación de instancias de una imagen (la creación de un contenedor) es similar a la creación de instancias de un proceso como un servicio o una aplicación web.</span><span class="sxs-lookup"><span data-stu-id="e72f2-118">From an application point of view, instantiating an image (creating a container) is similar to instantiating a process like a service or web app.</span></span> <span data-ttu-id="e72f2-119">Pero con fines de confiabilidad, cuando ejecute varias instancias de la misma imagen en varios servidores host, seguramente le interesará que cada contenedor (instancia de imagen) se ejecute en un servidor host o máquina virtual diferente en dominios de error distintos.</span><span class="sxs-lookup"><span data-stu-id="e72f2-119">For reliability, however, when you run multiple instances of the same image across multiple host servers, you typically want each container (image instance) to run in a different host server or VM in different fault domains.</span></span>

<span data-ttu-id="e72f2-120">En resumen, los contenedores ofrecen las ventajas del aislamiento, la portabilidad, la agilidad, la escalabilidad y el control a lo largo de todo el flujo de trabajo del ciclo de vida de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e72f2-120">In short, containers offer the benefits of isolation, portability, agility, scalability, and control across the whole application lifecycle workflow.</span></span> <span data-ttu-id="e72f2-121">La ventaja más importante es el aislamiento que se proporciona entre el desarrollo y las operaciones.</span><span class="sxs-lookup"><span data-stu-id="e72f2-121">The most important benefit is the isolation provided between Dev and Ops.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="e72f2-122">[Anterior] (../index.md) [Siguiente] (docker-defined.md)</span><span class="sxs-lookup"><span data-stu-id="e72f2-122">[Previous] (../index.md) [Next] (docker-defined.md)</span></span>
