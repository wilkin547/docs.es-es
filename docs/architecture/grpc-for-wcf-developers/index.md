---
title: 'gRPC de ASP.NET Core para desarrolladores de WCF: gRPC para desarrolladores de WCF'
description: PENDIENTE DE REDACTAR
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 6a5b4f6d0b47a272f7a753e22bfd61b06202944a
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2019
ms.locfileid: "72919373"
---
# <a name="aspnet-core-grpc-for-wcf-developers"></a><span data-ttu-id="303b9-103">gRPC de ASP.NET Core para desarrolladores de WCF</span><span class="sxs-lookup"><span data-stu-id="303b9-103">ASP.NET Core gRPC for WCF Developers</span></span>

![imagen de portada](./media/cover.png)

<span data-ttu-id="303b9-105">PUBLICADO POR</span><span class="sxs-lookup"><span data-stu-id="303b9-105">PUBLISHED BY</span></span>

<span data-ttu-id="303b9-106">Equipos de producto de la División de desarrolladores de Microsoft, .NET y Visual Studio</span><span class="sxs-lookup"><span data-stu-id="303b9-106">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="303b9-107">División de Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="303b9-107">A division of Microsoft Corporation</span></span>

<span data-ttu-id="303b9-108">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="303b9-108">One Microsoft Way</span></span>

<span data-ttu-id="303b9-109">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="303b9-109">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="303b9-110">Copyright © 2019 de Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="303b9-110">Copyright © 2019 by Microsoft Corporation</span></span>

<span data-ttu-id="303b9-111">Todos los derechos reservados.</span><span class="sxs-lookup"><span data-stu-id="303b9-111">All rights reserved.</span></span> <span data-ttu-id="303b9-112">No se puede reproducir ni transmitir de ninguna forma ni por ningún medio ninguna parte del contenido de este libro sin la autorización por escrito del publicador.</span><span class="sxs-lookup"><span data-stu-id="303b9-112">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="303b9-113">Este libro se proporciona “tal cual” y expresa las opiniones del autor.</span><span class="sxs-lookup"><span data-stu-id="303b9-113">This book is provided “as-is” and expresses the author’s views and opinions.</span></span> <span data-ttu-id="303b9-114">Las opiniones y la información expresados en este libro, incluidas las direcciones URL y otras referencias a sitios web de Internet, pueden cambiar sin previo aviso.</span><span class="sxs-lookup"><span data-stu-id="303b9-114">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="303b9-115">Algunos ejemplos descritos aquí se proporcionan únicamente con fines ilustrativos y son ficticios.</span><span class="sxs-lookup"><span data-stu-id="303b9-115">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="303b9-116">No debe deducirse ninguna asociación ni conexión reales.</span><span class="sxs-lookup"><span data-stu-id="303b9-116">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="303b9-117">Microsoft y las marcas comerciales indicadas en https://www.microsoft.com en la página web "Marcas comerciales" pertenecen al grupo de empresas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="303b9-117">Microsoft and the trademarks listed at https://www.microsoft.com on the “Trademarks” webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="303b9-118">El logotipo de la ballena de Docker es una marca registrada de Docker, Inc. Se usa con permiso.</span><span class="sxs-lookup"><span data-stu-id="303b9-118">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="303b9-119">El resto de marcas y logotipos pertenece a sus respectivos propietarios.</span><span class="sxs-lookup"><span data-stu-id="303b9-119">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="303b9-120">Autor:</span><span class="sxs-lookup"><span data-stu-id="303b9-120">Author:</span></span>

> <span data-ttu-id="303b9-121">**Mark Rendle**, director técnico, [recodificación visual](https://visualrecode.com)</span><span class="sxs-lookup"><span data-stu-id="303b9-121">**Mark Rendle** - Chief Technical Officer - [Visual Recode](https://visualrecode.com)</span></span>
>
> <span data-ttu-id="303b9-122">**Miranda Steiner**, autora técnica</span><span class="sxs-lookup"><span data-stu-id="303b9-122">**Miranda Steiner** - Technical Author</span></span>

<span data-ttu-id="303b9-123">Editores:</span><span class="sxs-lookup"><span data-stu-id="303b9-123">Editors:</span></span>

> <span data-ttu-id="303b9-124">**Maira Wenzel**, desarrolladora de contenidos sénior, Microsoft</span><span class="sxs-lookup"><span data-stu-id="303b9-124">**Maira Wenzel** - Sr Content Developer - Microsoft</span></span>

## <a name="introduction"></a><span data-ttu-id="303b9-125">Introducción</span><span class="sxs-lookup"><span data-stu-id="303b9-125">Introduction</span></span>

<span data-ttu-id="303b9-126">TODO</span><span class="sxs-lookup"><span data-stu-id="303b9-126">TODO</span></span>

## <a name="purpose"></a><span data-ttu-id="303b9-127">Propósito</span><span class="sxs-lookup"><span data-stu-id="303b9-127">Purpose</span></span>

<span data-ttu-id="303b9-128">TODO</span><span class="sxs-lookup"><span data-stu-id="303b9-128">TODO</span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="303b9-129">Destinatarios de esta guía</span><span class="sxs-lookup"><span data-stu-id="303b9-129">Who should use this guide</span></span>

<span data-ttu-id="303b9-130">**ACTUALIZAR ESTO**</span><span class="sxs-lookup"><span data-stu-id="303b9-130">**UPDATE THIS**</span></span>

<span data-ttu-id="303b9-131">Esta guía está dirigida a desarrolladores de WCF, responsables de desarrollo y arquitectos que estén interesados en migrar soluciones de WCF en .NET Framework 4 y versiones anteriores a ASP.NET Core 3.0 con servicios de gRPC.</span><span class="sxs-lookup"><span data-stu-id="303b9-131">The audience for this guide is WCF developers, development leads, and architects who are interested in migrating WCF solutions on .NET Framework 4 and earlier to ASP.NET Core 3.0 using gRPC services.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="303b9-132">Cómo leer esta guía</span><span class="sxs-lookup"><span data-stu-id="303b9-132">How you can use this guide</span></span>

<span data-ttu-id="303b9-133">**ACTUALIZAR ESTO**</span><span class="sxs-lookup"><span data-stu-id="303b9-133">**UPDATE THIS**</span></span>

<span data-ttu-id="303b9-134">Esta es una breve introducción a la creación de servicios de gRPC en ASP.NET Core 3.0 en la que se hace referencia a WCF como plataforma análoga.</span><span class="sxs-lookup"><span data-stu-id="303b9-134">This is a short introduction to building gRPC Services in ASP.NET Core 3.0 with particular reference to WCF as an analogous platform.</span></span> <span data-ttu-id="303b9-135">Se explican los principios de gRPC, relacionando cada concepto con las características equivalentes de WCF, y se ofrecen instrucciones para migrar una aplicación WCF actual a gRPC.</span><span class="sxs-lookup"><span data-stu-id="303b9-135">It explains the principles of gRPC, relating each concept to the equivalent features of WCF, and offers guidance for migrating an existing WCF application to gRPC.</span></span> <span data-ttu-id="303b9-136">También es útil para los desarrolladores que tienen experiencia en WCF y quieren aprender a crear nuevos servicios con gRPC.</span><span class="sxs-lookup"><span data-stu-id="303b9-136">It is also useful for developers who have experience of WCF and are looking to learn gRPC to build new services.</span></span> <span data-ttu-id="303b9-137">La aplicación de ejemplo se puede usar como una plantilla o como referencia para sus propios proyectos, y también se puede copiar y reutilizar el código del libro o sus ejemplos.</span><span class="sxs-lookup"><span data-stu-id="303b9-137">The sample application can be used as a template or reference for your own projects, and you are free to copy and reuse code from the book or its samples.</span></span>

<span data-ttu-id="303b9-138">No dude en reenviar esta guía a su equipo para ayudarlo a garantizar una comprensión común de estas consideraciones y oportunidades.</span><span class="sxs-lookup"><span data-stu-id="303b9-138">Feel free to forward this guide to your team to help ensure a common understanding of these considerations and opportunities.</span></span> <span data-ttu-id="303b9-139">El hecho de que todos los usuarios trabajen a partir de un conjunto común de principios subyacentes y terminología permite garantizar una aplicación coherente de las prácticas y los patrones de diseño.</span><span class="sxs-lookup"><span data-stu-id="303b9-139">Having everybody working from a common set of terminology and underlying principles helps ensure consistent application of architectural patterns and practices.</span></span>

## <a name="references"></a><span data-ttu-id="303b9-140">Referencias</span><span class="sxs-lookup"><span data-stu-id="303b9-140">References</span></span>

- <span data-ttu-id="303b9-141">**Sitio web de gRPC**</span><span class="sxs-lookup"><span data-stu-id="303b9-141">**gRPC web site**</span></span>  
  <https://grpc.io>
- <span data-ttu-id="303b9-142">**Selección entre .NET Core y .NET Framework para aplicaciones de servidor**</span><span class="sxs-lookup"><span data-stu-id="303b9-142">**Choosing between .NET Core and .NET Framework for server apps**</span></span>  
  <https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server>

>[!div class="step-by-step"]
>[<span data-ttu-id="303b9-143">Siguiente</span><span class="sxs-lookup"><span data-stu-id="303b9-143">Next</span></span>](introduction.md)
