---
title: "Diseñar y desarrollar aplicaciones .NET basadas en varios contenedores y microservicios"
description: "Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Diseñar y desarrollar aplicaciones .NET basadas en varios contenedores y microservicios"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 46d2859fa3b739b1a2a8b1502d4e418fab204648
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="designing-and-developing-multi-container-and-microservice-based-net-applications"></a><span data-ttu-id="fdc8f-104">Diseñar y desarrollar aplicaciones .NET basadas en varios contenedores y microservicios</span><span class="sxs-lookup"><span data-stu-id="fdc8f-104">Designing and Developing Multi-Container and Microservice-Based .NET Applications</span></span>

<span data-ttu-id="fdc8f-105">*Si desarrolla aplicaciones de microservicios en contenedor significa que está compilando aplicaciones de varios contenedores. Pero una aplicación de varios contenedores también podría ser más sencilla (por ejemplo, una aplicación de tres niveles) y podría no compilarse con una arquitectura de microservicios.*</span><span class="sxs-lookup"><span data-stu-id="fdc8f-105">*Developing containerized microservice applications means you are building multi-container applications. However, a multi-container application could also be simpler—for example, a three-tier application—and might not be built using a microservice architecture.*</span></span>

<span data-ttu-id="fdc8f-106">Previamente planteamos la pregunta “¿Se necesita Docker para compilar una arquitectura de microservicios?”.</span><span class="sxs-lookup"><span data-stu-id="fdc8f-106">Earlier we raised the question “Is Docker necessary when building a microservice architecture?”</span></span> <span data-ttu-id="fdc8f-107">La respuesta es un no rotundo.</span><span class="sxs-lookup"><span data-stu-id="fdc8f-107">The answer is a clear no.</span></span> <span data-ttu-id="fdc8f-108">Docker es un habilitador y puede proporcionar grandes ventajas, pero los contenedores y Docker no son un requisito imprescindible para los microservicios.</span><span class="sxs-lookup"><span data-stu-id="fdc8f-108">Docker is an enabler and can provide significant benefits, but containers and Docker are not a hard requirement for microservices.</span></span> <span data-ttu-id="fdc8f-109">Por ejemplo, podría crear una aplicación basada en microservicios con o sin Docker al usar Azure Service Fabric, que es compatible con los microservicios que se ejecutan como procesos simples o como contenedores de Docker.</span><span class="sxs-lookup"><span data-stu-id="fdc8f-109">As an example, you could create a microservices-based application with or without Docker when using Azure Service Fabric, which supports microservices running as simple processes or as Docker containers.</span></span>

<span data-ttu-id="fdc8f-110">Pero si sabe cómo diseñar y desarrollar una aplicación basada en microservicios que también se base en contenedores de Docker, podrá diseñar y desarrollar cualquier modelo de aplicación más sencillo.</span><span class="sxs-lookup"><span data-stu-id="fdc8f-110">However, if you know how to design and develop a microservices-based application that is also based on Docker containers, you will be able to design and develop any other, simpler application model.</span></span> <span data-ttu-id="fdc8f-111">Por ejemplo, podría diseñar una aplicación de tres niveles que también requiera un enfoque de varios contenedores.</span><span class="sxs-lookup"><span data-stu-id="fdc8f-111">For example, you might design a three-tier application that also requires a multi-container approach.</span></span> <span data-ttu-id="fdc8f-112">Debido a eso, y dado que las arquitecturas de microservicios son una tendencia importante en el mundo de los contenedores, esta sección se centra en la implementación de una arquitectura de microservicios con contenedores de Docker.</span><span class="sxs-lookup"><span data-stu-id="fdc8f-112">Because of that, and because microservice architectures are an important trend within the container world, this section focuses on a microservice architecture implementation using Docker containers.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="fdc8f-113">[Anterior] (../containerize-net-framework-applications/index.md) [Siguiente] (microservice-application-design.md)</span><span class="sxs-lookup"><span data-stu-id="fdc8f-113">[Previous] (../containerize-net-framework-applications/index.md) [Next] (microservice-application-design.md)</span></span>
