---
title: Modernización de aplicaciones de escritorio en Windows 10 con .NET Core 3.1
description: Información sobre cómo modernizar aplicaciones de escritorio con .NET Core 3.1
ms.date: 05/12/2020
ms.openlocfilehash: 5861f806a9158ef761c47bc23e51327d4e2d0480
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83422666"
---
# <a name="modernizing-desktop-apps-on-windows-10-with-net-core-31"></a><span data-ttu-id="5975a-103">Modernización de aplicaciones de escritorio en Windows 10 con .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="5975a-103">Modernizing Desktop Apps on Windows 10 with .NET Core 3.1</span></span>

![Captura de pantalla en la que se muestra la portada del libro electrónico de modernización de aplicaciones de escritorio.](./media/modernizing-existing-desktop-apps-ebook-cover.png)

<span data-ttu-id="5975a-105">PUBLICADO POR</span><span class="sxs-lookup"><span data-stu-id="5975a-105">PUBLISHED BY</span></span>

<span data-ttu-id="5975a-106">Equipos de producto de la División de desarrolladores de Microsoft, .NET y Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5975a-106">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="5975a-107">División de Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="5975a-107">A division of Microsoft Corporation</span></span>

<span data-ttu-id="5975a-108">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="5975a-108">One Microsoft Way</span></span>

<span data-ttu-id="5975a-109">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="5975a-109">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="5975a-110">Copyright © 2020 de Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="5975a-110">Copyright © 2020 by Microsoft Corporation</span></span>

<span data-ttu-id="5975a-111">Todos los derechos reservados.</span><span class="sxs-lookup"><span data-stu-id="5975a-111">All rights reserved.</span></span> <span data-ttu-id="5975a-112">No se puede reproducir ni transmitir de ninguna forma ni por ningún medio ninguna parte del contenido de este libro sin la autorización por escrito del publicador.</span><span class="sxs-lookup"><span data-stu-id="5975a-112">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="5975a-113">Este libro se proporciona “tal cual” y expresa las opiniones del autor.</span><span class="sxs-lookup"><span data-stu-id="5975a-113">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="5975a-114">Las opiniones y la información expresados en este libro, incluidas las direcciones URL y otras referencias a sitios web de Internet, pueden cambiar sin previo aviso.</span><span class="sxs-lookup"><span data-stu-id="5975a-114">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="5975a-115">Algunos ejemplos descritos aquí se proporcionan únicamente con fines ilustrativos y son ficticios.</span><span class="sxs-lookup"><span data-stu-id="5975a-115">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="5975a-116">No debe deducirse ninguna asociación ni conexión reales.</span><span class="sxs-lookup"><span data-stu-id="5975a-116">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="5975a-117">Microsoft y las marcas comerciales indicadas en <https://www.microsoft.com> en la página web "Marcas comerciales" pertenecen al grupo de empresas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5975a-117">Microsoft and the trademarks listed at <https://www.microsoft.com> on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="5975a-118">Mac y macOS son marcas comerciales de Apple Inc.</span><span class="sxs-lookup"><span data-stu-id="5975a-118">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="5975a-119">El resto de marcas y logotipos pertenece a sus respectivos propietarios.</span><span class="sxs-lookup"><span data-stu-id="5975a-119">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="5975a-120">Coautores:</span><span class="sxs-lookup"><span data-stu-id="5975a-120">Co-Authors:</span></span>

> <span data-ttu-id="5975a-121">**Olia Gavrysh**, directora de administración de programas, equipo de .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="5975a-121">**Olia Gavrysh**, Program Manager, .NET team, Microsoft</span></span>

> <span data-ttu-id="5975a-122">**Miguel Ángel Castejón Dominguez**, arquitecto de innovación, Kabel</span><span class="sxs-lookup"><span data-stu-id="5975a-122">**Miguel Angel Castejón Dominguez**, Innovation Architect, Kabel</span></span>

<span data-ttu-id="5975a-123">Participantes y revisores:</span><span class="sxs-lookup"><span data-stu-id="5975a-123">Participants and reviewers:</span></span>

> <span data-ttu-id="5975a-124">**Maira Wenzel**, administradora de programas sénior, equipo de .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="5975a-124">**Maira Wenzel**, Senior Program Manager, .NET team, Microsoft</span></span>

> <span data-ttu-id="5975a-125">**Andy De Gorge**, desarrollador de contenido sénior, equipo de documentación de .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="5975a-125">**Andy De Gorge**, Senior Content Developer, .NET docs team, Microsoft</span></span>

> <span data-ttu-id="5975a-126">**Miguel Ramos**, administrador de programas sénior, equipo de la plataforma de desarrolladores de Windows, Microsoft</span><span class="sxs-lookup"><span data-stu-id="5975a-126">**Miguel Ramos**, Senior Program Manager, Windows Developer Platform team, Microsoft</span></span>

> <span data-ttu-id="5975a-127">**Adam Braden**, administrador de programas principal, equipo de la plataforma de desarrolladores de Windows, Microsoft</span><span class="sxs-lookup"><span data-stu-id="5975a-127">**Adam Braden**, Principal Program Manager, Windows Developer Platform team, Microsoft</span></span>

> <span data-ttu-id="5975a-128">**Ricardo Minguez Pablos**, administrador de programas sénior, equipo de Azure IoT, Microsoft</span><span class="sxs-lookup"><span data-stu-id="5975a-128">**Ricardo Minguez Pablos**, Senior Program Manager, Azure IoT team, Microsoft</span></span>

> <span data-ttu-id="5975a-129">**Nish Anil**, director de administración de programas, equipo de .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="5975a-129">**Nish Anil**, Senior Program Manager, .NET team, Microsoft</span></span>

> <span data-ttu-id="5975a-130">**Beth Massi**, administradora sénior de marketing de producto, Microsoft</span><span class="sxs-lookup"><span data-stu-id="5975a-130">**Beth Massi**, Senior Product Marketing Manager, Microsoft</span></span>

> <span data-ttu-id="5975a-131">**Scott Hunter**, director asociado de administración de programas, equipo de .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="5975a-131">**Scott Hunter**, Partner Director Program Manager, .NET team, Microsoft</span></span>

> <span data-ttu-id="5975a-132">**Marta Fuentes Lara**, Kabel</span><span class="sxs-lookup"><span data-stu-id="5975a-132">**Marta Fuentes Lara**, Kabel</span></span>

> <span data-ttu-id="5975a-133">**Raúl Fernández de Córdoba**, Kabel</span><span class="sxs-lookup"><span data-stu-id="5975a-133">**Raúl Fernández de Córdoba**, Kabel</span></span>

> <span data-ttu-id="5975a-134">**Antonio Manuel Fernández Cantos**, Kabel</span><span class="sxs-lookup"><span data-stu-id="5975a-134">**Antonio Manuel Fernández Cantos**, Kabel</span></span>

## <a name="introduction"></a><span data-ttu-id="5975a-135">Introducción</span><span class="sxs-lookup"><span data-stu-id="5975a-135">Introduction</span></span>

<span data-ttu-id="5975a-136">Este libro trata sobre las estrategias que puede adoptar para llevar sus aplicaciones de escritorio a la modernización e incorporación de las características más recientes sobre runtime, idioma y plataformas.</span><span class="sxs-lookup"><span data-stu-id="5975a-136">This book is about strategies you can adopt to move your existing desktop applications through the path of modernization and incorporate the latest runtime, language, and platform features.</span></span> <span data-ttu-id="5975a-137">Descubrirá que no existe un único método, ya que cada aplicación es distinta, y también lo son sus requisitos y preferencias.</span><span class="sxs-lookup"><span data-stu-id="5975a-137">You'll discover that there's no unique recipe as each application is different, and so are your requirements and preferences.</span></span> <span data-ttu-id="5975a-138">Sin embargo, la buena noticia es que puede aplicar enfoques comunes para agregar nuevas características y funcionalidades a sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="5975a-138">The good news is that there are common approaches you can apply to add new features and capabilities to your applications.</span></span> <span data-ttu-id="5975a-139">Para algunos de estos enfoques no será necesario aplicar ninguna modificación importante al código.</span><span class="sxs-lookup"><span data-stu-id="5975a-139">Some of them won't even require major modifications of your code.</span></span> <span data-ttu-id="5975a-140">En este libro, explicaremos cómo funcionan todas esas características en segundo plano, así como la mecánica de sus implementaciones.</span><span class="sxs-lookup"><span data-stu-id="5975a-140">In this book, we'll reveal how all those features work behind the scenes and explain the mechanics of their implementations.</span></span> <span data-ttu-id="5975a-141">Además, encontrará algunos escenarios habituales para modernizar aplicaciones de escritorio explicados en detalle, así que seguro que tendrá la inspiración necesaria para hacer evolucionar sus proyectos.</span><span class="sxs-lookup"><span data-stu-id="5975a-141">Moreover, you'll find some common scenarios for modernizing existing desktop applications shown in detail so you can find inspiration for evolving your projects.</span></span>

<span data-ttu-id="5975a-142">El enfoque de Microsoft para modernizar las aplicaciones consiste en proporcionarle la flexibilidad necesaria para crear una ruta de acceso personalizada.</span><span class="sxs-lookup"><span data-stu-id="5975a-142">Microsoft's approach to modernizing existing applications is to give you the flexibility to create your own customized path.</span></span> <span data-ttu-id="5975a-143">Todas las estrategias de modernización descritas en este libro son mayoritariamente independientes.</span><span class="sxs-lookup"><span data-stu-id="5975a-143">All the modernization strategies described in this book are mostly independent.</span></span> <span data-ttu-id="5975a-144">Puede elegir las que sean pertinentes para su aplicación y omitir las que no considere importantes.</span><span class="sxs-lookup"><span data-stu-id="5975a-144">You can choose ones that are relevant for your application and skip others that aren't important for you.</span></span> <span data-ttu-id="5975a-145">Dicho de otra forma, puede combinar las estrategias para cubrir de la mejor forma las necesidades de sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="5975a-145">In other words, you can mix and match the strategies to best address your application needs.</span></span>

## <a name="who-should-use-the-book"></a><span data-ttu-id="5975a-146">Destinatarios de este libro</span><span class="sxs-lookup"><span data-stu-id="5975a-146">Who should use the book</span></span>

<span data-ttu-id="5975a-147">Este libro está destinado a los desarrolladores y arquitectos de soluciones que quieren modernizar las aplicaciones de escritorio existentes de Windows Forms y WPF para aprovechar las ventajas que ofrecen .NET Core y Windows 10.</span><span class="sxs-lookup"><span data-stu-id="5975a-147">We wrote this book for developers and solution architects who want to modernize existing Windows Forms and WPF desktop applications to leverage the benefits of .NET Core and Windows 10.</span></span>

<span data-ttu-id="5975a-148">También es posible que este libro le resulte útil si se dedica a tomar decisiones técnicas, por ejemplo, si es arquitecto empresarial o un director o responsable de desarrollo que quiere disponer de información general relacionada con las ventajas de actualizar las aplicaciones de escritorio.</span><span class="sxs-lookup"><span data-stu-id="5975a-148">You might also find this book useful if you're a technical decision maker, such as an enterprise architect or a development lead or director who wants an overview of the benefits of updating existing desktop applications.</span></span>

## <a name="how-to-use-the-book"></a><span data-ttu-id="5975a-149">Cómo usar este libro</span><span class="sxs-lookup"><span data-stu-id="5975a-149">How to use the book</span></span>

<span data-ttu-id="5975a-150">En este libro se aborda el motivo por el que es recomendable modernizar las aplicaciones existentes y, además, se explican las ventajas específicas derivadas del uso de .NET Core 3.1 y MSIX para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="5975a-150">This book addresses the "why"—why you might want to modernize your existing applications, and the specific benefits you get from using NET Core 3.1 and MSIX to modernize your desktop apps.</span></span> <span data-ttu-id="5975a-151">El contenido del libro está diseñado para arquitectos y responsables de la toma de decisiones técnicas que quieren obtener información general, pero que no tienen que centrarse en información detallada de carácter técnico ni de implementación.</span><span class="sxs-lookup"><span data-stu-id="5975a-151">The content of the book is designed for architects and technical decision makers who want an overview, but who don't need to focus on implementation and technical, step-by-step details.</span></span>

<span data-ttu-id="5975a-152">A lo largo de los distintos capítulos, se proporcionan fragmentos de códigos de implementación de ejemplo y capturas de pantalla. Además, el capítulo 5 se ha dedicado a mostrar el proceso de migración completo de unas aplicaciones de muestra.</span><span class="sxs-lookup"><span data-stu-id="5975a-152">Along the different chapters, sample implementation code snippets and screenshots are provided, with chapter 5 devoted to showcase a complete migration process for sample applications.</span></span>

## <a name="what-this-book-doesnt-cover"></a><span data-ttu-id="5975a-153">Aspectos no tratados en este libro</span><span class="sxs-lookup"><span data-stu-id="5975a-153">What this book doesn't cover</span></span>

<span data-ttu-id="5975a-154">Este libro trata sobre un subconjunto específico de escenarios centrados en la migración mediante lift-and-shift. En él, se describe la forma de conseguir las ventajas que ofrece la modernización sin necesidad de volver a escribir el código.</span><span class="sxs-lookup"><span data-stu-id="5975a-154">This book covers a specific subset of scenarios that are focused on lift-and-shift scenarios, outlining the way to gain the benefits of modernizing without the effort of rewriting code.</span></span>

<span data-ttu-id="5975a-155">Este libro no trata sobre el desarrollo desde cero de aplicaciones modernas con .NET ni sobre cómo empezar a usar Windows Forms y WPF, sino que</span><span class="sxs-lookup"><span data-stu-id="5975a-155">This book isn't about developing modern applications with .NET Core from scratch or about getting started with Windows Forms and WPF.</span></span> <span data-ttu-id="5975a-156">se centra en cómo actualizar las aplicaciones de escritorio con las características tecnológicas más recientes para el desarrollo de escritorio.</span><span class="sxs-lookup"><span data-stu-id="5975a-156">It focuses on how you can update existing desktop applications with the latest technologies for desktop development.</span></span>

## <a name="samples-used-in-this-book"></a><span data-ttu-id="5975a-157">Ejemplos usados en este libro</span><span class="sxs-lookup"><span data-stu-id="5975a-157">Samples used in this book</span></span>

<span data-ttu-id="5975a-158">Para indicar los pasos necesarios para realizar una modernización, usaremos una aplicación de ejemplo llamada `eShopModernizing`.</span><span class="sxs-lookup"><span data-stu-id="5975a-158">To highlight the necessary steps to perform a modernization, we'll be using a sample application called `eShopModernizing`.</span></span> <span data-ttu-id="5975a-159">Esta aplicación tiene dos tipos, Windows Forms y WPF, y nosotros explicaremos un proceso detallado sobre cómo llevar a cabo la modernización de los dos en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5975a-159">This application has two flavors, Windows Forms and WPF, and we'll show a step-by-step process on how to perform the modernization on both of them to .NET Core.</span></span>

<span data-ttu-id="5975a-160">Además, en el repositorio de GitHub de este libro, encontrará los resultados del proceso, que puede consultar si decide seguir el tutorial paso a paso.</span><span class="sxs-lookup"><span data-stu-id="5975a-160">Also, on the GitHub repository for this book, you'll find the results of the process, which you can consult with if you decide to follow the step-by-step tutorial.</span></span>

## <a name="send-your-feedback"></a><span data-ttu-id="5975a-161">Envíe sus comentarios</span><span class="sxs-lookup"><span data-stu-id="5975a-161">Send your feedback</span></span>

<span data-ttu-id="5975a-162">Nos gustaría recibir sus comentarios al respecto para contribuir al desarrollo constante del libro y sus ejemplos relacionados.</span><span class="sxs-lookup"><span data-stu-id="5975a-162">This book and related samples are constantly evolving, so your feedback is welcomed!</span></span> <span data-ttu-id="5975a-163">Si tiene algún comentario sobre cómo mejorar este libro, escríbalo en la sección pertinente situada en la parte inferior de cualquier página creada en [Problemas de GitHub](https://github.com/dotnet/docs/issues).</span><span class="sxs-lookup"><span data-stu-id="5975a-163">If you have comments about how this book can be improved, use the feedback section at the bottom of any page built on [GitHub issues](https://github.com/dotnet/docs/issues).</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="5975a-164">Siguiente</span><span class="sxs-lookup"><span data-stu-id="5975a-164">Next</span></span>](why-modern-applications.md)
