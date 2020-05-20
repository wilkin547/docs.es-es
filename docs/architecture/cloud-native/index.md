---
title: Diseño de aplicaciones .NET nativas en la nube para Azure
description: Guía para crear aplicaciones nativas en la nube con la ayuda de contenedores, microservicios y características sin servidor de Azure.
author: ardalis
ms.date: 05/13/2020
ms.openlocfilehash: 1607c1bbcc9bbb3c9fe19840a2827aa5ea083728
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614009"
---
# <a name="architecting-cloud-native-net-applications-for-azure"></a><span data-ttu-id="39dbc-103">Diseño de aplicaciones .NET nativas en la nube para Azure</span><span class="sxs-lookup"><span data-stu-id="39dbc-103">Architecting Cloud Native .NET Applications for Azure</span></span>

![imagen de portada](./media/cover.png)

<span data-ttu-id="39dbc-105">**EDICIÓN 1.0**</span><span class="sxs-lookup"><span data-stu-id="39dbc-105">**EDITION v.1.0**</span></span>

<span data-ttu-id="39dbc-106">PUBLICADO POR</span><span class="sxs-lookup"><span data-stu-id="39dbc-106">PUBLISHED BY</span></span>

<span data-ttu-id="39dbc-107">Equipos de producto de la División de desarrolladores de Microsoft, .NET y Visual Studio</span><span class="sxs-lookup"><span data-stu-id="39dbc-107">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="39dbc-108">División de Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="39dbc-108">A division of Microsoft Corporation</span></span>

<span data-ttu-id="39dbc-109">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="39dbc-109">One Microsoft Way</span></span>

<span data-ttu-id="39dbc-110">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="39dbc-110">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="39dbc-111">Copyright &copy; 2020 de Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="39dbc-111">Copyright &copy; 2020 by Microsoft Corporation</span></span>

<span data-ttu-id="39dbc-112">Todos los derechos reservados.</span><span class="sxs-lookup"><span data-stu-id="39dbc-112">All rights reserved.</span></span> <span data-ttu-id="39dbc-113">No se puede reproducir ni transmitir de ninguna forma ni por ningún medio ninguna parte del contenido de este libro sin la autorización por escrito del publicador.</span><span class="sxs-lookup"><span data-stu-id="39dbc-113">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="39dbc-114">Este libro se proporciona “tal cual” y expresa las opiniones del autor.</span><span class="sxs-lookup"><span data-stu-id="39dbc-114">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="39dbc-115">Las opiniones y la información expresados en este libro, incluidas las direcciones URL y otras referencias a sitios web de Internet, pueden cambiar sin previo aviso.</span><span class="sxs-lookup"><span data-stu-id="39dbc-115">The views, opinions, and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="39dbc-116">Algunos ejemplos descritos aquí se proporcionan únicamente con fines ilustrativos y son ficticios.</span><span class="sxs-lookup"><span data-stu-id="39dbc-116">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="39dbc-117">No debe deducirse ninguna asociación ni conexión reales.</span><span class="sxs-lookup"><span data-stu-id="39dbc-117">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="39dbc-118">Microsoft y las marcas comerciales indicadas en https://www.microsoft.com en la página web "Marcas comerciales" pertenecen al grupo de empresas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="39dbc-118">Microsoft and the trademarks listed at https://www.microsoft.com on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="39dbc-119">Mac y macOS son marcas comerciales de Apple Inc.</span><span class="sxs-lookup"><span data-stu-id="39dbc-119">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="39dbc-120">El logotipo de la ballena de Docker es una marca registrada de Docker, Inc. Se usa con permiso.</span><span class="sxs-lookup"><span data-stu-id="39dbc-120">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="39dbc-121">El resto de marcas y logotipos pertenece a sus respectivos propietarios.</span><span class="sxs-lookup"><span data-stu-id="39dbc-121">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="39dbc-122">Autores:</span><span class="sxs-lookup"><span data-stu-id="39dbc-122">Authors:</span></span>

> <span data-ttu-id="39dbc-123">**Rob Vettor**, arquitecto principal de IP y sistemas de [thinkingincloudnative.com](http://thinkingincloudnative.com/about/), Microsoft</span><span class="sxs-lookup"><span data-stu-id="39dbc-123">**Rob Vettor**, Principal Cloud System Architect/IP Architect - [thinkingincloudnative.com](http://thinkingincloudnative.com/about/), Microsoft</span></span>
>
> <span data-ttu-id="39dbc-124">**Steve "ardalis" Smith**, instructor y arquitecto de software de [Ardalis.com](https://ardalis.com)</span><span class="sxs-lookup"><span data-stu-id="39dbc-124">**Steve "ardalis" Smith**, Software Architect and Trainer - [Ardalis.com](https://ardalis.com)</span></span>

<span data-ttu-id="39dbc-125">Participantes y revisores:</span><span class="sxs-lookup"><span data-stu-id="39dbc-125">Participants and Reviewers:</span></span>

> <span data-ttu-id="39dbc-126">**Cesar de la Torre**, administrador de programas principal, equipo de .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="39dbc-126">**Cesar De la Torre**, Principal Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="39dbc-127">**Nish Anil**, director de administración de programas, equipo de .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="39dbc-127">**Nish Anil**, Senior Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="39dbc-128">**Jeremy Likness**, director de administración de programas, equipo de .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="39dbc-128">**Jeremy Likness**, Senior Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="39dbc-129">**Cecil Phillip**, director de promoción de la nube, Microsoft</span><span class="sxs-lookup"><span data-stu-id="39dbc-129">**Cecil Phillip**, Senior Cloud Advocate, Microsoft</span></span>

<span data-ttu-id="39dbc-130">Editores:</span><span class="sxs-lookup"><span data-stu-id="39dbc-130">Editors:</span></span>

> <span data-ttu-id="39dbc-131">**Maira Wenzel**, directora de administración de programas, equipo de .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="39dbc-131">**Maira Wenzel**, Program Manager, .NET team, Microsoft</span></span>

## <a name="version"></a><span data-ttu-id="39dbc-132">Versión</span><span class="sxs-lookup"><span data-stu-id="39dbc-132">Version</span></span>

<span data-ttu-id="39dbc-133">Esta guía se ha redactado para **.NET Core 3.1**, junto con muchas actualizaciones adicionales relacionadas con la misma "ola" de tecnologías (es decir, Azure y otras tecnologías de terceros) que coincidan en el tiempo con .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="39dbc-133">This guide has been written to cover **.NET Core 3.1** version along with many additional updates related to the same “wave” of technologies (that is, Azure and additional third-party technologies) coinciding in time with the .NET Core 3.1 release.</span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="39dbc-134">Destinatarios de esta guía</span><span class="sxs-lookup"><span data-stu-id="39dbc-134">Who should use this guide</span></span>

<span data-ttu-id="39dbc-135">Esta guía está dirigida principalmente a desarrolladores, responsables de desarrollo y arquitectos interesados en aprender a crear aplicaciones diseñadas para la nube.</span><span class="sxs-lookup"><span data-stu-id="39dbc-135">The audience for this guide is mainly developers, development leads, and architects who are interested in learning how to build applications designed for the cloud.</span></span>

<span data-ttu-id="39dbc-136">También puede resultar útil a aquellas personas responsables de tomar decisiones técnicas que tengan previsto elegir si quieren crear sus aplicaciones con un enfoque nativo en la nube.</span><span class="sxs-lookup"><span data-stu-id="39dbc-136">A secondary audience is technical decision-makers who plan to choose whether to build their applications using a cloud-native approach.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="39dbc-137">Cómo leer esta guía</span><span class="sxs-lookup"><span data-stu-id="39dbc-137">How you can use this guide</span></span>

<span data-ttu-id="39dbc-138">Esta guía empieza definiendo el enfoque nativo en la nube y presenta una aplicación de referencia creada mediante tecnologías y principios nativos en la nube.</span><span class="sxs-lookup"><span data-stu-id="39dbc-138">This guide begins by defining cloud native and introducing a reference application built using cloud-native principles and technologies.</span></span> <span data-ttu-id="39dbc-139">Tras los dos primeros capítulos, el resto del libro se divide en capítulos específicos centrados en temas comunes para la mayoría de las aplicaciones nativas en la nube.</span><span class="sxs-lookup"><span data-stu-id="39dbc-139">Beyond these first two chapters, the rest of the book is broken up into specific chapters focused on topics common to most cloud-native applications.</span></span> <span data-ttu-id="39dbc-140">Puede ir directamente a cualquiera de estos capítulos para obtener más información más sobre los enfoques nativos en la nube relativos a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="39dbc-140">You can jump to any of these chapters to learn about cloud-native approaches to:</span></span>

- <span data-ttu-id="39dbc-141">Datos y acceso a datos</span><span class="sxs-lookup"><span data-stu-id="39dbc-141">Data and data access</span></span>
- <span data-ttu-id="39dbc-142">Patrones de comunicación</span><span class="sxs-lookup"><span data-stu-id="39dbc-142">Communication patterns</span></span>
- <span data-ttu-id="39dbc-143">Escalado y escalabilidad</span><span class="sxs-lookup"><span data-stu-id="39dbc-143">Scaling and scalability</span></span>
- <span data-ttu-id="39dbc-144">Resistencia de las aplicaciones</span><span class="sxs-lookup"><span data-stu-id="39dbc-144">Application resiliency</span></span>
- <span data-ttu-id="39dbc-145">Supervisión y estado</span><span class="sxs-lookup"><span data-stu-id="39dbc-145">Monitoring and health</span></span>
- <span data-ttu-id="39dbc-146">Identidad y seguridad</span><span class="sxs-lookup"><span data-stu-id="39dbc-146">Identity and security</span></span>
- <span data-ttu-id="39dbc-147">DevOps</span><span class="sxs-lookup"><span data-stu-id="39dbc-147">DevOps</span></span>

<span data-ttu-id="39dbc-148">Esta guía está disponible en formato PDF y en línea.</span><span class="sxs-lookup"><span data-stu-id="39dbc-148">This guide is available both in PDF form and online.</span></span> <span data-ttu-id="39dbc-149">No dude en reenviar este documento o los vínculos a la versión en línea a su equipo para que todos los miembros puedan consultarla.</span><span class="sxs-lookup"><span data-stu-id="39dbc-149">Feel free to forward this document or links to its online version to your team to help ensure common understanding of these topics.</span></span> <span data-ttu-id="39dbc-150">La mayoría de estos temas presentan unos conocimientos sólidos de los principios y los patrones subyacentes, así como los inconvenientes de las decisiones relacionadas con estos temas.</span><span class="sxs-lookup"><span data-stu-id="39dbc-150">Most of these topics benefit from a consistent understanding of the underlying principles and patterns, as well as the trade-offs involved in decisions related to these topics.</span></span> <span data-ttu-id="39dbc-151">Con este documento, nuestro objetivo es facilitar a los equipos y sus responsables la información necesaria para tomar decisiones fundamentadas en lo que respecta al diseño, el desarrollo y el hospedaje de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="39dbc-151">Our goal with this document is to equip teams and their leaders with the information they need to make well-informed decisions for their applications' architecture, development, and hosting.</span></span>

## <a name="send-your-feedback"></a><span data-ttu-id="39dbc-152">Envíe sus comentarios</span><span class="sxs-lookup"><span data-stu-id="39dbc-152">Send your feedback</span></span>

<span data-ttu-id="39dbc-153">Nos gustaría recibir sus comentarios al respecto para contribuir al desarrollo constante del libro y sus ejemplos relacionados.</span><span class="sxs-lookup"><span data-stu-id="39dbc-153">This book and related samples are constantly evolving, so your feedback is welcomed!</span></span> <span data-ttu-id="39dbc-154">Si tiene algún comentario sobre cómo mejorar este libro, escríbalo en la sección pertinente situada en la parte inferior de cualquier página creada en [Problemas de GitHub](https://github.com/dotnet/docs/issues).</span><span class="sxs-lookup"><span data-stu-id="39dbc-154">If you have comments about how this book can be improved, use the feedback section at the bottom of any page built on [GitHub issues](https://github.com/dotnet/docs/issues).</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="39dbc-155">Siguiente</span><span class="sxs-lookup"><span data-stu-id="39dbc-155">Next</span></span>](introduction.md)
