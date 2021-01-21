---
title: Modernización de aplicaciones de escritorio en Windows 10 con .NET 5
description: Información sobre cómo modernizar aplicaciones de escritorio con .NET 5
ms.date: 01/06/2021
ms.openlocfilehash: de8a451b0598b5eabd99028d377c161dace61623
ms.sourcegitcommit: 632818f4b527e5bf3c48fc04e0c7f3b4bdb8a248
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/20/2021
ms.locfileid: "98615714"
---
# <a name="modernizing-desktop-apps-on-windows-10-with-net-5"></a><span data-ttu-id="434cf-103">Modernización de aplicaciones de escritorio en Windows 10 con .NET 5</span><span class="sxs-lookup"><span data-stu-id="434cf-103">Modernizing Desktop Apps on Windows 10 with .NET 5</span></span>

![Captura de pantalla en la que se muestra la portada del libro electrónico de modernización de aplicaciones de escritorio.](./media/modernizing-existing-desktop-apps-ebook-cover.png)

<span data-ttu-id="434cf-105">**EDICIÓN v1.0.1**: actualizada a .NET 5</span><span class="sxs-lookup"><span data-stu-id="434cf-105">**EDITION v1.0.1** - Updated to .NET 5</span></span>

<span data-ttu-id="434cf-106">Consulte el [registro de cambios](https://aka.ms/desktop-ebook-changelog) para ver las modificaciones del libro y las colaboraciones para la comunidad.</span><span class="sxs-lookup"><span data-stu-id="434cf-106">Refer [changelog](https://aka.ms/desktop-ebook-changelog) for the book updates and community contributions.</span></span>

<span data-ttu-id="434cf-107">PUBLICADO POR</span><span class="sxs-lookup"><span data-stu-id="434cf-107">PUBLISHED BY</span></span>

<span data-ttu-id="434cf-108">Equipos de producto de la División de desarrolladores de Microsoft, .NET y Visual Studio</span><span class="sxs-lookup"><span data-stu-id="434cf-108">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="434cf-109">División de Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="434cf-109">A division of Microsoft Corporation</span></span>

<span data-ttu-id="434cf-110">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="434cf-110">One Microsoft Way</span></span>

<span data-ttu-id="434cf-111">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="434cf-111">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="434cf-112">Copyright © 2021 de Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="434cf-112">Copyright © 2021 by Microsoft Corporation</span></span>

<span data-ttu-id="434cf-113">Todos los derechos reservados.</span><span class="sxs-lookup"><span data-stu-id="434cf-113">All rights reserved.</span></span> <span data-ttu-id="434cf-114">No se puede reproducir ni transmitir de ninguna forma ni por ningún medio ninguna parte del contenido de este libro sin la autorización por escrito del publicador.</span><span class="sxs-lookup"><span data-stu-id="434cf-114">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="434cf-115">Este libro se proporciona “tal cual” y expresa las opiniones del autor.</span><span class="sxs-lookup"><span data-stu-id="434cf-115">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="434cf-116">Las opiniones y la información expresados en este libro, incluidas las direcciones URL y otras referencias a sitios web de Internet, pueden cambiar sin previo aviso.</span><span class="sxs-lookup"><span data-stu-id="434cf-116">The views, opinions, and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="434cf-117">Algunos ejemplos descritos aquí se proporcionan únicamente con fines ilustrativos y son ficticios.</span><span class="sxs-lookup"><span data-stu-id="434cf-117">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="434cf-118">No debe deducirse ninguna asociación ni conexión reales.</span><span class="sxs-lookup"><span data-stu-id="434cf-118">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="434cf-119">Microsoft y las marcas comerciales indicadas en <https://www.microsoft.com> en la página web "Marcas comerciales" pertenecen al grupo de empresas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="434cf-119">Microsoft and the trademarks listed at <https://www.microsoft.com> on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="434cf-120">Mac y macOS son marcas comerciales de Apple Inc.</span><span class="sxs-lookup"><span data-stu-id="434cf-120">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="434cf-121">El resto de marcas y logotipos pertenece a sus respectivos propietarios.</span><span class="sxs-lookup"><span data-stu-id="434cf-121">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="434cf-122">Coautores:</span><span class="sxs-lookup"><span data-stu-id="434cf-122">Co-Authors:</span></span>

> <span data-ttu-id="434cf-123">**Olia Gavrysh**, directora de administración de programas, equipo de .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="434cf-123">**Olia Gavrysh**, Program Manager, .NET team, Microsoft</span></span>

> <span data-ttu-id="434cf-124">**Miguel Ángel Castejón Dominguez**, arquitecto de innovación, Kabel</span><span class="sxs-lookup"><span data-stu-id="434cf-124">**Miguel Angel Castejón Dominguez**, Innovation Architect, Kabel</span></span>

<span data-ttu-id="434cf-125">Participantes y revisores:</span><span class="sxs-lookup"><span data-stu-id="434cf-125">Participants and reviewers:</span></span>

> <span data-ttu-id="434cf-126">**Maira Wenzel**, administradora de programas sénior, equipo de .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="434cf-126">**Maira Wenzel**, Senior Program Manager, .NET team, Microsoft</span></span>

> <span data-ttu-id="434cf-127">**Andy De Gorge**, desarrollador de contenido sénior, equipo de documentación de .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="434cf-127">**Andy De Gorge**, Senior Content Developer, .NET docs team, Microsoft</span></span>

> <span data-ttu-id="434cf-128">**Miguel Ramos**, administrador de programas sénior, equipo de la plataforma de desarrolladores de Windows, Microsoft</span><span class="sxs-lookup"><span data-stu-id="434cf-128">**Miguel Ramos**, Senior Program Manager, Windows Developer Platform team, Microsoft</span></span>

> <span data-ttu-id="434cf-129">**Adam Braden**, administrador de programas principal, equipo de la plataforma de desarrolladores de Windows, Microsoft</span><span class="sxs-lookup"><span data-stu-id="434cf-129">**Adam Braden**, Principal Program Manager, Windows Developer Platform team, Microsoft</span></span>

> <span data-ttu-id="434cf-130">**Ricardo Minguez Pablos**, administrador de programas sénior, equipo de Azure IoT, Microsoft</span><span class="sxs-lookup"><span data-stu-id="434cf-130">**Ricardo Minguez Pablos**, Senior Program Manager, Azure IoT team, Microsoft</span></span>

> <span data-ttu-id="434cf-131">**Nish Anil**, director de administración de programas, equipo de .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="434cf-131">**Nish Anil**, Senior Program Manager, .NET team, Microsoft</span></span>

> <span data-ttu-id="434cf-132">**Beth Massi**, administradora sénior de marketing de producto, Microsoft</span><span class="sxs-lookup"><span data-stu-id="434cf-132">**Beth Massi**, Senior Product Marketing Manager, Microsoft</span></span>

> <span data-ttu-id="434cf-133">**Scott Hunter**, director asociado de administración de programas, equipo de .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="434cf-133">**Scott Hunter**, Partner Director Program Manager, .NET team, Microsoft</span></span>

> <span data-ttu-id="434cf-134">**Marta Fuentes Lara**, Kabel</span><span class="sxs-lookup"><span data-stu-id="434cf-134">**Marta Fuentes Lara**, Kabel</span></span>

> <span data-ttu-id="434cf-135">**Raúl Fernández de Córdoba**, Kabel</span><span class="sxs-lookup"><span data-stu-id="434cf-135">**Raúl Fernández de Córdoba**, Kabel</span></span>

> <span data-ttu-id="434cf-136">**Antonio Manuel Fernández Cantos**, Kabel</span><span class="sxs-lookup"><span data-stu-id="434cf-136">**Antonio Manuel Fernández Cantos**, Kabel</span></span>

## <a name="introduction"></a><span data-ttu-id="434cf-137">Introducción</span><span class="sxs-lookup"><span data-stu-id="434cf-137">Introduction</span></span>

<span data-ttu-id="434cf-138">Este libro trata sobre las estrategias que puede adoptar para llevar sus aplicaciones de escritorio a la modernización e incorporación de las características más recientes sobre runtime, idioma y plataformas.</span><span class="sxs-lookup"><span data-stu-id="434cf-138">This book is about strategies you can adopt to move your existing desktop applications through the path of modernization and incorporate the latest runtime, language, and platform features.</span></span> <span data-ttu-id="434cf-139">Descubrirá que no existe un único método, ya que cada aplicación es distinta, y también lo son sus requisitos y preferencias.</span><span class="sxs-lookup"><span data-stu-id="434cf-139">You'll discover that there's no unique recipe as each application is different, and so are your requirements and preferences.</span></span> <span data-ttu-id="434cf-140">Sin embargo, la buena noticia es que puede aplicar enfoques comunes para agregar nuevas características y funcionalidades a sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="434cf-140">The good news is that there are common approaches you can apply to add new features and capabilities to your applications.</span></span> <span data-ttu-id="434cf-141">Para algunos de estos enfoques no será necesario aplicar ninguna modificación importante al código.</span><span class="sxs-lookup"><span data-stu-id="434cf-141">Some of them won't even require major modifications of your code.</span></span> <span data-ttu-id="434cf-142">En este libro, explicaremos cómo funcionan todas esas características en segundo plano, así como la mecánica de sus implementaciones.</span><span class="sxs-lookup"><span data-stu-id="434cf-142">In this book, we'll reveal how all those features work behind the scenes and explain the mechanics of their implementations.</span></span> <span data-ttu-id="434cf-143">Además, encontrará algunos escenarios habituales para modernizar aplicaciones de escritorio explicados en detalle, así que seguro que tendrá la inspiración necesaria para hacer evolucionar sus proyectos.</span><span class="sxs-lookup"><span data-stu-id="434cf-143">Moreover, you'll find some common scenarios for modernizing existing desktop applications shown in detail so you can find inspiration for evolving your projects.</span></span>

<span data-ttu-id="434cf-144">El enfoque de Microsoft para modernizar las aplicaciones consiste en proporcionarle la flexibilidad necesaria para crear una ruta de acceso personalizada.</span><span class="sxs-lookup"><span data-stu-id="434cf-144">Microsoft's approach to modernizing existing applications is to give you the flexibility to create your own customized path.</span></span> <span data-ttu-id="434cf-145">Todas las estrategias de modernización descritas en este libro son mayoritariamente independientes.</span><span class="sxs-lookup"><span data-stu-id="434cf-145">All the modernization strategies described in this book are mostly independent.</span></span> <span data-ttu-id="434cf-146">Puede elegir las que sean pertinentes para su aplicación y omitir las que no considere importantes.</span><span class="sxs-lookup"><span data-stu-id="434cf-146">You can choose ones that are relevant for your application and skip others that aren't important for you.</span></span> <span data-ttu-id="434cf-147">Dicho de otra forma, puede combinar las estrategias para cubrir de la mejor forma las necesidades de sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="434cf-147">In other words, you can mix and match the strategies to best address your application needs.</span></span>

## <a name="who-should-use-the-book"></a><span data-ttu-id="434cf-148">Destinatarios de este libro</span><span class="sxs-lookup"><span data-stu-id="434cf-148">Who should use the book</span></span>

<span data-ttu-id="434cf-149">Libro para los desarrolladores y arquitectos de soluciones que quieren modernizar las aplicaciones de escritorio existentes de Windows Forms y WPF para aprovechar las ventajas que ofrecen .NET y Windows 10.</span><span class="sxs-lookup"><span data-stu-id="434cf-149">This book for developers and solution architects who want to modernize existing Windows Forms and WPF desktop applications to leverage the benefits of .NET and Windows 10.</span></span>

<span data-ttu-id="434cf-150">También es posible que este libro le resulte útil si se dedica a tomar decisiones técnicas, por ejemplo, si es arquitecto empresarial o un director o responsable de desarrollo que quiere disponer de información general relacionada con las ventajas de actualizar las aplicaciones de escritorio.</span><span class="sxs-lookup"><span data-stu-id="434cf-150">You might also find this book useful if you're a technical decision maker, such as an enterprise architect or a development lead or director who wants an overview of the benefits of updating existing desktop applications.</span></span>

## <a name="how-to-use-the-book"></a><span data-ttu-id="434cf-151">Cómo usar este libro</span><span class="sxs-lookup"><span data-stu-id="434cf-151">How to use the book</span></span>

<span data-ttu-id="434cf-152">En este libro se aborda el motivo por el que es recomendable modernizar las aplicaciones existentes y, además, se explican las ventajas específicas derivadas del uso de .NET y MSIX para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="434cf-152">This book addresses the "why"—why you might want to modernize your existing applications, and the specific benefits you get from using NET and MSIX to modernize your desktop apps.</span></span> <span data-ttu-id="434cf-153">El contenido del libro está diseñado para arquitectos y responsables de la toma de decisiones técnicas que quieren obtener información general, pero que no tienen que centrarse en información detallada de carácter técnico ni de implementación.</span><span class="sxs-lookup"><span data-stu-id="434cf-153">The content of the book is designed for architects and technical decision makers who want an overview, but who don't need to focus on implementation and technical, step-by-step details.</span></span>

<span data-ttu-id="434cf-154">A lo largo de los distintos capítulos, se proporcionan fragmentos de códigos de implementación de ejemplo y capturas de pantalla. Además, el capítulo 5 se ha dedicado a mostrar el proceso de migración completo de unas aplicaciones de muestra.</span><span class="sxs-lookup"><span data-stu-id="434cf-154">Along the different chapters, sample implementation code snippets and screenshots are provided, with chapter 5 devoted to showcase a complete migration process for sample applications.</span></span>

## <a name="what-this-book-doesnt-cover"></a><span data-ttu-id="434cf-155">Aspectos no tratados en este libro</span><span class="sxs-lookup"><span data-stu-id="434cf-155">What this book doesn't cover</span></span>

<span data-ttu-id="434cf-156">Este libro trata sobre un subconjunto específico de escenarios centrados en la migración mediante lift-and-shift. En él, se describe la forma de conseguir las ventajas que ofrece la modernización sin necesidad de volver a escribir el código.</span><span class="sxs-lookup"><span data-stu-id="434cf-156">This book covers a specific subset of scenarios that are focused on lift-and-shift scenarios, outlining the way to gain the benefits of modernizing without the effort of rewriting code.</span></span>

<span data-ttu-id="434cf-157">Este libro no trata sobre el desarrollo desde cero de aplicaciones modernas con .NET ni sobre cómo empezar a usar Windows Forms y WPF, sino que</span><span class="sxs-lookup"><span data-stu-id="434cf-157">This book isn't about developing modern applications with .NET from scratch or about getting started with Windows Forms and WPF.</span></span> <span data-ttu-id="434cf-158">se centra en cómo actualizar las aplicaciones de escritorio con las características tecnológicas más recientes para el desarrollo de escritorio.</span><span class="sxs-lookup"><span data-stu-id="434cf-158">It focuses on how you can update existing desktop applications with the latest technologies for desktop development.</span></span>

## <a name="samples-used-in-this-book"></a><span data-ttu-id="434cf-159">Ejemplos usados en este libro</span><span class="sxs-lookup"><span data-stu-id="434cf-159">Samples used in this book</span></span>

<span data-ttu-id="434cf-160">Para indicar los pasos necesarios para realizar una modernización, usaremos una aplicación de ejemplo llamada `eShopModernizing`.</span><span class="sxs-lookup"><span data-stu-id="434cf-160">To highlight the necessary steps to perform a modernization, we'll be using a sample application called `eShopModernizing`.</span></span> <span data-ttu-id="434cf-161">Esta aplicación tiene dos tipos, Windows Forms y WPF, y nosotros explicaremos un proceso detallado sobre cómo llevar a cabo la modernización de los dos en .NET.</span><span class="sxs-lookup"><span data-stu-id="434cf-161">This application has two flavors, Windows Forms and WPF, and we'll show a step-by-step process on how to perform the modernization on both of them to .NET.</span></span>

<span data-ttu-id="434cf-162">Además, en el repositorio de GitHub de este libro, encontrará los resultados del proceso, que puede consultar si decide seguir el tutorial paso a paso.</span><span class="sxs-lookup"><span data-stu-id="434cf-162">Also, on the GitHub repository for this book, you'll find the results of the process, which you can consult with if you decide to follow the step-by-step tutorial.</span></span>

## <a name="send-your-feedback"></a><span data-ttu-id="434cf-163">Envíe sus comentarios</span><span class="sxs-lookup"><span data-stu-id="434cf-163">Send your feedback</span></span>

<span data-ttu-id="434cf-164">Nos gustaría recibir sus comentarios al respecto para contribuir al desarrollo constante del libro y sus ejemplos relacionados.</span><span class="sxs-lookup"><span data-stu-id="434cf-164">This book and related samples are constantly evolving, so your feedback is welcomed!</span></span> <span data-ttu-id="434cf-165">Si tiene algún comentario sobre cómo mejorar este libro, escríbalo en la sección pertinente situada en la parte inferior de cualquier página creada en [Problemas de GitHub](https://github.com/dotnet/docs/issues).</span><span class="sxs-lookup"><span data-stu-id="434cf-165">If you have comments about how this book can be improved, use the feedback section at the bottom of any page built on [GitHub issues](https://github.com/dotnet/docs/issues).</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="434cf-166">Siguiente</span><span class="sxs-lookup"><span data-stu-id="434cf-166">Next</span></span>](why-modern-applications.md)
