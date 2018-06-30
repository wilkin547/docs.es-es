---
title: Introducción a Containers y Docker
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: e9f81c5fecc06b19ebd84cc4b2cc232686768a90
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106637"
---
# <a name="introduction-to-containers-and-docker"></a><span data-ttu-id="e895f-103">Introducción a Containers y Docker</span><span class="sxs-lookup"><span data-stu-id="e895f-103">Introduction to containers and Docker</span></span>

<span data-ttu-id="e895f-104">La inclusión en contenedores es un enfoque de desarrollo de software en el que una aplicación o un servicio, sus dependencias y su configuración (extraídos como archivos de manifiesto de implementación) se empaquetan como una imagen de contenedor.</span><span class="sxs-lookup"><span data-stu-id="e895f-104">Containerization is an approach to software development in which an application or service, its dependencies, and its configuration (abstracted as deployment manifest files) are packaged together as a container image.</span></span> <span data-ttu-id="e895f-105">Puede probar la aplicación en contenedor como una unidad e implementarla como una instancia de imagen de contenedor en el sistema operativo host.</span><span class="sxs-lookup"><span data-stu-id="e895f-105">You then can test the containerized application as a unit and deploy it as a container image instance to the host operating system.</span></span>

<span data-ttu-id="e895f-106">Del mismo modo que el sector de transporte de mercancías usa contenedores normalizados para transportar mercancías por barco, tren o camión independientemente de la carga de su interior, los contenedores de software actúan como una unidad estándar de software que puede contener diferentes dependencias y código.</span><span class="sxs-lookup"><span data-stu-id="e895f-106">Just as the shipping industry uses standardized containers to move goods by ship, train, or truck, regardless of the cargo within them, software containers act as a standard unit of software that can contain different code and dependencies.</span></span> <span data-ttu-id="e895f-107">La inclusión del software en contenedores permite a los desarrolladores y profesionales de TI implementar tales contenedores en entornos con pocas modificaciones o incluso ninguna.</span><span class="sxs-lookup"><span data-stu-id="e895f-107">Placing software into containers makes it possible for developers and IT professionals to deploy those containers across environments with little or no modification.</span></span>

<span data-ttu-id="e895f-108">Los contenedores también aíslan las aplicaciones entre sí en un sistema operativo compartido.</span><span class="sxs-lookup"><span data-stu-id="e895f-108">Containers also isolate applications from one another on a shared operating system (OS).</span></span> <span data-ttu-id="e895f-109">Las aplicaciones en contenedor se ejecutan sobre un host de contenedor que a su vez se ejecuta en el sistema operativo (Linux o Windows).</span><span class="sxs-lookup"><span data-stu-id="e895f-109">Containerized applications run on top of a container host, which in turn runs on the OS (Linux or Windows).</span></span> <span data-ttu-id="e895f-110">Por lo tanto, los contenedores tienen una superficie significativamente menor que las imágenes de máquina virtual (VM).</span><span class="sxs-lookup"><span data-stu-id="e895f-110">Thus, containers have a significantly smaller footprint than virtual machine (VM) images.</span></span>

<span data-ttu-id="e895f-111">Cada contenedor puede ejecutar una aplicación web o un servicio al completo, como se muestra en la figura 1-1.</span><span class="sxs-lookup"><span data-stu-id="e895f-111">Each container can run an entire web application or a service, as shown in Figure 1-1.</span></span>

![](./media/image1.png)

<span data-ttu-id="e895f-112">Figura 1-1: Varios contenedores ejecutándose en un host de contenedor</span><span class="sxs-lookup"><span data-stu-id="e895f-112">Figure 1-1: Multiple containers running on a container host</span></span>

<span data-ttu-id="e895f-113">En este ejemplo, el host de Docker es un host de contenedor, y App 1, App 2, Svc 1 y Svc 2 son aplicaciones o servicios en contenedor.</span><span class="sxs-lookup"><span data-stu-id="e895f-113">In this example, Docker Host is a container host, and App 1, App 2, Svc 1, and Svc 2 are containerized applications or services.</span></span>

<span data-ttu-id="e895f-114">Otra ventaja derivada de la inclusión en contenedores es la escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="e895f-114">Another benefit you can derive from containerization is scalability.</span></span> <span data-ttu-id="e895f-115">La creación de contenedores para tareas a corto plazo permite escalar horizontalmente con gran rapidez.</span><span class="sxs-lookup"><span data-stu-id="e895f-115">You can scale-out quickly by creating new containers for short-term tasks.</span></span> <span data-ttu-id="e895f-116">Desde el punto de vista de la aplicación, *la creación de instancias de una imagen* (la creación de un contenedor) es similar a la creación de instancias de un proceso como un servicio o una aplicación web.</span><span class="sxs-lookup"><span data-stu-id="e895f-116">From an application point of view, *instantiating an image* (creating a container) is similar to instantiating a process like a service or web app.</span></span> <span data-ttu-id="e895f-117">Pero con fines de confiabilidad, cuando ejecute varias instancias de la misma imagen en varios servidores host, seguramente le interesará que cada contenedor (instancia de imagen) se ejecute en un servidor host o máquina virtual diferente en dominios de error distintos.</span><span class="sxs-lookup"><span data-stu-id="e895f-117">For reliability, however, when you run multiple instances of the same image across multiple host servers, you typically want each container (image instance) to run in a different host server or VM in different fault domains.</span></span>

<span data-ttu-id="e895f-118">En resumen, los contenedores ofrecen las ventajas del aislamiento, la portabilidad, la agilidad, la escalabilidad y el control a lo largo de todo el flujo de trabajo del ciclo de vida de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e895f-118">In short, containers offer the benefits of isolation, portability, agility, scalability, and control across the entire application life cycle workflow.</span></span> <span data-ttu-id="e895f-119">La ventaja más importante es el aislamiento que se proporciona entre el desarrollo y las operaciones.</span><span class="sxs-lookup"><span data-stu-id="e895f-119">The most important benefit is the isolation provided between Dev and Ops.</span></span>


>[!div class="step-by-step"]
[<span data-ttu-id="e895f-120">Siguiente</span><span class="sxs-lookup"><span data-stu-id="e895f-120">Next</span></span>](what-is-docker.md)
