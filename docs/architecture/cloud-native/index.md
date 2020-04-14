---
title: Diseño de aplicaciones .NET nativas en la nube para Azure
description: Guía para crear aplicaciones nativas en la nube con la ayuda de contenedores, microservicios y características sin servidor de Azure.
author: ardalis
ms.date: 03/07/2019
ms.openlocfilehash: cf3be07f0d37aacf4f0252ef2f4d922b7be93eee
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989069"
---
# <a name="architecting-cloud-native-net-applications-for-azure"></a><span data-ttu-id="cd7bc-103">Diseño de aplicaciones .NET nativas en la nube para Azure</span><span class="sxs-lookup"><span data-stu-id="cd7bc-103">Architecting Cloud Native .NET Applications for Azure</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

![imagen de portada](./media/cover.png)

<span data-ttu-id="cd7bc-105">PUBLICADO POR</span><span class="sxs-lookup"><span data-stu-id="cd7bc-105">PUBLISHED BY</span></span>

<span data-ttu-id="cd7bc-106">Equipos de producto de la División de desarrolladores de Microsoft, .NET y Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cd7bc-106">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="cd7bc-107">División de Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="cd7bc-107">A division of Microsoft Corporation</span></span>

<span data-ttu-id="cd7bc-108">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="cd7bc-108">One Microsoft Way</span></span>

<span data-ttu-id="cd7bc-109">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="cd7bc-109">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="cd7bc-110">Copyright &copy; 2019; 2001-2003 de Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="cd7bc-110">Copyright &copy; 2019 by Microsoft Corporation</span></span>

<span data-ttu-id="cd7bc-111">Todos los derechos reservados.</span><span class="sxs-lookup"><span data-stu-id="cd7bc-111">All rights reserved.</span></span> <span data-ttu-id="cd7bc-112">No se puede reproducir ni transmitir de ninguna forma ni por ningún medio ninguna parte del contenido de este libro sin la autorización por escrito del publicador.</span><span class="sxs-lookup"><span data-stu-id="cd7bc-112">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="cd7bc-113">Este libro se proporciona “tal cual” y expresa las opiniones del autor.</span><span class="sxs-lookup"><span data-stu-id="cd7bc-113">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="cd7bc-114">Las opiniones y la información expresados en este libro, incluidas las direcciones URL y otras referencias a sitios web de Internet, pueden cambiar sin previo aviso.</span><span class="sxs-lookup"><span data-stu-id="cd7bc-114">The views, opinions, and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="cd7bc-115">Algunos ejemplos descritos aquí se proporcionan únicamente con fines ilustrativos y son ficticios.</span><span class="sxs-lookup"><span data-stu-id="cd7bc-115">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="cd7bc-116">No debe deducirse ninguna asociación ni conexión reales.</span><span class="sxs-lookup"><span data-stu-id="cd7bc-116">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="cd7bc-117">Microsoft y las marcas comerciales indicadas en https://www.microsoft.com en la página web "Marcas comerciales" pertenecen al grupo de empresas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cd7bc-117">Microsoft and the trademarks listed at https://www.microsoft.com on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="cd7bc-118">Mac y macOS son marcas comerciales de Apple Inc.</span><span class="sxs-lookup"><span data-stu-id="cd7bc-118">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="cd7bc-119">El logotipo de la ballena de Docker es una marca registrada de Docker, Inc. Se usa con permiso.</span><span class="sxs-lookup"><span data-stu-id="cd7bc-119">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="cd7bc-120">El resto de marcas y logotipos pertenece a sus respectivos propietarios.</span><span class="sxs-lookup"><span data-stu-id="cd7bc-120">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="cd7bc-121">Autores:</span><span class="sxs-lookup"><span data-stu-id="cd7bc-121">Authors:</span></span>

> <span data-ttu-id="cd7bc-122">**Steve "ardalis" Smith**: instructor y arquitecto de software de [Ardalis.com](https://ardalis.com)</span><span class="sxs-lookup"><span data-stu-id="cd7bc-122">**Steve "ardalis" Smith** - Software Architect and Trainer - [Ardalis.com](https://ardalis.com)</span></span>
>
> <span data-ttu-id="cd7bc-123">**Rob Vettor**: arquitecto principal de IP y sistemas de Microsoft de [thinkingincloudnative.com](http://thinkingincloudnative.com/about/)</span><span class="sxs-lookup"><span data-stu-id="cd7bc-123">**Rob Vettor** - Microsoft - Principal Cloud System Architect/IP Architect - [thinkingincloudnative.com](http://thinkingincloudnative.com/about/)</span></span>

<span data-ttu-id="cd7bc-124">Participantes y revisores:</span><span class="sxs-lookup"><span data-stu-id="cd7bc-124">Participants and Reviewers:</span></span>

> <span data-ttu-id="cd7bc-125">**Cesar de la Torre**, administrador de programas principal, equipo de .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="cd7bc-125">**Cesar De la Torre**, Principal Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="cd7bc-126">**Nish Anil**, director de administración de programas, equipo de .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="cd7bc-126">**Nish Anil**, Sr. Program Manager, .NET team, Microsoft</span></span>

<span data-ttu-id="cd7bc-127">Editores:</span><span class="sxs-lookup"><span data-stu-id="cd7bc-127">Editors:</span></span>

> <span data-ttu-id="cd7bc-128">**Maira Wenzel**, desarrolladora de contenidos sénior, equipo de .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="cd7bc-128">**Maira Wenzel**, Sr. Content Developer, .NET team, Microsoft</span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="cd7bc-129">Destinatarios de esta guía</span><span class="sxs-lookup"><span data-stu-id="cd7bc-129">Who should use this guide</span></span>

<span data-ttu-id="cd7bc-130">Esta guía está dirigida principalmente a desarrolladores, responsables de desarrollo y arquitectos interesados en aprender a crear aplicaciones diseñadas para la nube.</span><span class="sxs-lookup"><span data-stu-id="cd7bc-130">The audience for this guide is mainly developers, development leads, and architects who are interested in learning how to build applications designed for the cloud.</span></span>

<span data-ttu-id="cd7bc-131">También puede resultar útil a aquellas personas responsables de tomar decisiones técnicas que tengan previsto elegir si quieren crear sus aplicaciones con un enfoque nativo en la nube.</span><span class="sxs-lookup"><span data-stu-id="cd7bc-131">A secondary audience is technical decision-makers who plan to choose whether to build their applications using a cloud-native approach.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="cd7bc-132">Cómo leer esta guía</span><span class="sxs-lookup"><span data-stu-id="cd7bc-132">How you can use this guide</span></span>

<span data-ttu-id="cd7bc-133">Esta guía empieza definiendo el enfoque nativo en la nube y presenta una aplicación de referencia creada mediante tecnologías y principios nativos en la nube.</span><span class="sxs-lookup"><span data-stu-id="cd7bc-133">This guide begins by defining cloud native and introducing a reference application built using cloud-native principles and technologies.</span></span> <span data-ttu-id="cd7bc-134">Tras los dos primeros capítulos, el resto del libro se divide en capítulos específicos centrados en temas comunes para la mayoría de las aplicaciones nativas en la nube.</span><span class="sxs-lookup"><span data-stu-id="cd7bc-134">Beyond these first two chapters, the rest of the book is broken up into specific chapters focused on topics common to most cloud-native applications.</span></span> <span data-ttu-id="cd7bc-135">Puede ir directamente a cualquiera de estos capítulos para obtener más información más sobre los enfoques nativos en la nube relativos a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cd7bc-135">You can jump to any of these chapters to learn about cloud-native approaches to:</span></span>

- <span data-ttu-id="cd7bc-136">Datos y acceso a datos</span><span class="sxs-lookup"><span data-stu-id="cd7bc-136">Data and data access</span></span>
- <span data-ttu-id="cd7bc-137">Patrones de comunicación</span><span class="sxs-lookup"><span data-stu-id="cd7bc-137">Communication patterns</span></span>
- <span data-ttu-id="cd7bc-138">Escalado y escalabilidad</span><span class="sxs-lookup"><span data-stu-id="cd7bc-138">Scaling and scalability</span></span>
- <span data-ttu-id="cd7bc-139">Resistencia de las aplicaciones</span><span class="sxs-lookup"><span data-stu-id="cd7bc-139">Application resiliency</span></span>
- <span data-ttu-id="cd7bc-140">Supervisión y estado</span><span class="sxs-lookup"><span data-stu-id="cd7bc-140">Monitoring and health</span></span>
- <span data-ttu-id="cd7bc-141">Identidad y seguridad</span><span class="sxs-lookup"><span data-stu-id="cd7bc-141">Identity and security</span></span>
- <span data-ttu-id="cd7bc-142">DevOps</span><span class="sxs-lookup"><span data-stu-id="cd7bc-142">DevOps</span></span>

<span data-ttu-id="cd7bc-143">Esta guía está disponible en formato PDF y en línea.</span><span class="sxs-lookup"><span data-stu-id="cd7bc-143">This guide is available both in PDF form and online.</span></span> <span data-ttu-id="cd7bc-144">No dude en reenviar este documento o los vínculos a la versión en línea a su equipo para que todos los miembros puedan consultarla.</span><span class="sxs-lookup"><span data-stu-id="cd7bc-144">Feel free to forward this document or links to its online version to your team to help ensure common understanding of these topics.</span></span> <span data-ttu-id="cd7bc-145">La mayoría de estos temas presentan unos conocimientos sólidos de los principios y los patrones subyacentes, así como los inconvenientes de las decisiones relacionadas con estos temas.</span><span class="sxs-lookup"><span data-stu-id="cd7bc-145">Most of these topics benefit from a consistent understanding of the underlying principles and patterns, as well as the trade-offs involved in decisions related to these topics.</span></span> <span data-ttu-id="cd7bc-146">Con este documento, nuestro objetivo es facilitar a los equipos y sus responsables la información necesaria para tomar decisiones fundamentadas en lo que respecta al diseño, el desarrollo y el hospedaje de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="cd7bc-146">Our goal with this document is to equip teams and their leaders with the information they need to make well-informed decisions for their applications' architecture, development, and hosting.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="cd7bc-147">Siguiente</span><span class="sxs-lookup"><span data-stu-id="cd7bc-147">Next</span></span>](introduction.md)
