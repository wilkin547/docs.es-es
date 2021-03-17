---
title: Dapr para desarrolladores de .NET
description: Una guía para que los desarrolladores de .NET comprendan y aprovechen toda la eficacia de Distributed Apps Runtime de código abierto de Microsoft.
author: robvet
ms.date: 02/17/2021
ms.openlocfilehash: 2ab66257cca6f99074e2aa45a24869012b4976fe
ms.sourcegitcommit: d623f686701b94bef905ec5e93d8b55d031c5d6f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2021
ms.locfileid: "103623725"
---
# <a name="dapr-for-net-developers"></a><span data-ttu-id="7dea4-103">Dapr para desarrolladores de .NET</span><span class="sxs-lookup"><span data-stu-id="7dea4-103">Dapr for .NET Developers</span></span>

![imagen de portada](./media/cover.png)

<span data-ttu-id="7dea4-105">**EDICIÓN EN VERSIÓN PRELIMINAR**</span><span class="sxs-lookup"><span data-stu-id="7dea4-105">**PREVIEW EDITION**</span></span>

<span data-ttu-id="7dea4-106">PUBLICADO POR</span><span class="sxs-lookup"><span data-stu-id="7dea4-106">PUBLISHED BY</span></span>

<span data-ttu-id="7dea4-107">Equipos de Microsoft Developer Division, .NET y Azure Incubations</span><span class="sxs-lookup"><span data-stu-id="7dea4-107">Microsoft Developer Division, .NET, and Azure Incubations teams</span></span>

<span data-ttu-id="7dea4-108">División de Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="7dea4-108">A division of Microsoft Corporation</span></span>

<span data-ttu-id="7dea4-109">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="7dea4-109">One Microsoft Way</span></span>

<span data-ttu-id="7dea4-110">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="7dea4-110">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="7dea4-111">Copyright &copy; 2021 de Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="7dea4-111">Copyright &copy; 2021 by Microsoft Corporation</span></span>

<span data-ttu-id="7dea4-112">Todos los derechos reservados.</span><span class="sxs-lookup"><span data-stu-id="7dea4-112">All rights reserved.</span></span> <span data-ttu-id="7dea4-113">No se puede reproducir ni transmitir de ninguna forma ni por ningún medio ninguna parte del contenido de este libro sin la autorización por escrito del publicador.</span><span class="sxs-lookup"><span data-stu-id="7dea4-113">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="7dea4-114">Este libro se proporciona “tal cual” y expresa las opiniones del autor.</span><span class="sxs-lookup"><span data-stu-id="7dea4-114">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="7dea4-115">Las opiniones y la información expresados en este libro, incluidas las direcciones URL y otras referencias a sitios web de Internet, pueden cambiar sin previo aviso.</span><span class="sxs-lookup"><span data-stu-id="7dea4-115">The views, opinions, and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="7dea4-116">Algunos ejemplos descritos aquí se proporcionan únicamente con fines ilustrativos y son ficticios.</span><span class="sxs-lookup"><span data-stu-id="7dea4-116">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="7dea4-117">No debe deducirse ninguna asociación ni conexión reales.</span><span class="sxs-lookup"><span data-stu-id="7dea4-117">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="7dea4-118">Microsoft y las marcas comerciales indicadas en <https://www.microsoft.com> en la página web "Marcas comerciales" pertenecen al grupo de empresas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7dea4-118">Microsoft and the trademarks listed at <https://www.microsoft.com> on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="7dea4-119">Mac y macOS son marcas comerciales de Apple Inc.</span><span class="sxs-lookup"><span data-stu-id="7dea4-119">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="7dea4-120">El logotipo de la ballena de Docker es una marca registrada de Docker, Inc. Se usa con permiso.</span><span class="sxs-lookup"><span data-stu-id="7dea4-120">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="7dea4-121">El resto de marcas y logotipos pertenece a sus respectivos propietarios.</span><span class="sxs-lookup"><span data-stu-id="7dea4-121">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="7dea4-122">Autores:</span><span class="sxs-lookup"><span data-stu-id="7dea4-122">Authors:</span></span>

> <span data-ttu-id="7dea4-123">**Rob Vettor**, arquitecto principal de soluciones en la nube, [thinkingincloudnative.com](https://thinkingincloudnative.com/about/), Microsoft</span><span class="sxs-lookup"><span data-stu-id="7dea4-123">**Rob Vettor**, Principal Cloud Solution Architect - [thinkingincloudnative.com](https://thinkingincloudnative.com/about/), Microsoft</span></span>
>
> <span data-ttu-id="7dea4-124">**Sander Molenkamp**, arquitecto de la nube principal/MVP de Microsoft, [sandermolenkamp.com](https://www.sandermolenkamp.com), [Info Support](https://www.infosupport.com/en/)</span><span class="sxs-lookup"><span data-stu-id="7dea4-124">**Sander Molenkamp**, Principal Cloud Architect/Microsoft MVP - [sandermolenkamp.com](https://www.sandermolenkamp.com), [Info Support](https://www.infosupport.com/en/)</span></span>
>
> <span data-ttu-id="7dea4-125">**Edwin van Wijk**, arquitecto de soluciones principales/MVP de Microsoft,[defaultconstructor.com](https://defaultconstructor.com), [Info Support](https://www.infosupport.com/en/)</span><span class="sxs-lookup"><span data-stu-id="7dea4-125">**Edwin van Wijk**, Principal Solution Architect/Microsoft MVP - [defaultconstructor.com](https://defaultconstructor.com), [Info Support](https://www.infosupport.com/en/)</span></span>

<span data-ttu-id="7dea4-126">Participantes y revisores:</span><span class="sxs-lookup"><span data-stu-id="7dea4-126">Participants and Reviewers:</span></span>

> <span data-ttu-id="7dea4-127">**Mark Russinovich**, CTO de Azure y técnico, Azure Office de CTO, Microsoft</span><span class="sxs-lookup"><span data-stu-id="7dea4-127">**Mark Russinovich**, Azure CTO and Technical Fellow, Azure Office of CTO, Microsoft</span></span>
>
> <span data-ttu-id="7dea4-128">**Nish Anil**, director de administración de programas, equipo de .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="7dea4-128">**Nish Anil**, Senior Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="7dea4-129">**Mark Fussell**, director de programas principales, Azure Incubations, Microsoft</span><span class="sxs-lookup"><span data-stu-id="7dea4-129">**Mark Fussell**, Principal Program Manager, Azure Incubations, Microsoft</span></span>
>
> <span data-ttu-id="7dea4-130">**Yaron Schneider**, ingeniero de software principal, Azure Incubations, Microsoft</span><span class="sxs-lookup"><span data-stu-id="7dea4-130">**Yaron Schneider**, Principal Software Engineer, Azure Incubations, Microsoft</span></span>
>
> <span data-ttu-id="7dea4-131">**Ori Zohar**, director de programas sénior, Azure Incubations, Microsoft</span><span class="sxs-lookup"><span data-stu-id="7dea4-131">**Ori Zohar**, Senior Program Manager, Azure Incubations, Microsoft</span></span>

<span data-ttu-id="7dea4-132">Editores:</span><span class="sxs-lookup"><span data-stu-id="7dea4-132">Editors:</span></span>

> <span data-ttu-id="7dea4-133">**David Pine**, desarrollador de contenidos sénior, equipo de .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="7dea4-133">**David Pine**, Senior Content Developer, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="7dea4-134">**Maira Wenzel**, administradora de programas sénior, equipo de .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="7dea4-134">**Maira Wenzel**, Senior Program Manager, .NET team, Microsoft</span></span>

## <a name="version"></a><span data-ttu-id="7dea4-135">Versión</span><span class="sxs-lookup"><span data-stu-id="7dea4-135">Version</span></span>

<span data-ttu-id="7dea4-136">Esta guía se ha escrito para cubrir la versión **Dapr 1.0**.</span><span class="sxs-lookup"><span data-stu-id="7dea4-136">This guide has been written to cover the **Dapr 1.0** version.</span></span> <span data-ttu-id="7dea4-137">Los ejemplos de .NET Core se basan en **.NET Core 3.1**.</span><span class="sxs-lookup"><span data-stu-id="7dea4-137">.NET Core samples are based on **.NET Core 3.1**.</span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="7dea4-138">Destinatarios de esta guía</span><span class="sxs-lookup"><span data-stu-id="7dea4-138">Who should use this guide</span></span>

<span data-ttu-id="7dea4-139">Esta guía está dirigida principalmente a desarrolladores, responsables de desarrollo y arquitectos interesados en aprender a crear aplicaciones diseñadas para la nube.</span><span class="sxs-lookup"><span data-stu-id="7dea4-139">The audience for this guide is mainly developers, development leads, and architects who are interested in learning how to build applications designed for the cloud.</span></span>

<span data-ttu-id="7dea4-140">También puede resultar útil a aquellas personas responsables de tomar decisiones técnicas que tengan previsto elegir si quieren crear sus aplicaciones con un enfoque nativo en la nube.</span><span class="sxs-lookup"><span data-stu-id="7dea4-140">A secondary audience is technical decision-makers who plan to choose whether to build their applications using a cloud-native approach.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="7dea4-141">Cómo leer esta guía</span><span class="sxs-lookup"><span data-stu-id="7dea4-141">How you can use this guide</span></span>

<span data-ttu-id="7dea4-142">Esta guía está disponible en formato [PDF](https://aka.ms/dapr-ebook) y en línea.</span><span class="sxs-lookup"><span data-stu-id="7dea4-142">This guide is available both in [PDF](https://aka.ms/dapr-ebook) form and online.</span></span> <span data-ttu-id="7dea4-143">No dude en reenviar este documento o los vínculos a la versión en línea a su equipo para que todos los miembros puedan consultarla.</span><span class="sxs-lookup"><span data-stu-id="7dea4-143">Feel free to forward this document or links to its online version to your team to help ensure common understanding of these topics.</span></span> <span data-ttu-id="7dea4-144">La mayoría de estos temas presentan unos conocimientos sólidos de los principios y los patrones subyacentes, así como los inconvenientes de las decisiones relacionadas con estos temas.</span><span class="sxs-lookup"><span data-stu-id="7dea4-144">Most of these topics benefit from a consistent understanding of the underlying principles and patterns, as well as the trade-offs involved in decisions related to these topics.</span></span> <span data-ttu-id="7dea4-145">Con este documento, nuestro objetivo es facilitar a los equipos y sus responsables la información necesaria para tomar decisiones fundamentadas en lo que respecta al diseño, el desarrollo y el hospedaje de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="7dea4-145">Our goal with this document is to equip teams and their leaders with the information they need to make well-informed decisions for their applications' architecture, development, and hosting.</span></span>

## <a name="send-your-feedback"></a><span data-ttu-id="7dea4-146">Envíe sus comentarios</span><span class="sxs-lookup"><span data-stu-id="7dea4-146">Send your feedback</span></span>

<span data-ttu-id="7dea4-147">Nos gustaría recibir sus comentarios al respecto para contribuir al desarrollo constante del libro y sus ejemplos relacionados.</span><span class="sxs-lookup"><span data-stu-id="7dea4-147">This book and related samples are constantly evolving, so your feedback is welcomed!</span></span> <span data-ttu-id="7dea4-148">Si tiene algún comentario sobre cómo mejorar este libro, escríbalo en la sección pertinente situada en la parte inferior de cualquier página creada en [Problemas de GitHub](https://github.com/dotnet/docs/issues).</span><span class="sxs-lookup"><span data-stu-id="7dea4-148">If you have comments about how this book can be improved, use the feedback section at the bottom of any page built on [GitHub issues](https://github.com/dotnet/docs/issues).</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="7dea4-149">Siguiente</span><span class="sxs-lookup"><span data-stu-id="7dea4-149">Next</span></span>](foreword.md)
