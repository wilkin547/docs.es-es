---
title: Diseño de aplicaciones .NET nativas en la nube para Azure
description: Guía para crear aplicaciones nativas en la nube con la ayuda de contenedores, microservicios y características sin servidor de Azure.
author: ardalis
ms.date: 04/23/2020
ms.openlocfilehash: 24d5c75fc5d2e5623892e8f83daea52553d13765
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2020
ms.locfileid: "82507395"
---
# <a name="architecting-cloud-native-net-applications-for-azure"></a><span data-ttu-id="c9938-103">Diseño de aplicaciones .NET nativas en la nube para Azure</span><span class="sxs-lookup"><span data-stu-id="c9938-103">Architecting Cloud Native .NET Applications for Azure</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

![imagen de portada](./media/cover.png)

<span data-ttu-id="c9938-105">PUBLICADO POR</span><span class="sxs-lookup"><span data-stu-id="c9938-105">PUBLISHED BY</span></span>

<span data-ttu-id="c9938-106">Equipos de producto de la División de desarrolladores de Microsoft, .NET y Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c9938-106">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="c9938-107">División de Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="c9938-107">A division of Microsoft Corporation</span></span>

<span data-ttu-id="c9938-108">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="c9938-108">One Microsoft Way</span></span>

<span data-ttu-id="c9938-109">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="c9938-109">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="c9938-110">Copyright &copy; 2019; 2001-2003 de Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="c9938-110">Copyright &copy; 2019 by Microsoft Corporation</span></span>

<span data-ttu-id="c9938-111">Todos los derechos reservados.</span><span class="sxs-lookup"><span data-stu-id="c9938-111">All rights reserved.</span></span> <span data-ttu-id="c9938-112">No se puede reproducir ni transmitir de ninguna forma ni por ningún medio ninguna parte del contenido de este libro sin la autorización por escrito del publicador.</span><span class="sxs-lookup"><span data-stu-id="c9938-112">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="c9938-113">Este libro se proporciona “tal cual” y expresa las opiniones del autor.</span><span class="sxs-lookup"><span data-stu-id="c9938-113">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="c9938-114">Las opiniones y la información expresados en este libro, incluidas las direcciones URL y otras referencias a sitios web de Internet, pueden cambiar sin previo aviso.</span><span class="sxs-lookup"><span data-stu-id="c9938-114">The views, opinions, and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="c9938-115">Algunos ejemplos descritos aquí se proporcionan únicamente con fines ilustrativos y son ficticios.</span><span class="sxs-lookup"><span data-stu-id="c9938-115">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="c9938-116">No debe deducirse ninguna asociación ni conexión reales.</span><span class="sxs-lookup"><span data-stu-id="c9938-116">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="c9938-117">Microsoft y las marcas comerciales indicadas en https://www.microsoft.com en la página web "Marcas comerciales" pertenecen al grupo de empresas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c9938-117">Microsoft and the trademarks listed at https://www.microsoft.com on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="c9938-118">Mac y macOS son marcas comerciales de Apple Inc.</span><span class="sxs-lookup"><span data-stu-id="c9938-118">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="c9938-119">El logotipo de la ballena de Docker es una marca registrada de Docker, Inc. Se usa con permiso.</span><span class="sxs-lookup"><span data-stu-id="c9938-119">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="c9938-120">El resto de marcas y logotipos pertenece a sus respectivos propietarios.</span><span class="sxs-lookup"><span data-stu-id="c9938-120">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="c9938-121">Autores:</span><span class="sxs-lookup"><span data-stu-id="c9938-121">Authors:</span></span>

> <span data-ttu-id="c9938-122">**Rob Vettor**, arquitecto principal de IP y sistemas de [thinkingincloudnative.com](http://thinkingincloudnative.com/about/), Microsoft</span><span class="sxs-lookup"><span data-stu-id="c9938-122">**Rob Vettor**, Principal Cloud System Architect/IP Architect - [thinkingincloudnative.com](http://thinkingincloudnative.com/about/), Microsoft</span></span>
>
> <span data-ttu-id="c9938-123">**Steve "ardalis" Smith**, instructor y arquitecto de software de [Ardalis.com](https://ardalis.com)</span><span class="sxs-lookup"><span data-stu-id="c9938-123">**Steve "ardalis" Smith**, Software Architect and Trainer - [Ardalis.com](https://ardalis.com)</span></span>

<span data-ttu-id="c9938-124">Participantes y revisores:</span><span class="sxs-lookup"><span data-stu-id="c9938-124">Participants and Reviewers:</span></span>

> <span data-ttu-id="c9938-125">**Cesar de la Torre**, administrador de programas principal, equipo de .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="c9938-125">**Cesar De la Torre**, Principal Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="c9938-126">**Nish Anil**, director de administración de programas, equipo de .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="c9938-126">**Nish Anil**, Senior Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="c9938-127">**Jeremy Likness**, director de administración de programas, equipo de .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="c9938-127">**Jeremy Likness**, Senior Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="c9938-128">**Cecil Phillip**, director de promoción de la nube, Microsoft</span><span class="sxs-lookup"><span data-stu-id="c9938-128">**Cecil Phillip**, Senior Cloud Advocate, Microsoft</span></span>

<span data-ttu-id="c9938-129">Más información sobre eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="c9938-129">Learn more about eShopOnContainers</span></span>

<span data-ttu-id="c9938-130">Editores:</span><span class="sxs-lookup"><span data-stu-id="c9938-130">Editors:</span></span>

> <span data-ttu-id="c9938-131">**Maira Wenzel**, directora de administración de programas, equipo de .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="c9938-131">**Maira Wenzel**, Program Manager, .NET team, Microsoft</span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="c9938-132">Destinatarios de esta guía</span><span class="sxs-lookup"><span data-stu-id="c9938-132">Who should use this guide</span></span>

<span data-ttu-id="c9938-133">Esta guía está dirigida principalmente a desarrolladores, responsables de desarrollo y arquitectos interesados en aprender a crear aplicaciones diseñadas para la nube.</span><span class="sxs-lookup"><span data-stu-id="c9938-133">The audience for this guide is mainly developers, development leads, and architects who are interested in learning how to build applications designed for the cloud.</span></span>

<span data-ttu-id="c9938-134">También puede resultar útil a aquellas personas responsables de tomar decisiones técnicas que tengan previsto elegir si quieren crear sus aplicaciones con un enfoque nativo en la nube.</span><span class="sxs-lookup"><span data-stu-id="c9938-134">A secondary audience is technical decision-makers who plan to choose whether to build their applications using a cloud-native approach.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="c9938-135">Cómo leer esta guía</span><span class="sxs-lookup"><span data-stu-id="c9938-135">How you can use this guide</span></span>

<span data-ttu-id="c9938-136">Esta guía empieza definiendo el enfoque nativo en la nube y presenta una aplicación de referencia creada mediante tecnologías y principios nativos en la nube.</span><span class="sxs-lookup"><span data-stu-id="c9938-136">This guide begins by defining cloud native and introducing a reference application built using cloud-native principles and technologies.</span></span> <span data-ttu-id="c9938-137">Tras los dos primeros capítulos, el resto del libro se divide en capítulos específicos centrados en temas comunes para la mayoría de las aplicaciones nativas en la nube.</span><span class="sxs-lookup"><span data-stu-id="c9938-137">Beyond these first two chapters, the rest of the book is broken up into specific chapters focused on topics common to most cloud-native applications.</span></span> <span data-ttu-id="c9938-138">Puede ir directamente a cualquiera de estos capítulos para obtener más información más sobre los enfoques nativos en la nube relativos a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c9938-138">You can jump to any of these chapters to learn about cloud-native approaches to:</span></span>

- <span data-ttu-id="c9938-139">Datos y acceso a datos</span><span class="sxs-lookup"><span data-stu-id="c9938-139">Data and data access</span></span>
- <span data-ttu-id="c9938-140">Patrones de comunicación</span><span class="sxs-lookup"><span data-stu-id="c9938-140">Communication patterns</span></span>
- <span data-ttu-id="c9938-141">Escalado y escalabilidad</span><span class="sxs-lookup"><span data-stu-id="c9938-141">Scaling and scalability</span></span>
- <span data-ttu-id="c9938-142">Resistencia de las aplicaciones</span><span class="sxs-lookup"><span data-stu-id="c9938-142">Application resiliency</span></span>
- <span data-ttu-id="c9938-143">Supervisión y estado</span><span class="sxs-lookup"><span data-stu-id="c9938-143">Monitoring and health</span></span>
- <span data-ttu-id="c9938-144">Identidad y seguridad</span><span class="sxs-lookup"><span data-stu-id="c9938-144">Identity and security</span></span>
- <span data-ttu-id="c9938-145">DevOps</span><span class="sxs-lookup"><span data-stu-id="c9938-145">DevOps</span></span>

<span data-ttu-id="c9938-146">Esta guía está disponible en formato PDF y en línea.</span><span class="sxs-lookup"><span data-stu-id="c9938-146">This guide is available both in PDF form and online.</span></span> <span data-ttu-id="c9938-147">No dude en reenviar este documento o los vínculos a la versión en línea a su equipo para que todos los miembros puedan consultarla.</span><span class="sxs-lookup"><span data-stu-id="c9938-147">Feel free to forward this document or links to its online version to your team to help ensure common understanding of these topics.</span></span> <span data-ttu-id="c9938-148">La mayoría de estos temas presentan unos conocimientos sólidos de los principios y los patrones subyacentes, así como los inconvenientes de las decisiones relacionadas con estos temas.</span><span class="sxs-lookup"><span data-stu-id="c9938-148">Most of these topics benefit from a consistent understanding of the underlying principles and patterns, as well as the trade-offs involved in decisions related to these topics.</span></span> <span data-ttu-id="c9938-149">Con este documento, nuestro objetivo es facilitar a los equipos y sus responsables la información necesaria para tomar decisiones fundamentadas en lo que respecta al diseño, el desarrollo y el hospedaje de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="c9938-149">Our goal with this document is to equip teams and their leaders with the information they need to make well-informed decisions for their applications' architecture, development, and hosting.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="c9938-150">Siguiente</span><span class="sxs-lookup"><span data-stu-id="c9938-150">Next</span></span>](introduction.md)
