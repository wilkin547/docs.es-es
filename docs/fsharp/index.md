---
title: "Guía de F#"
description: "Obtenga información sobre F #, un lenguaje de programación funcional que se ejecuta en. NET."
keywords: .NET, .NET Core
author: jackfoxy
ms.author: phcart
ms.date: 12/01/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: ea27fb37-dad1-4bd4-a3cc-4f5c70767ae9
ms.openlocfilehash: 45f5d2ca794ccea7a35cf6c0bf9d58a3e6500453
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="f-guide"></a><span data-ttu-id="b173b-104">Guía de F#</span><span class="sxs-lookup"><span data-stu-id="b173b-104">F# Guide</span></span>

<span data-ttu-id="b173b-105">F # es un lenguaje de programación funcional que se ejecuta en. NET.</span><span class="sxs-lookup"><span data-stu-id="b173b-105">F# is a functional programming language which runs on .NET.</span></span>  <span data-ttu-id="b173b-106">Además de apoyo construcciones de programación funcional, también tiene capacidades de programación del objeto.</span><span class="sxs-lookup"><span data-stu-id="b173b-106">In addition to supporting functional programming constructs, it also has object programming capabilities.</span></span>  <span data-ttu-id="b173b-107">Hace que este híbrido de la programación funcional con capacidades orientadas a objetos de F # un lenguaje práctico para llevar a cabo cualquier tarea.</span><span class="sxs-lookup"><span data-stu-id="b173b-107">This hybrid of functional programming with object-oriented capabilities makes F# a pragmatic language for accomplishing any task.</span></span>

## <a name="if-youre-new-to-f"></a><span data-ttu-id="b173b-108">Si está familiarizado con F #</span><span class="sxs-lookup"><span data-stu-id="b173b-108">If You're New to F#</span></span> #

<span data-ttu-id="b173b-109">Si está familiarizado con F #, comenzar con la [paseo de F #](tour.md) para obtener información general sobre el lenguaje y algunos de sus conceptos de programación.</span><span class="sxs-lookup"><span data-stu-id="b173b-109">If you're new to F#, begin with the [Tour of F#](tour.md) to get an overview of the language and some of its programming concepts.</span></span>  <span data-ttu-id="b173b-110">Si está utilizando Visual Studio, la plantilla de proyecto de Tutorial contiene el mismo contenido.</span><span class="sxs-lookup"><span data-stu-id="b173b-110">If you're using Visual Studio, the Tutorial project template contains the same content.</span></span>

## <a name="if-youre-experienced-with-f"></a><span data-ttu-id="b173b-111">Si tiene experiencia con F #</span><span class="sxs-lookup"><span data-stu-id="b173b-111">If You're Experienced with F#</span></span> #

<span data-ttu-id="b173b-112">Si desea sabe más acerca de F #, u obtener más información sobre una construcción de lenguaje específico, consulte la [referencia del lenguaje](language-reference/index.md).</span><span class="sxs-lookup"><span data-stu-id="b173b-112">If you know your way around F#, or want to learn more about a specific language construct, see the [Language Reference](language-reference/index.md).</span></span>  <span data-ttu-id="b173b-113">Es una guía exhaustiva de todas las funcionalidades del lenguaje F #.</span><span class="sxs-lookup"><span data-stu-id="b173b-113">It's a thorough guide of all F# language capabilities.</span></span>

<span data-ttu-id="b173b-114">Además, el [referencia de biblioteca básica de F #](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference) es un excelente recurso para aprender sobre FSharp.Core, la biblioteca principal que forma parte de F #.</span><span class="sxs-lookup"><span data-stu-id="b173b-114">Additionally, the [F# Core Library Reference](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference) is a great resource for learning about FSharp.Core, the core library which is a part of F#.</span></span>

## <a name="the-f-software-foundation"></a><span data-ttu-id="b173b-115">F# Software Foundation</span><span class="sxs-lookup"><span data-stu-id="b173b-115">The F# Software Foundation</span></span>

<span data-ttu-id="b173b-116">Aunque Microsoft es el desarrollador principal del lenguaje F # y sus herramientas, F # también está respaldado por una Fundación independiente, la F # Software Foundation (FSSF).</span><span class="sxs-lookup"><span data-stu-id="b173b-116">Although Microsoft is the primary developer of the F# language and its tooling, F# is also backed by an independent foundation, the F# Software Foundation (FSSF).</span></span>

<span data-ttu-id="b173b-117">La misión de la F# Software Foundation es promover, proteger y hacer avanzar el lenguaje de programación F#, así como respaldar y facilitar el crecimiento de una comunidad internacional y diversa de programadores de F#.</span><span class="sxs-lookup"><span data-stu-id="b173b-117">The mission of the F# Software Foundation is to promote, protect, and advance the F# programming language, and to support and facilitate the growth of a diverse and international community of F# programmers.</span></span>

<span data-ttu-id="b173b-118">Para más información y participar, visite [fsharp.org](http://fsharp.org).</span><span class="sxs-lookup"><span data-stu-id="b173b-118">To learn more and get involved, check out [fsharp.org](http://fsharp.org).</span></span>

## <a name="documentation"></a><span data-ttu-id="b173b-119">Documentación</span><span class="sxs-lookup"><span data-stu-id="b173b-119">Documentation</span></span>

* [<span data-ttu-id="b173b-120">Tutoriales</span><span class="sxs-lookup"><span data-stu-id="b173b-120">Tutorials</span></span>](tutorials/getting-started/index.md)
* <span data-ttu-id="b173b-121">[Funciones como valores de primera clase](introduction-to-functional-programming/functions-as-first-class-values.md)<!--[Introduction to Functional Programming](introduction-to-functional-programming/index.md)--></span><span class="sxs-lookup"><span data-stu-id="b173b-121">[Functions as First-Class Values](introduction-to-functional-programming/functions-as-first-class-values.md)<!--[Introduction to Functional Programming](introduction-to-functional-programming/index.md)--></span></span>
* [<span data-ttu-id="b173b-122">Referencia del lenguaje</span><span class="sxs-lookup"><span data-stu-id="b173b-122">Language Reference</span></span>](language-reference/index.md)
* <span data-ttu-id="b173b-123">[F# Core Library Reference](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference) (Referencia de la biblioteca básica de F#)</span><span class="sxs-lookup"><span data-stu-id="b173b-123">[F# Core Library Reference](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference)</span></span>

## <a name="online-reading-resources"></a><span data-ttu-id="b173b-124">Recursos de lectura en línea</span><span class="sxs-lookup"><span data-stu-id="b173b-124">Online Reading Resources</span></span>

* <span data-ttu-id="b173b-125">[F# for Fun and Profit Gitbook](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/) (Gitbook de F# para divertirse y negocios)</span><span class="sxs-lookup"><span data-stu-id="b173b-125">[F# for Fun and Profit Gitbook](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/)</span></span> 
* <span data-ttu-id="b173b-126">[F# Programming Wikibook](https://en.wikibooks.org/wiki/F_Sharp_Programming) (Wikibook de programación en F#)</span><span class="sxs-lookup"><span data-stu-id="b173b-126">[F# Programming Wikibook](https://en.wikibooks.org/wiki/F_Sharp_Programming)</span></span>

## <a name="video-learning-resources"></a><span data-ttu-id="b173b-127">Recursos de aprendizaje en vídeo</span><span class="sxs-lookup"><span data-stu-id="b173b-127">Video Learning Resources</span></span>

* [<span data-ttu-id="b173b-128">Serie de introducción a la programación con F# en YouTube</span><span class="sxs-lookup"><span data-stu-id="b173b-128">Introduction to Programming with F# series on YouTube</span></span>](https://www.youtube.com/watch?v=Teak30_pXHk&list=PLEoMzSkcN8oNiJ67Hd7oRGgD1d4YBxYGC)
* [<span data-ttu-id="b173b-129">Serie de introducción a F# en FSharpTV</span><span class="sxs-lookup"><span data-stu-id="b173b-129">Introduction to F# series on FSharpTV</span></span>](https://fsharp.tv/courses/fsharp-programming-intro/)

## <a name="further-resources"></a><span data-ttu-id="b173b-130">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="b173b-130">Further Resources</span></span>

* [<span data-ttu-id="b173b-131">Recursos de aprendizaje de F# en fsharp.org</span><span class="sxs-lookup"><span data-stu-id="b173b-131">F# Learning Resources on fsharp.org</span></span>](http://fsharp.org/learn.html)
* [<span data-ttu-id="b173b-132">Sitio web de F# Snippets</span><span class="sxs-lookup"><span data-stu-id="b173b-132">F# Snippets Website</span></span>](http://www.fssnip.net)
* [<span data-ttu-id="b173b-133">F# Software Foundation</span><span class="sxs-lookup"><span data-stu-id="b173b-133">F# Software Foundation</span></span>](http://fsharp.org)