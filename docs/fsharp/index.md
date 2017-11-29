---
title: "Guía de F#"
description: "Obtenga información sobre el lenguaje F # programación, un lenguaje de código abierto para .NET que proporciona compatibilidad de primera clase para la programación funcional."
keywords: .NET, .NET Core
author: jackfoxy
ms.author: phcart
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: ea27fb37-dad1-4bd4-a3cc-4f5c70767ae9
ms.openlocfilehash: 4ddd77cef6cf70a63f1af81359d82eda27a01593
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="f-guide"></a><span data-ttu-id="28a6f-104">Guía de F#</span><span class="sxs-lookup"><span data-stu-id="28a6f-104">F# Guide</span></span>

<span data-ttu-id="28a6f-105">F# es un lenguaje de programación multiplataforma y de código abierto para .NET que proporciona soporte de primera clase para la programación funcional, además de compatibilidad con la programación orientada a objetos e imperativa.</span><span class="sxs-lookup"><span data-stu-id="28a6f-105">F# is a cross-platform, open source programming language for .NET which provides first-class support for functional programming, along with support of object-oriented and imperative programming.</span></span>  <span data-ttu-id="28a6f-106">El compilador y las herramientas de Visual F# son la implementación y las herramientas de Microsoft para el lenguaje de programación F#, lo que lo convierte en un miembro de primera clase de .NET.</span><span class="sxs-lookup"><span data-stu-id="28a6f-106">The Visual F# compiler and tooling are Microsoft's implementation and tooling for the F# programming language, making F# a first-class member of .NET.</span></span>

## <a name="if-youre-new-to-f"></a><span data-ttu-id="28a6f-107">Si está familiarizado con F #</span><span class="sxs-lookup"><span data-stu-id="28a6f-107">If You're New to F#</span></span> #

<span data-ttu-id="28a6f-108">Si está familiarizado con F #, comenzar con la [paseo de F #](tour.md) para obtener una visión general del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="28a6f-108">If you're new to F#, begin with the [Tour of F#](tour.md) to get an overview of the language.</span></span>

<span data-ttu-id="28a6f-109">También se recomienda que pase por el [funciona como valores de primera clase](introduction-to-functional-programming/functions-as-first-class-values.md) <!--[Introduction to Functional Progamming](introduction-to-functional-programming/index.md)--> para obtener información sobre conceptos de programación funcional que son esenciales para trabajar con F #.</span><span class="sxs-lookup"><span data-stu-id="28a6f-109">It's also recommended that you go through the [Functions as First-Class Values](introduction-to-functional-programming/functions-as-first-class-values.md)<!--[Introduction to Functional Progamming](introduction-to-functional-programming/index.md)--> to learn Functional Programming concepts which are essential to working with F#.</span></span>

<span data-ttu-id="28a6f-110">La sección [Tutorials](tutorials/getting-started/index.md) (Tutoriales) también tiene guías paso a paso para los distintos niveles de dificultad y características del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="28a6f-110">The [Tutorials](tutorials/getting-started/index.md) also have step-by-step guides for various skill levels and features of the language.</span></span>

## <a name="if-youre-experienced-with-f"></a><span data-ttu-id="28a6f-111">Si tiene experiencia con F #</span><span class="sxs-lookup"><span data-stu-id="28a6f-111">If You're Experienced with F#</span></span> #

<span data-ttu-id="28a6f-112">Si sabe cómo usar F#, encontrará de gran utilidad la [Language Reference](language-reference/index.md) (Referencia del lenguaje), donde se documentan exhaustivamente todos los aspectos del lenguaje, junto con numerosos ejemplos de código.</span><span class="sxs-lookup"><span data-stu-id="28a6f-112">If you know your way around F#, you'll find a lot of use in the [Language Reference](language-reference/index.md), which documents each aspect of the language thoroughly, supplemented by numerous code samples.</span></span>  <span data-ttu-id="28a6f-113">También encontrará de gran utilidad la [F# Core Library Reference](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference) (Referencia de la biblioteca básica de F#).</span><span class="sxs-lookup"><span data-stu-id="28a6f-113">You'll also find a lot of use in the [F# Core Library Reference](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference).</span></span>  <span data-ttu-id="28a6f-114">La referencia de biblioteca básica de F # pasará finalmente fuera de MSDN y en estos documentos actuales.</span><span class="sxs-lookup"><span data-stu-id="28a6f-114">The F# Core Library Reference will eventually move away from MSDN and into these current docs.</span></span>

## <a name="the-f-software-foundation"></a><span data-ttu-id="28a6f-115">F# Software Foundation</span><span class="sxs-lookup"><span data-stu-id="28a6f-115">The F# Software Foundation</span></span>

<span data-ttu-id="28a6f-116">Aunque Microsoft es el desarrollador principal del lenguaje F# y las herramientas de Visual F#, F# también está respaldado por una fundación independiente, la F# Software Foundation (FSSF).</span><span class="sxs-lookup"><span data-stu-id="28a6f-116">Although Microsoft is the primary developer of the F# language and Visual F# Tooling, F# is also backed by an independent foundation, the F# Software Foundation (FSSF).</span></span>

<span data-ttu-id="28a6f-117">La misión de la F# Software Foundation es promover, proteger y hacer avanzar el lenguaje de programación F#, así como respaldar y facilitar el crecimiento de una comunidad internacional y diversa de programadores de F#.</span><span class="sxs-lookup"><span data-stu-id="28a6f-117">The mission of the F# Software Foundation is to promote, protect, and advance the F# programming language, and to support and facilitate the growth of a diverse and international community of F# programmers.</span></span>

<span data-ttu-id="28a6f-118">Para más información y participar, visite [fsharp.org](http://fsharp.org).</span><span class="sxs-lookup"><span data-stu-id="28a6f-118">To learn more and get involved, check out [fsharp.org](http://fsharp.org).</span></span>

## <a name="documentation"></a><span data-ttu-id="28a6f-119">Documentación</span><span class="sxs-lookup"><span data-stu-id="28a6f-119">Documentation</span></span>

* [<span data-ttu-id="28a6f-120">Tutoriales</span><span class="sxs-lookup"><span data-stu-id="28a6f-120">Tutorials</span></span>](tutorials/getting-started/index.md)
* <span data-ttu-id="28a6f-121">[Funciones como valores de primera clase](introduction-to-functional-programming/functions-as-first-class-values.md)<!--[Introduction to Functional Programming](introduction-to-functional-programming/index.md)--></span><span class="sxs-lookup"><span data-stu-id="28a6f-121">[Functions as First-Class Values](introduction-to-functional-programming/functions-as-first-class-values.md)<!--[Introduction to Functional Programming](introduction-to-functional-programming/index.md)--></span></span>
* [<span data-ttu-id="28a6f-122">Referencia del lenguaje</span><span class="sxs-lookup"><span data-stu-id="28a6f-122">Language Reference</span></span>](language-reference/index.md)
* <span data-ttu-id="28a6f-123">[F# Core Library Reference](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference) (Referencia de la biblioteca básica de F#)</span><span class="sxs-lookup"><span data-stu-id="28a6f-123">[F# Core Library Reference](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference)</span></span>

## <a name="online-reading-resources"></a><span data-ttu-id="28a6f-124">Recursos de lectura en línea</span><span class="sxs-lookup"><span data-stu-id="28a6f-124">Online Reading Resources</span></span>

* <span data-ttu-id="28a6f-125">[F# for Fun and Profit Gitbook](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/) (Gitbook de F# para divertirse y negocios)</span><span class="sxs-lookup"><span data-stu-id="28a6f-125">[F# for Fun and Profit Gitbook](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/)</span></span> 
* <span data-ttu-id="28a6f-126">[F# Programming Wikibook](https://en.wikibooks.org/wiki/F_Sharp_Programming) (Wikibook de programación en F#)</span><span class="sxs-lookup"><span data-stu-id="28a6f-126">[F# Programming Wikibook](https://en.wikibooks.org/wiki/F_Sharp_Programming)</span></span>

## <a name="video-learning-resources"></a><span data-ttu-id="28a6f-127">Recursos de aprendizaje en vídeo</span><span class="sxs-lookup"><span data-stu-id="28a6f-127">Video Learning Resources</span></span>

* [<span data-ttu-id="28a6f-128">Serie de introducción a la programación con F# en YouTube</span><span class="sxs-lookup"><span data-stu-id="28a6f-128">Introduction to Programming with F# series on YouTube</span></span>](https://www.youtube.com/watch?v=Teak30_pXHk&list=PLEoMzSkcN8oNiJ67Hd7oRGgD1d4YBxYGC)
* [<span data-ttu-id="28a6f-129">Serie de introducción a F# en FSharpTV</span><span class="sxs-lookup"><span data-stu-id="28a6f-129">Introduction to F# series on FSharpTV</span></span>](https://fsharp.tv/courses/fsharp-programming-intro/)

## <a name="further-resources"></a><span data-ttu-id="28a6f-130">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="28a6f-130">Further Resources</span></span>

* [<span data-ttu-id="28a6f-131">Recursos de aprendizaje de F# en fsharp.org</span><span class="sxs-lookup"><span data-stu-id="28a6f-131">F# Learning Resources on fsharp.org</span></span>](http://fsharp.org/learn.html)
* [<span data-ttu-id="28a6f-132">Sitio web de F# Snippets</span><span class="sxs-lookup"><span data-stu-id="28a6f-132">F# Snippets Website</span></span>](http://www.fssnip.net)
* [<span data-ttu-id="28a6f-133">F# Software Foundation</span><span class="sxs-lookup"><span data-stu-id="28a6f-133">F# Software Foundation</span></span>](http://fsharp.org)
