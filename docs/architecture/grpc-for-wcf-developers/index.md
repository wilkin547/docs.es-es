---
title: 'gRPC de ASP.NET Core para desarrolladores de WCF: gRPC para desarrolladores de WCF'
description: Introducción a la creación de servicios gRPC en ASP.NET Core 3.0 para desarrolladores de WCF
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: b89f5974dd18e7005c6479c5b9eead039364e654
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738076"
---
# <a name="aspnet-core-grpc-for-wcf-developers"></a><span data-ttu-id="5463a-103">gRPC de ASP.NET Core para desarrolladores de WCF</span><span class="sxs-lookup"><span data-stu-id="5463a-103">ASP.NET Core gRPC for WCF Developers</span></span>

![imagen de portada](./media/cover.png)

<span data-ttu-id="5463a-105">PUBLICADO POR</span><span class="sxs-lookup"><span data-stu-id="5463a-105">PUBLISHED BY</span></span>

<span data-ttu-id="5463a-106">Equipos de producto de la División de desarrolladores de Microsoft, .NET y Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5463a-106">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="5463a-107">División de Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="5463a-107">A division of Microsoft Corporation</span></span>

<span data-ttu-id="5463a-108">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="5463a-108">One Microsoft Way</span></span>

<span data-ttu-id="5463a-109">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="5463a-109">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="5463a-110">Copyright © 2019 de Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="5463a-110">Copyright © 2019 by Microsoft Corporation</span></span>

<span data-ttu-id="5463a-111">Todos los derechos reservados.</span><span class="sxs-lookup"><span data-stu-id="5463a-111">All rights reserved.</span></span> <span data-ttu-id="5463a-112">No se puede reproducir ni transmitir de ninguna forma ni por ningún medio ninguna parte del contenido de este libro sin la autorización por escrito del publicador.</span><span class="sxs-lookup"><span data-stu-id="5463a-112">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="5463a-113">Este libro se proporciona “tal cual” y expresa las opiniones del autor.</span><span class="sxs-lookup"><span data-stu-id="5463a-113">This book is provided “as-is” and expresses the author’s views and opinions.</span></span> <span data-ttu-id="5463a-114">Las opiniones y la información expresados en este libro, incluidas las direcciones URL y otras referencias a sitios web de Internet, pueden cambiar sin previo aviso.</span><span class="sxs-lookup"><span data-stu-id="5463a-114">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="5463a-115">Algunos ejemplos descritos aquí se proporcionan únicamente con fines ilustrativos y son ficticios.</span><span class="sxs-lookup"><span data-stu-id="5463a-115">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="5463a-116">No debe deducirse ninguna asociación ni conexión reales.</span><span class="sxs-lookup"><span data-stu-id="5463a-116">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="5463a-117">Microsoft y las marcas comerciales indicadas en https://www.microsoft.com en la página web "Marcas comerciales" pertenecen al grupo de empresas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5463a-117">Microsoft and the trademarks listed at https://www.microsoft.com on the “Trademarks” webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="5463a-118">El logotipo de la ballena de Docker es una marca registrada de Docker, Inc. Se usa con permiso.</span><span class="sxs-lookup"><span data-stu-id="5463a-118">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="5463a-119">El resto de marcas y logotipos pertenece a sus respectivos propietarios.</span><span class="sxs-lookup"><span data-stu-id="5463a-119">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="5463a-120">Autor:</span><span class="sxs-lookup"><span data-stu-id="5463a-120">Author:</span></span>

> <span data-ttu-id="5463a-121">**Mark Rendle**, director técnico, [recodificación visual](https://visualrecode.com)</span><span class="sxs-lookup"><span data-stu-id="5463a-121">**Mark Rendle** - Chief Technical Officer - [Visual Recode](https://visualrecode.com)</span></span>
>
> <span data-ttu-id="5463a-122">**Miranda Steiner**, autora técnica</span><span class="sxs-lookup"><span data-stu-id="5463a-122">**Miranda Steiner** - Technical Author</span></span>

<span data-ttu-id="5463a-123">Editores:</span><span class="sxs-lookup"><span data-stu-id="5463a-123">Editors:</span></span>

> <span data-ttu-id="5463a-124">**Maira Wenzel**, desarrolladora de contenidos sénior, Microsoft</span><span class="sxs-lookup"><span data-stu-id="5463a-124">**Maira Wenzel** - Sr Content Developer - Microsoft</span></span>

## <a name="introduction"></a><span data-ttu-id="5463a-125">Introducción</span><span class="sxs-lookup"><span data-stu-id="5463a-125">Introduction</span></span>

<span data-ttu-id="5463a-126">gRPC es una plataforma de trabajo moderna para compilar servicios en red y aplicaciones distribuidas.</span><span class="sxs-lookup"><span data-stu-id="5463a-126">gRPC is a modern framework for building networked services and distributed applications.</span></span> <span data-ttu-id="5463a-127">Imagínese el rendimiento de los enlaces de NetTCP de WCF con la interoperabilidad multiplataforma de SOAP.</span><span class="sxs-lookup"><span data-stu-id="5463a-127">Imagine the performance of WCF's NetTCP bindings with the cross-platform interoperability of SOAP.</span></span> <span data-ttu-id="5463a-128">gRPC se basa en HTTP/2 y el protocolo de codificación de mensajes Protobuf para proporcionar una comunicación de alto rendimiento y bajo ancho de banda entre aplicaciones y servicios.</span><span class="sxs-lookup"><span data-stu-id="5463a-128">gRPC builds on HTTP/2 and the Protobuf message-encoding protocol to provide high performance, low-bandwidth communication between applications and services.</span></span> <span data-ttu-id="5463a-129">Admite la generación de código de cliente y servidor en las plataformas y los lenguajes de programación más populares, como .NET, Java, Python, Node.js, Go, C++ y muchos más.</span><span class="sxs-lookup"><span data-stu-id="5463a-129">It supports server and client code generation across most popular programming languages and platforms, including .NET, Java, Python, Node.js, Go, C++ and more.</span></span> <span data-ttu-id="5463a-130">Con la compatibilidad de primera clase con gRPC en ASP.NET Core 3.0, junto con las herramientas y las bibliotecas de gRPC existentes para .NET 4.x, creemos que es una alternativa excelente a WCF para los equipos de desarrollo que quieran adoptar .NET Core en sus organizaciones.</span><span class="sxs-lookup"><span data-stu-id="5463a-130">With the first-class support for gRPC in ASP.NET Core 3.0, alongside the existing gRPC tools and libraries for .NET 4.x, we think it is an excellent alternative to WCF for development teams looking to adopt .NET Core in their organizations.</span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="5463a-131">Destinatarios de esta guía</span><span class="sxs-lookup"><span data-stu-id="5463a-131">Who should use this guide</span></span>

<span data-ttu-id="5463a-132">Esta guía se ha escrito para desarrolladores que trabajan con .NET Framework o .NET Core, que han usado WCF antes y que buscan migrar sus aplicaciones a un entorno de RPC moderno para .NET Core 3.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="5463a-132">This guide was written for developers working in .NET Framework or .NET Core who have previously used WCF and who are seeking to migrate their applications to a modern RPC environment for .NET Core 3.0 and later versions.</span></span> <span data-ttu-id="5463a-133">La guía también puede ser de uso más general para desarrolladores que vayan a realizar la actualización a .NET Core 3.0 (o piensen hacerlo) y que quieran usar las herramientas de gRPC integradas.</span><span class="sxs-lookup"><span data-stu-id="5463a-133">The guide may also be of use more generally for developers upgrading or considering upgrading to .NET Core 3.0 who want to use the built-in gRPC tools.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="5463a-134">Cómo leer esta guía</span><span class="sxs-lookup"><span data-stu-id="5463a-134">How you can use this guide</span></span>

<span data-ttu-id="5463a-135">Esta es una breve introducción a la creación de servicios de gRPC en ASP.NET Core 3.0 en la que se hace referencia a WCF como plataforma análoga.</span><span class="sxs-lookup"><span data-stu-id="5463a-135">This is a short introduction to building gRPC Services in ASP.NET Core 3.0 with particular reference to WCF as an analogous platform.</span></span> <span data-ttu-id="5463a-136">Se explican los principios de gRPC, relacionando cada concepto con las características equivalentes de WCF, y se ofrecen instrucciones para migrar una aplicación WCF actual a gRPC.</span><span class="sxs-lookup"><span data-stu-id="5463a-136">It explains the principles of gRPC, relating each concept to the equivalent features of WCF, and offers guidance for migrating an existing WCF application to gRPC.</span></span> <span data-ttu-id="5463a-137">También es útil para los desarrolladores que tienen experiencia en WCF y quieren aprender a crear nuevos servicios con gRPC.</span><span class="sxs-lookup"><span data-stu-id="5463a-137">It is also useful for developers who have experience of WCF and are looking to learn gRPC to build new services.</span></span> <span data-ttu-id="5463a-138">Las aplicaciones de ejemplo se pueden usar como una plantilla o como referencia para proyectos propios, y el código del libro o sus ejemplos también se puede copiar y reutilizar.</span><span class="sxs-lookup"><span data-stu-id="5463a-138">The sample applications can be used as a template or reference for your own projects, and you are free to copy and reuse code from the book or its samples.</span></span>

<span data-ttu-id="5463a-139">No dude en reenviar esta guía a su equipo para ayudarlo a garantizar una comprensión común de estas consideraciones y oportunidades.</span><span class="sxs-lookup"><span data-stu-id="5463a-139">Feel free to forward this guide to your team to help ensure a common understanding of these considerations and opportunities.</span></span> <span data-ttu-id="5463a-140">El hecho de que todos los usuarios trabajen a partir de un conjunto común de principios subyacentes y terminología permite garantizar una aplicación coherente de las prácticas y los patrones de diseño.</span><span class="sxs-lookup"><span data-stu-id="5463a-140">Having everybody working from a common set of terminology and underlying principles helps ensure consistent application of architectural patterns and practices.</span></span>

## <a name="references"></a><span data-ttu-id="5463a-141">Referencias</span><span class="sxs-lookup"><span data-stu-id="5463a-141">References</span></span>

- <span data-ttu-id="5463a-142">**Sitio web de gRPC**</span><span class="sxs-lookup"><span data-stu-id="5463a-142">**gRPC web site**</span></span>  
  <https://grpc.io>
- <span data-ttu-id="5463a-143">**Selección entre .NET Core y .NET Framework para aplicaciones de servidor**</span><span class="sxs-lookup"><span data-stu-id="5463a-143">**Choosing between .NET Core and .NET Framework for server apps**</span></span>  
  <https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server>

>[!div class="step-by-step"]
>[<span data-ttu-id="5463a-144">Siguiente</span><span class="sxs-lookup"><span data-stu-id="5463a-144">Next</span></span>](introduction.md)
