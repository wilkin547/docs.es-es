---
title: 'gRPC de ASP.NET Core para desarrolladores de WCF: gRPC para desarrolladores de WCF'
description: Introducción a la creación de servicios gRPC en ASP.NET Core 5.0 para desarrolladores de WCF
ms.date: 01/06/2021
ms.openlocfilehash: 26cce6bb784c08a5b59623ff5882fcf2fbb9e9ac
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970198"
---
# <a name="aspnet-core-grpc-for-wcf-developers"></a><span data-ttu-id="1d0ca-103">gRPC de ASP.NET Core para desarrolladores de WCF</span><span class="sxs-lookup"><span data-stu-id="1d0ca-103">ASP.NET Core gRPC for WCF Developers</span></span>

![imagen de portada](./media/cover.png)

<span data-ttu-id="1d0ca-105">EDICIÓN v1.0.1: actualizada a ASP.NET Core 5.0</span><span class="sxs-lookup"><span data-stu-id="1d0ca-105">EDITION v1.0.1 - Updated to ASP.NET Core 5.0</span></span>

<span data-ttu-id="1d0ca-106">Consulte el [registro de cambios](https://aka.ms/grpc-ebook-changelog) para ver las modificaciones del libro y las colaboraciones para la comunidad.</span><span class="sxs-lookup"><span data-stu-id="1d0ca-106">Refer [changelog](https://aka.ms/grpc-ebook-changelog) for the book updates and community contributions.</span></span>

<span data-ttu-id="1d0ca-107">PUBLICADO POR</span><span class="sxs-lookup"><span data-stu-id="1d0ca-107">PUBLISHED BY</span></span>

<span data-ttu-id="1d0ca-108">Equipos de producto de la División de desarrolladores de Microsoft, .NET y Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1d0ca-108">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="1d0ca-109">División de Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="1d0ca-109">A division of Microsoft Corporation</span></span>

<span data-ttu-id="1d0ca-110">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="1d0ca-110">One Microsoft Way</span></span>

<span data-ttu-id="1d0ca-111">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="1d0ca-111">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="1d0ca-112">Copyright © 2021 de Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="1d0ca-112">Copyright © 2021 by Microsoft Corporation</span></span>

<span data-ttu-id="1d0ca-113">Todos los derechos reservados.</span><span class="sxs-lookup"><span data-stu-id="1d0ca-113">All rights reserved.</span></span> <span data-ttu-id="1d0ca-114">No se puede reproducir ni transmitir de ninguna forma ni por ningún medio ninguna parte del contenido de este libro sin la autorización por escrito del publicador.</span><span class="sxs-lookup"><span data-stu-id="1d0ca-114">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="1d0ca-115">Este libro se proporciona “tal cual” y expresa las opiniones del autor.</span><span class="sxs-lookup"><span data-stu-id="1d0ca-115">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="1d0ca-116">Las opiniones y la información expresados en este libro, incluidas las direcciones URL y otras referencias a sitios web de Internet, pueden cambiar sin previo aviso.</span><span class="sxs-lookup"><span data-stu-id="1d0ca-116">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="1d0ca-117">Algunos ejemplos descritos aquí se proporcionan únicamente con fines ilustrativos y son ficticios.</span><span class="sxs-lookup"><span data-stu-id="1d0ca-117">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="1d0ca-118">No debe deducirse ninguna asociación ni conexión reales.</span><span class="sxs-lookup"><span data-stu-id="1d0ca-118">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="1d0ca-119">Microsoft y las marcas comerciales indicadas en <https://www.microsoft.com> en la página web "Marcas comerciales" pertenecen al grupo de empresas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1d0ca-119">Microsoft and the trademarks listed at <https://www.microsoft.com> on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="1d0ca-120">El logotipo de la ballena de Docker es una marca registrada de Docker, Inc. Se usa con permiso.</span><span class="sxs-lookup"><span data-stu-id="1d0ca-120">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="1d0ca-121">El resto de marcas y logotipos pertenece a sus respectivos propietarios.</span><span class="sxs-lookup"><span data-stu-id="1d0ca-121">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="1d0ca-122">Autores:</span><span class="sxs-lookup"><span data-stu-id="1d0ca-122">Authors:</span></span>

> <span data-ttu-id="1d0ca-123">**Mark Rendle**, director técnico, [recodificación visual](https://visualrecode.com)</span><span class="sxs-lookup"><span data-stu-id="1d0ca-123">**Mark Rendle** - Chief Technical Officer - [Visual Recode](https://visualrecode.com)</span></span>
>
> <span data-ttu-id="1d0ca-124">**Miranda Steiner**, autora técnica</span><span class="sxs-lookup"><span data-stu-id="1d0ca-124">**Miranda Steiner** - Technical Author</span></span>

<span data-ttu-id="1d0ca-125">Editor:</span><span class="sxs-lookup"><span data-stu-id="1d0ca-125">Editor:</span></span>

> <span data-ttu-id="1d0ca-126">**Maira Wenzel**, desarrolladora de contenidos sénior, Microsoft</span><span class="sxs-lookup"><span data-stu-id="1d0ca-126">**Maira Wenzel** - Sr. Content Developer - Microsoft</span></span>

## <a name="introduction"></a><span data-ttu-id="1d0ca-127">Introducción</span><span class="sxs-lookup"><span data-stu-id="1d0ca-127">Introduction</span></span>

<span data-ttu-id="1d0ca-128">gRPC es una plataforma de trabajo moderna para compilar servicios en red y aplicaciones distribuidas.</span><span class="sxs-lookup"><span data-stu-id="1d0ca-128">gRPC is a modern framework for building networked services and distributed applications.</span></span> <span data-ttu-id="1d0ca-129">Imagínese el rendimiento de los enlaces de NetTCP de Windows Communication Foundation (WCF), junto con la interoperabilidad multiplataforma de SOAP.</span><span class="sxs-lookup"><span data-stu-id="1d0ca-129">Imagine the performance of Windows Communication Foundation (WCF) NetTCP bindings, combined with the cross-platform interoperability of SOAP.</span></span> <span data-ttu-id="1d0ca-130">gRPC se basa en HTTP/2 y el protocolo de codificación de mensajes Protobuf para proporcionar una comunicación de alto rendimiento y bajo ancho de banda entre aplicaciones y servicios.</span><span class="sxs-lookup"><span data-stu-id="1d0ca-130">gRPC builds on HTTP/2 and the Protobuf message-encoding protocol to provide high performance, low-bandwidth communication between applications and services.</span></span> <span data-ttu-id="1d0ca-131">Admite la generación de código de cliente y servidor en las plataformas y los lenguajes de programación más populares, como .NET, Java, Python, Node.js, Go y C++.</span><span class="sxs-lookup"><span data-stu-id="1d0ca-131">It supports server and client code generation across most popular programming languages and platforms, including .NET, Java, Python, Node.js, Go, and C++.</span></span> <span data-ttu-id="1d0ca-132">Con la compatibilidad de primera clase con gRPC en ASP.NET Core 5.0, junto con las herramientas y las bibliotecas de gRPC existentes para .NET Framework 4.x, es una alternativa excelente a WCF para los equipos de desarrollo que quieran adoptar .NET en sus organizaciones.</span><span class="sxs-lookup"><span data-stu-id="1d0ca-132">With the first-class support for gRPC in ASP.NET Core 5.0, alongside the existing gRPC tools and libraries for .NET Framework 4.x, it's an excellent alternative to WCF for development teams looking to adopt .NET in their organizations.</span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="1d0ca-133">Destinatarios de esta guía</span><span class="sxs-lookup"><span data-stu-id="1d0ca-133">Who should use this guide</span></span>

<span data-ttu-id="1d0ca-134">Esta guía se ha escrito para desarrolladores que trabajan con .NET Framework o .NET, que han usado WCF antes y que buscan migrar sus aplicaciones a un entorno de RPC moderno para .NET Core 3.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="1d0ca-134">This guide was written for developers working in .NET Framework or .NET who have previously used WCF, and who are seeking to migrate their applications to a modern RPC environment for .NET Core 3.0 and later versions.</span></span> <span data-ttu-id="1d0ca-135">En general, si va a realizar una actualización a .NET 5, o si se lo está pensando, y quiere usar las herramientas de gRPC integradas, esta guía también le será útil.</span><span class="sxs-lookup"><span data-stu-id="1d0ca-135">More generally, if you are upgrading, or considering upgrading, to .NET 5, and you want to use the built-in gRPC tools, this guide is also useful.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="1d0ca-136">Cómo leer esta guía</span><span class="sxs-lookup"><span data-stu-id="1d0ca-136">How you can use this guide</span></span>

<span data-ttu-id="1d0ca-137">Esta es una breve introducción a la creación de servicios de gRPC en ASP.NET Core 5.0 en la que se hace referencia a WCF como plataforma análoga.</span><span class="sxs-lookup"><span data-stu-id="1d0ca-137">This is a short introduction to building gRPC Services in ASP.NET Core 5.0, with particular reference to WCF as an analogous platform.</span></span> <span data-ttu-id="1d0ca-138">Se explican los principios de gRPC, relacionando cada concepto con las características equivalentes de WCF, y se ofrecen instrucciones para migrar una aplicación WCF actual a gRPC.</span><span class="sxs-lookup"><span data-stu-id="1d0ca-138">It explains the principles of gRPC, relating each concept to the equivalent features of WCF, and offers guidance for migrating an existing WCF application to gRPC.</span></span> <span data-ttu-id="1d0ca-139">También es útil para los desarrolladores que tienen experiencia con WCF y quieren aprender a crear nuevos servicios con gRPC.</span><span class="sxs-lookup"><span data-stu-id="1d0ca-139">It's also useful for developers who have experience with WCF and are looking to learn gRPC to build new services.</span></span> <span data-ttu-id="1d0ca-140">Puede usar las aplicaciones de ejemplo como una plantilla o como referencia para proyectos propios, y el código del libro o sus ejemplos también se puede copiar y reutilizar.</span><span class="sxs-lookup"><span data-stu-id="1d0ca-140">You can use the sample applications as a template or reference for your own projects, and you are free to copy and reuse code from the book or its samples.</span></span>

<span data-ttu-id="1d0ca-141">No dude en reenviar esta guía a su equipo para ayudarlo a garantizar una comprensión común de estas consideraciones y oportunidades.</span><span class="sxs-lookup"><span data-stu-id="1d0ca-141">Feel free to forward this guide to your team to help ensure a common understanding of these considerations and opportunities.</span></span> <span data-ttu-id="1d0ca-142">El hecho de que todos los usuarios trabajen a partir de un conjunto común de principios subyacentes y de términos permite garantizar una aplicación coherente de las prácticas y los patrones de diseño.</span><span class="sxs-lookup"><span data-stu-id="1d0ca-142">Having everybody working from a common set of terms and underlying principles helps ensure consistent application of architectural patterns and practices.</span></span>

## <a name="references"></a><span data-ttu-id="1d0ca-143">Referencias</span><span class="sxs-lookup"><span data-stu-id="1d0ca-143">References</span></span>

- <span data-ttu-id="1d0ca-144">**Sitio web de gRPC**
  <https://grpc.io></span><span class="sxs-lookup"><span data-stu-id="1d0ca-144">**gRPC website**
<https://grpc.io></span></span>
- <span data-ttu-id="1d0ca-145">**Elección entre .NET 5 y .NET Framework para aplicaciones de servidor**
  <https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server></span><span class="sxs-lookup"><span data-stu-id="1d0ca-145">**Choosing between .NET 5 and .NET Framework for server apps**
<https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server></span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="1d0ca-146">Siguiente</span><span class="sxs-lookup"><span data-stu-id="1d0ca-146">Next</span></span>](introduction.md)
