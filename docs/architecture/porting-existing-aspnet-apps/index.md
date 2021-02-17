---
title: Migración de aplicaciones existentes de ASP.NET a .NET Core
description: Una guía gratuita para convertir aplicaciones de ASP.NET MVC y Web API a ASP.NET Core.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 36c0cdbe03fb97ae82336d53e15be2108e9c6367
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100488169"
---
# <a name="porting-existing-aspnet-apps-to-net-core"></a><span data-ttu-id="af0d9-103">Migración de aplicaciones existentes de ASP.NET a .NET Core</span><span class="sxs-lookup"><span data-stu-id="af0d9-103">Porting Existing ASP.NET Apps to .NET Core</span></span>

![imagen de portada](./media/index/porting-existing-aspnet-apps.png)

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="af0d9-105">PUBLICADO POR</span><span class="sxs-lookup"><span data-stu-id="af0d9-105">PUBLISHED BY</span></span>

<span data-ttu-id="af0d9-106">Equipos de producto de la División de desarrolladores de Microsoft, .NET y Visual Studio</span><span class="sxs-lookup"><span data-stu-id="af0d9-106">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="af0d9-107">División de Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="af0d9-107">A division of Microsoft Corporation</span></span>

<span data-ttu-id="af0d9-108">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="af0d9-108">One Microsoft Way</span></span>

<span data-ttu-id="af0d9-109">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="af0d9-109">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="af0d9-110">Copyright &copy; 2020 de Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="af0d9-110">Copyright &copy; 2020 by Microsoft Corporation</span></span>

<span data-ttu-id="af0d9-111">Todos los derechos reservados.</span><span class="sxs-lookup"><span data-stu-id="af0d9-111">All rights reserved.</span></span> <span data-ttu-id="af0d9-112">No se puede reproducir ni transmitir de ninguna forma ni por ningún medio ninguna parte del contenido de este libro sin la autorización por escrito del publicador.</span><span class="sxs-lookup"><span data-stu-id="af0d9-112">No part of this book's contents may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="af0d9-113">Este libro se proporciona “tal cual” y expresa las opiniones del autor.</span><span class="sxs-lookup"><span data-stu-id="af0d9-113">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="af0d9-114">Las opiniones y la información expresados en este libro, incluidas las direcciones URL y otras referencias a sitios web de Internet, pueden cambiar sin previo aviso.</span><span class="sxs-lookup"><span data-stu-id="af0d9-114">The views, opinions, and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="af0d9-115">Algunos ejemplos descritos aquí se proporcionan únicamente con fines ilustrativos y son ficticios.</span><span class="sxs-lookup"><span data-stu-id="af0d9-115">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="af0d9-116">No debe deducirse ninguna asociación ni conexión reales.</span><span class="sxs-lookup"><span data-stu-id="af0d9-116">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="af0d9-117">Microsoft y las marcas comerciales indicadas en <https://www.microsoft.com> en la página web "Marcas comerciales" pertenecen al grupo de empresas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="af0d9-117">Microsoft and the trademarks listed at <https://www.microsoft.com> on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="af0d9-118">Mac y macOS son marcas comerciales de Apple Inc.</span><span class="sxs-lookup"><span data-stu-id="af0d9-118">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="af0d9-119">El logotipo de la ballena de Docker es una marca registrada de Docker, Inc. Se usa con permiso.</span><span class="sxs-lookup"><span data-stu-id="af0d9-119">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="af0d9-120">El resto de marcas y logotipos pertenece a sus respectivos propietarios.</span><span class="sxs-lookup"><span data-stu-id="af0d9-120">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="af0d9-121">Autores:</span><span class="sxs-lookup"><span data-stu-id="af0d9-121">Authors:</span></span>

> <span data-ttu-id="af0d9-122">**Steve "ardalis" Smith**, instructor y arquitecto de software de [Ardalis.com](https://ardalis.com)</span><span class="sxs-lookup"><span data-stu-id="af0d9-122">**Steve "ardalis" Smith**, Software Architect and Trainer - [Ardalis.com](https://ardalis.com)</span></span>

<span data-ttu-id="af0d9-123">Participantes y revisores:</span><span class="sxs-lookup"><span data-stu-id="af0d9-123">Participants and Reviewers:</span></span>

> <span data-ttu-id="af0d9-124">**Nish Anil**, director de administración de programas, equipo de .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="af0d9-124">**Nish Anil**, Senior Program Manager, .NET team, Microsoft</span></span>

> <span data-ttu-id="af0d9-125">**Mike Rousos**, ingeniero de software principal, equipo de .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="af0d9-125">**Mike Rousos**, Principal Software Engineer, .NET team, Microsoft</span></span>

> <span data-ttu-id="af0d9-126">**Scott Addie**, desarrollador de contenidos sénior, equipo de .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="af0d9-126">**Scott Addie**, Senior Content Developer, .NET team, Microsoft</span></span>

> <span data-ttu-id="af0d9-127">**David Pine**, desarrollador de contenidos sénior, equipo de .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="af0d9-127">**David Pine**, Senior Content Developer, .NET team, Microsoft</span></span>

## <a name="version"></a><span data-ttu-id="af0d9-128">Versión</span><span class="sxs-lookup"><span data-stu-id="af0d9-128">Version</span></span>

<span data-ttu-id="af0d9-129">En esta guía se describe **.NET Core 3.1** y las actualizaciones relacionadas con la misma "ola" tecnológica (esto es, Azure y otras tecnologías de terceros) que coincidan en el tiempo con la versión de .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="af0d9-129">This guide covers **.NET Core 3.1** and updates related to the same technology "wave" (that is, Azure and other third-party technologies) coinciding in time with the .NET Core 3.1 release.</span></span> <span data-ttu-id="af0d9-130">La actualización de .NET Core 3.1 a .NET 5.0 (la versión siguiente) es relativamente sencilla y, por lo tanto, requiere menos esfuerzo que la migración de .NET Framework a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="af0d9-130">Updating from .NET Core 3.1 to .NET 5.0 (the next version) is relatively straightforward and certainly will require substantially less effort than porting from .NET Framework to .NET Core.</span></span> <span data-ttu-id="af0d9-131">La migración de .NET Framework 4.x a .NET 5.0 será similar a la migración a .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="af0d9-131">Migrating from .NET Framework 4.x to .NET 5.0 will be similar to migrating to .NET Core 3.1.</span></span> <span data-ttu-id="af0d9-132">Para obtener más información, vea [Selección de la versión correcta de .NET Core](choose-net-core-version.md).</span><span class="sxs-lookup"><span data-stu-id="af0d9-132">For more information, see [choosing the right .NET Core version](choose-net-core-version.md).</span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="af0d9-133">Destinatarios de esta guía</span><span class="sxs-lookup"><span data-stu-id="af0d9-133">Who should use this guide</span></span>

<span data-ttu-id="af0d9-134">Esta guía está dirigida a desarrolladores, jefes de desarrollo y arquitectos que estén interesados en migrar sus aplicaciones existentes escritas para ASP.NET MVC y Web API (.NET Framework 4.x) a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="af0d9-134">This guide's audience is developers, development leads, and architects who are interested in migrating their existing apps written for ASP.NET MVC and Web API (.NET Framework 4.x) to .NET Core.</span></span> <span data-ttu-id="af0d9-135">Los desarrolladores de ASP.NET Web Forms se beneficiarán de esta guía, pero también deberían leer el libro electrónico [Blazor para desarrolladores de ASP.NET Web Forms](https://docs.microsoft.com/dotnet/architecture/blazor-for-web-forms-developers/).</span><span class="sxs-lookup"><span data-stu-id="af0d9-135">ASP.NET Web Forms developers will benefit from this guide but should also read the [Blazor for ASP.NET Web Forms Developers](https://docs.microsoft.com/dotnet/architecture/blazor-for-web-forms-developers/) e-book.</span></span>

<span data-ttu-id="af0d9-136">Un público secundario es el de los responsables de la toma de decisiones técnicas que planean cuándo migrar sus aplicaciones a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="af0d9-136">A secondary audience is technical decision-makers planning when to move their apps to .NET Core.</span></span>

<span data-ttu-id="af0d9-137">El público objetivo de este libro son los desarrolladores de .NET con grandes aplicaciones existentes que se ejecutan en ASP.NET MVC y Web API.</span><span class="sxs-lookup"><span data-stu-id="af0d9-137">The target audience for this book is .NET developers with large, existing apps that run on ASP.NET MVC and Web API.</span></span> <span data-ttu-id="af0d9-138">Las aplicaciones basadas en ASP.NET Web Forms quedan fuera del ámbito central de este libro, aunque gran parte de la información que compara .NET Framework y .NET Core puede seguir siendo pertinente.</span><span class="sxs-lookup"><span data-stu-id="af0d9-138">Apps built on ASP.NET Web Forms are outside of the focus of this book, though much of the information comparing .NET Framework and .NET Core may still be relevant.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="af0d9-139">Cómo leer esta guía</span><span class="sxs-lookup"><span data-stu-id="af0d9-139">How you can use this guide</span></span>

<span data-ttu-id="af0d9-140">Puede leer este libro de corrido, como esperamos que hagan muchos lectores.</span><span class="sxs-lookup"><span data-stu-id="af0d9-140">You can read this book straight through, as we expect many readers to do.</span></span> <span data-ttu-id="af0d9-141">Este libro le proporcionará, en primer lugar, consideraciones sobre si debe migrar su aplicación.</span><span class="sxs-lookup"><span data-stu-id="af0d9-141">This book will provide you first with considerations for whether you should port your app at all.</span></span> <span data-ttu-id="af0d9-142">A ese contenido le siguen las diferencias arquitectónicas entre .NET Framework y .NET Core.</span><span class="sxs-lookup"><span data-stu-id="af0d9-142">That content is followed by architectural differences between .NET Framework and .NET Core.</span></span> <span data-ttu-id="af0d9-143">A partir de ahí, aprenderá estrategias para migrar una solución de gran tamaño en el tiempo y para trasladar una aplicación real.</span><span class="sxs-lookup"><span data-stu-id="af0d9-143">From there, you'll learn strategies for migrating a large solution over time and how to port a real app.</span></span> <span data-ttu-id="af0d9-144">Después, el libro incluye escenarios de implementación que solucionan la necesidad de ejecutar aplicaciones diferentes al tiempo que aparecen como una sola aplicación para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="af0d9-144">Next, the book includes deployment scenarios that address the need to run different apps while appearing as a single app to users.</span></span> <span data-ttu-id="af0d9-145">El libro concluye con dos casos prácticos en los que se describen aplicaciones reales que se han migrado de ASP.NET MVC a ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="af0d9-145">The book concludes with two case studies describing real apps that have migrated from ASP.NET MVC to ASP.NET Core.</span></span>

<span data-ttu-id="af0d9-146">Tanto si decide empezar por el primer capítulo como si no, puede consultar cualquiera de estos capítulos para obtener información sobre conceptos específicos:</span><span class="sxs-lookup"><span data-stu-id="af0d9-146">Whether or not you choose to start from the first chapter, you can reference any of these chapters to learn about specific concepts:</span></span>

- [<span data-ttu-id="af0d9-147">Diferencias arquitectónicas</span><span class="sxs-lookup"><span data-stu-id="af0d9-147">Architectural differences</span></span>](architectural-differences.md)
- [<span data-ttu-id="af0d9-148">Migración de soluciones de gran tamaño</span><span class="sxs-lookup"><span data-stu-id="af0d9-148">Migrate large solutions</span></span>](migrate-large-solutions.md)
- [<span data-ttu-id="af0d9-149">Migración de ejemplo</span><span class="sxs-lookup"><span data-stu-id="af0d9-149">Sample migration</span></span>](example-migration-eshop.md)
- [<span data-ttu-id="af0d9-150">Escenarios de implementación</span><span class="sxs-lookup"><span data-stu-id="af0d9-150">Deployment scenarios</span></span>](deployment-scenarios.md)

<span data-ttu-id="af0d9-151">Esta guía está disponible en [formato PDF](https://aka.ms/aspnet-porting-ebook) y en línea.</span><span class="sxs-lookup"><span data-stu-id="af0d9-151">This guide is available both in [PDF form](https://aka.ms/aspnet-porting-ebook) and online.</span></span> <span data-ttu-id="af0d9-152">No dude en reenviar este documento o los vínculos a la versión en línea a su equipo para garantizar que todos los integrantes hayan comprendido estos conceptos.</span><span class="sxs-lookup"><span data-stu-id="af0d9-152">Feel free to forward this document or links to its online version to your team to ensure a common understanding of these concepts.</span></span>

## <a name="send-your-feedback"></a><span data-ttu-id="af0d9-153">Envíe sus comentarios</span><span class="sxs-lookup"><span data-stu-id="af0d9-153">Send your feedback</span></span>

<span data-ttu-id="af0d9-154">Nos gustaría recibir sus comentarios al respecto para contribuir al desarrollo constante del libro y sus ejemplos relacionados.</span><span class="sxs-lookup"><span data-stu-id="af0d9-154">This book and related samples are constantly evolving, so your feedback is welcomed!</span></span> <span data-ttu-id="af0d9-155">Si tiene algún comentario sobre cómo mejorar este libro, escríbalo en la sección pertinente situada en la parte inferior de cualquier página creada en [Problemas de GitHub](https://github.com/dotnet/docs/issues).</span><span class="sxs-lookup"><span data-stu-id="af0d9-155">If you have comments about how this book can be improved, use the feedback section at the bottom of any page built on [GitHub issues](https://github.com/dotnet/docs/issues).</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="af0d9-156">Siguiente</span><span class="sxs-lookup"><span data-stu-id="af0d9-156">Next</span></span>](introduction.md)
