---
title: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
description: Obtenga información general de alto nivel del proceso de desarrollo e implementación para desarrollar e implementar aplicaciones en contenedores con la plataforma y las herramientas de Microsoft y Docker.
ms.date: 07/30/2020
ms.openlocfilehash: c506a3423ac4511f23452192e361e88dce6efec4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91160702"
---
# <a name="containerized-docker-application-lifecycle-with-microsoft-platform-and-tools"></a><span data-ttu-id="1f089-103">Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="1f089-103">Containerized Docker Application Lifecycle with Microsoft Platform and Tools</span></span>

![Portada del libro](./media/devops-book-cover-large-we.png)

<span data-ttu-id="1f089-105">**EDICIÓN v3.1**: actualizada a ASP.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="1f089-105">**EDITION v3.1** - Updated to ASP.NET Core 3.1</span></span>

<span data-ttu-id="1f089-106">En esta guía se incluye información general para desarrollar e implementar aplicaciones ASP.NET Core en contenedores con Docker, mediante la plataforma y las herramientas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1f089-106">This guide is a general overview for developing and deploying containerized ASP.NET Core applications with Docker, using the Microsoft platform and tools.</span></span> <span data-ttu-id="1f089-107">En ella también se incluye una presentación de alto nivel de Azure DevOps, a fin de implementar canalizaciones de CI/CD, así como Azure Container Registry (ACR) y Azure Kubernetes Services (AKS) para la implementación.</span><span class="sxs-lookup"><span data-stu-id="1f089-107">The guide includes a high-level introduction to Azure DevOps, for implementing CI/CD pipelines, as well as Azure Container Registry (ACR), and Azure Kubernetes Services AKS for deployment.</span></span>

<span data-ttu-id="1f089-108">Para obtener detalles de bajo nivel relacionados con el desarrollo, puede ver la guía [Microservicios de .NET: Arquitectura para aplicaciones .NET en contenedor](../microservices/index.md) y su aplicación de referencia relacionada, [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers).</span><span class="sxs-lookup"><span data-stu-id="1f089-108">For low-level, development-related details you can see the [.NET Microservices: Architecture for Containerized .NET Applications](../microservices/index.md) guide and it related reference application [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers).</span></span>

## <a name="send-us-your-feedback"></a><span data-ttu-id="1f089-109">Envíenos sus comentarios.</span><span class="sxs-lookup"><span data-stu-id="1f089-109">Send us your feedback!</span></span>

<span data-ttu-id="1f089-110">Hemos creado esta guía para ayudarle a entender la arquitectura de aplicaciones y microservicios en contenedor en .NET.</span><span class="sxs-lookup"><span data-stu-id="1f089-110">We wrote this guide to help you understand the architecture of containerized applications and microservices in .NET.</span></span> <span data-ttu-id="1f089-111">La guía y la aplicación de referencia relacionada irán evolucionando, por lo que le agradecemos sus comentarios.</span><span class="sxs-lookup"><span data-stu-id="1f089-111">The guide and related reference application will be evolving, so we welcome your feedback!</span></span> <span data-ttu-id="1f089-112">Si tiene comentarios sobre cómo se puede mejorar esta guía, envíelos a <https://aka.ms/ebookfeedback>.</span><span class="sxs-lookup"><span data-stu-id="1f089-112">If you have comments about how this guide can be improved, submit feedback at <https://aka.ms/ebookfeedback>.</span></span>

## <a name="credits"></a><span data-ttu-id="1f089-113">Créditos</span><span class="sxs-lookup"><span data-stu-id="1f089-113">Credits</span></span>

<span data-ttu-id="1f089-114">Autor:</span><span class="sxs-lookup"><span data-stu-id="1f089-114">Author:</span></span>

> <span data-ttu-id="1f089-115">**Cesar de la Torre**, administrador de programas sénior del equipo de producto de .NET, Microsoft Corp.</span><span class="sxs-lookup"><span data-stu-id="1f089-115">**Cesar de la Torre**, Sr. PM, .NET product team, Microsoft Corp.</span></span>

<span data-ttu-id="1f089-116">Editor de adquisiciones:</span><span class="sxs-lookup"><span data-stu-id="1f089-116">Acquisitions Editor:</span></span>

> <span data-ttu-id="1f089-117">**Janine Patrick**</span><span class="sxs-lookup"><span data-stu-id="1f089-117">**Janine Patrick**</span></span>

<span data-ttu-id="1f089-118">Editor de desarrollo:</span><span class="sxs-lookup"><span data-stu-id="1f089-118">Developmental Editor:</span></span>

> <span data-ttu-id="1f089-119">**Bob Russell**, profesional de soluciones en Microsoft</span><span class="sxs-lookup"><span data-stu-id="1f089-119">**Bob Russell**, Solutions Professional at Microsoft</span></span>
>
> [<span data-ttu-id="1f089-120">**Octal Publishing, Inc.** </span><span class="sxs-lookup"><span data-stu-id="1f089-120">**Octal Publishing, Inc.**</span></span>](http://www.octalpub.com/)

<span data-ttu-id="1f089-121">Producción editorial:</span><span class="sxs-lookup"><span data-stu-id="1f089-121">Editorial Production:</span></span>

> [<span data-ttu-id="1f089-122">Dianne Russell</span><span class="sxs-lookup"><span data-stu-id="1f089-122">Dianne Russell</span></span>](http://www.octalpub.com/)
>
> <span data-ttu-id="1f089-123">**Octal Publishing, Inc.**</span><span class="sxs-lookup"><span data-stu-id="1f089-123">**Octal Publishing, Inc.**</span></span>

<span data-ttu-id="1f089-124">Revisor:</span><span class="sxs-lookup"><span data-stu-id="1f089-124">Copyeditor:</span></span>

> <span data-ttu-id="1f089-125">**Bob Russell**, profesional de soluciones en Microsoft</span><span class="sxs-lookup"><span data-stu-id="1f089-125">**Bob Russell**, Solutions Professional at Microsoft</span></span>

<span data-ttu-id="1f089-126">Participantes y revisores:</span><span class="sxs-lookup"><span data-stu-id="1f089-126">Participants and reviewers:</span></span>

> <span data-ttu-id="1f089-127">**Nish Anil**, director de administración de programas, equipo de .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="1f089-127">**Nish Anil**, Sr. Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="1f089-128">**Miguel Veloso**, ingeniero de desarrollo de software en Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="1f089-128">**Miguel Veloso**, Software Development Engineer at Plain Concepts</span></span>
>
> <span data-ttu-id="1f089-129">**Sumit Ghosh**, asesor principal en Neudesic</span><span class="sxs-lookup"><span data-stu-id="1f089-129">**Sumit Ghosh**, Principal Consultant at Neudesic</span></span>

## <a name="copyright"></a><span data-ttu-id="1f089-130">Copyright</span><span class="sxs-lookup"><span data-stu-id="1f089-130">Copyright</span></span>

<span data-ttu-id="1f089-131">PUBLICADO POR</span><span class="sxs-lookup"><span data-stu-id="1f089-131">PUBLISHED BY</span></span>

<span data-ttu-id="1f089-132">Equipos de producto de la División de desarrolladores de Microsoft, .NET y Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1f089-132">Microsoft Developer Division, .NET and Visual Studio product teams</span></span>

<span data-ttu-id="1f089-133">División de Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="1f089-133">A division of Microsoft Corporation</span></span>

<span data-ttu-id="1f089-134">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="1f089-134">One Microsoft Way</span></span>

<span data-ttu-id="1f089-135">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="1f089-135">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="1f089-136">Copyright &copy; 2020 de Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="1f089-136">Copyright &copy; 2020 by Microsoft Corporation</span></span>

<span data-ttu-id="1f089-137">Todos los derechos reservados.</span><span class="sxs-lookup"><span data-stu-id="1f089-137">All rights reserved.</span></span> <span data-ttu-id="1f089-138">No se puede reproducir ni transmitir de ninguna forma ni por ningún medio ninguna parte del contenido de este libro sin la autorización por escrito del publicador.</span><span class="sxs-lookup"><span data-stu-id="1f089-138">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="1f089-139">Este libro se proporciona “tal cual” y expresa las opiniones del autor.</span><span class="sxs-lookup"><span data-stu-id="1f089-139">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="1f089-140">Las opiniones y la información expresados en este libro, incluidas las direcciones URL y otras referencias a sitios web de Internet, pueden cambiar sin previo aviso.</span><span class="sxs-lookup"><span data-stu-id="1f089-140">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="1f089-141">Algunos ejemplos descritos aquí se proporcionan únicamente con fines ilustrativos y son ficticios.</span><span class="sxs-lookup"><span data-stu-id="1f089-141">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="1f089-142">No debe deducirse ninguna asociación ni conexión reales.</span><span class="sxs-lookup"><span data-stu-id="1f089-142">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="1f089-143">Microsoft y las marcas comerciales indicadas en <https://www.microsoft.com> en la página web "Marcas comerciales" pertenecen al grupo de empresas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1f089-143">Microsoft and the trademarks listed at <https://www.microsoft.com> on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="1f089-144">Mac y macOS son marcas comerciales de Apple Inc.</span><span class="sxs-lookup"><span data-stu-id="1f089-144">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="1f089-145">El logotipo de la ballena de Docker es una marca registrada de Docker, Inc. Se usa con permiso.</span><span class="sxs-lookup"><span data-stu-id="1f089-145">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="1f089-146">El resto de marcas y logotipos pertenece a sus respectivos propietarios.</span><span class="sxs-lookup"><span data-stu-id="1f089-146">All other marks and logos are property of their respective owners.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="1f089-147">Siguiente</span><span class="sxs-lookup"><span data-stu-id="1f089-147">Next</span></span>](introduction-to-containers-and-docker.md)
