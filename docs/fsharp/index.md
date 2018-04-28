---
title: Guía de F#
description: 'Esta guía proporciona información general de los distintos materiales de aprendizaje en F #, un lenguaje de programación funcional que se ejecuta en. NET.'
author: jackfoxy
ms.author: phcart
ms.date: 03/19/2018
ms.topic: conceptual
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 9c03148d42f3cf8731580e36990aa21c68f705f6
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="f-guide"></a><span data-ttu-id="f41a8-103">Guía de F#</span><span class="sxs-lookup"><span data-stu-id="f41a8-103">F# Guide</span></span>

<span data-ttu-id="f41a8-104">F # es un lenguaje de programación funcional que se ejecuta en. NET.</span><span class="sxs-lookup"><span data-stu-id="f41a8-104">F# is a functional programming language that runs on .NET.</span></span> <span data-ttu-id="f41a8-105">También tiene compatibilidad completa para los objetos, permitiéndole blend funcional y programación de objeto práctico soluciones para cualquier problema.</span><span class="sxs-lookup"><span data-stu-id="f41a8-105">It also has full support for objects, letting you blend functional and object programming for pragmatic solutions to any problem.</span></span>

```fsharp
open System // Get access to functionality in System namespace.

// Function: takes a name and produces a greeting.
let getGreeting name =
    sprintf "Hello, %s! Isn't F# great?" name

// Use the EntryPoint attribute to run the program.
[<EntryPoint>]
let main args =
    // Define a list of names
    let names = [| "Don"; "Julia"; "Xi" |]
    
    // Print a fun greeting for each name!
    names
    |> Array.map getGreeting
    |> Array.iter (fun greeting -> printfn "%s" greeting)

    0
```

<span data-ttu-id="f41a8-106">F # es sobre la productividad en su centro.</span><span class="sxs-lookup"><span data-stu-id="f41a8-106">F# is about productivity at its heart.</span></span> <span data-ttu-id="f41a8-107">La compatibilidad con herramientas de F # es ubicuo y completa de características avanzadas.</span><span class="sxs-lookup"><span data-stu-id="f41a8-107">The tooling support for F# is ubiquitous and full of advanced features.</span></span>

## <a name="learning-f"></a><span data-ttu-id="f41a8-108">Aprendizaje de F #</span><span class="sxs-lookup"><span data-stu-id="f41a8-108">Learning F#</span></span> #

<span data-ttu-id="f41a8-109">[Paseo de F #](tour.md) ofrezca una visión general de las características del idioma principal con una gran cantidad de ejemplos de código.</span><span class="sxs-lookup"><span data-stu-id="f41a8-109">[Tour of F#](tour.md) gives an overview of major language features with lots of code samples.</span></span> <span data-ttu-id="f41a8-110">Esto se recomienda si está familiarizado con F # y desea tener una idea de cómo funciona el lenguaje.</span><span class="sxs-lookup"><span data-stu-id="f41a8-110">This is recommended if you are new to F# and want to get a feel for how the language works.</span></span>

<span data-ttu-id="f41a8-111">[Empezar a trabajar con F # en Visual Studio](get-started/get-started-visual-studio.md) si está en Windows y desea que la experiencia completa del IDE de Visual Studio (entorno de desarrollo de Integraded).</span><span class="sxs-lookup"><span data-stu-id="f41a8-111">[Get started with F# in Visual Studio](get-started/get-started-visual-studio.md) if you're on Windows and want the full Visual Studio IDE (Integraded Development Environment) experience.</span></span>

<span data-ttu-id="f41a8-112">[Empezar a trabajar con F # en Visual Studio para Mac](get-started/get-started-with-visual-studio-for-mac.md) si está en macOS y desea usar un IDE de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f41a8-112">[Get started with F# in Visual Studio for Mac](get-started/get-started-with-visual-studio-for-mac.md) if you're on macOS and want to use a Visual Studio IDE.</span></span>

<span data-ttu-id="f41a8-113">[Empezar a trabajar con F # en Visual Studio Code](get-started/get-started-vscode.md) si desea una ligera, multiplataforma y experiencia de IDE lleno de características.</span><span class="sxs-lookup"><span data-stu-id="f41a8-113">[Get Started with F# in Visual Studio Code](get-started/get-started-vscode.md) if you want a lightweight, cross-platform, and feature-packed IDE experience.</span></span>

<span data-ttu-id="f41a8-114">[Empezar a trabajar con F # con la CLI de núcleo de .NET](get-started/get-started-command-line.md) si desea utilizar las herramientas de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="f41a8-114">[Get started with F# with the .NET Core CLI](get-started/get-started-command-line.md) if you want to use command-line tools.</span></span>

<span data-ttu-id="f41a8-115">[Empezar a trabajar con F # y Xamarin](https://docs.microsoft.com/xamarin/cross-platform/platform/fsharp/) para móvil programar con F #.</span><span class="sxs-lookup"><span data-stu-id="f41a8-115">[Get started with F# and Xamarin](https://docs.microsoft.com/xamarin/cross-platform/platform/fsharp/) for mobile programming with F#.</span></span>

## <a name="references"></a><span data-ttu-id="f41a8-116">Referencias</span><span class="sxs-lookup"><span data-stu-id="f41a8-116">References</span></span>

<span data-ttu-id="f41a8-117">[Referencia del lenguaje F #](language-reference/index.md) es la referencia completa, oficial para todas las características del lenguaje F #.</span><span class="sxs-lookup"><span data-stu-id="f41a8-117">[F# Language Reference](language-reference/index.md) is the official, comprehensive reference for all F# language features.</span></span> <span data-ttu-id="f41a8-118">Cada artículo explica la sintaxis y ejemplos de código muestra.</span><span class="sxs-lookup"><span data-stu-id="f41a8-118">Each article explains the syntax and shows code samples.</span></span> <span data-ttu-id="f41a8-119">También puede utilizar la barra de filtro en la tabla de contenido para buscar artículos específicos.</span><span class="sxs-lookup"><span data-stu-id="f41a8-119">You can use the filter bar in the table of contents to find specific articles.</span></span>

<span data-ttu-id="f41a8-120">[Referencia de biblioteca básica de F #](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference) es la referencia de API para la biblioteca básica de F #.</span><span class="sxs-lookup"><span data-stu-id="f41a8-120">[F# Core Library Reference](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference) is the API reference for the F# Core Library.</span></span>


## <a name="additional-guides"></a><span data-ttu-id="f41a8-121">Guías adicionales</span><span class="sxs-lookup"><span data-stu-id="f41a8-121">Additional guides</span></span>

<span data-ttu-id="f41a8-122">[F # para diversión y ganancias](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/) es un libro muy detallado y completa sobre aprendizaje F #.</span><span class="sxs-lookup"><span data-stu-id="f41a8-122">[F# for Fun and Profit](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/) is a comprehensive and very detailed book on learning F#.</span></span> <span data-ttu-id="f41a8-123">El contenido y el autor son amadas por la Comunidad de F #.</span><span class="sxs-lookup"><span data-stu-id="f41a8-123">Its contents and author are beloved by the F# community.</span></span> <span data-ttu-id="f41a8-124">La audiencia de destino es principalmente los programadores con un fondo de programación orientada a objetos.</span><span class="sxs-lookup"><span data-stu-id="f41a8-124">The target audience is primarily developers with an object oriented programming background.</span></span>

<span data-ttu-id="f41a8-125">[Wikibook de programación de F #](https://en.wikibooks.org/wiki/F_Sharp_Programming) es un wikibook acerca de cómo aprender F #.</span><span class="sxs-lookup"><span data-stu-id="f41a8-125">[F# Programming Wikibook](https://en.wikibooks.org/wiki/F_Sharp_Programming) is a wikibook about learning F#.</span></span> <span data-ttu-id="f41a8-126">También es un producto de la Comunidad de F #.</span><span class="sxs-lookup"><span data-stu-id="f41a8-126">It is also a product of the F# community.</span></span> <span data-ttu-id="f41a8-127">Está dirigida a personas que son nuevos en F #, con un poco de conocimientos de programación orientada a objetos.</span><span class="sxs-lookup"><span data-stu-id="f41a8-127">The target audience is people who are new to F#, with a little bit of object oriented programming background.</span></span>

## <a name="learn-f-through-videos"></a><span data-ttu-id="f41a8-128">Obtenga información acerca de F # a través de vídeos</span><span class="sxs-lookup"><span data-stu-id="f41a8-128">Learn F# through videos</span></span>

<span data-ttu-id="f41a8-129">[Tutorial de F # en YouTube](https://www.youtube.com/watch?v=c7eNDJN758U) es una buena introducción a F # mediante Visual Studio, que muestra una gran cantidad de buenos ejemplos a lo largo de 1,5 horas.</span><span class="sxs-lookup"><span data-stu-id="f41a8-129">[F# tutorial on YouTube](https://www.youtube.com/watch?v=c7eNDJN758U) is a great introduction to F# using Visual Studio, showing lots of great examples over the course of 1.5 hours.</span></span> <span data-ttu-id="f41a8-130">Está dirigida a los desarrolladores de Visual Studio que están familiarizados con F #.</span><span class="sxs-lookup"><span data-stu-id="f41a8-130">The target audience is Visual Studio developers who are new to F#.</span></span>

<span data-ttu-id="f41a8-131">[Introducción a la programación con F #](https://www.youtube.com/watch?v=Teak30_pXHk&list=PLEoMzSkcN8oNiJ67Hd7oRGgD1d4YBxYGC) es una serie de vídeos excelente que usa código de Visual Studio como el editor principal.</span><span class="sxs-lookup"><span data-stu-id="f41a8-131">[Introduction to Programming with F#](https://www.youtube.com/watch?v=Teak30_pXHk&list=PLEoMzSkcN8oNiJ67Hd7oRGgD1d4YBxYGC) is a great video series that uses Visual Studio Code as the main editor.</span></span> <span data-ttu-id="f41a8-132">La serie de vídeos de nada se inicia y finaliza con la creación de un juego de vídeo RPG basado en texto.</span><span class="sxs-lookup"><span data-stu-id="f41a8-132">The video series starts from nothing and ends with building a text-based RPG video game.</span></span> <span data-ttu-id="f41a8-133">Está dirigida a los programadores que prefieren código de Visual Studio (o un IDE ligera) y son nuevos en F #.</span><span class="sxs-lookup"><span data-stu-id="f41a8-133">The target audience is developers who prefer Visual Studio Code (or a lightweight IDE) and are new to F#.</span></span>

<span data-ttu-id="f41a8-134">[Novedades de Visual Studio de 2017 para F # para los desarrolladores](https://www.linkedin.com/learning/what-s-new-in-visual-studio-2017-for-f-sharp-for-developers) es un curso de vídeo que muestra algunas de las nuevas características de F # en Visual Studio de 2017.</span><span class="sxs-lookup"><span data-stu-id="f41a8-134">[What's New in Visual Studio 2017 for F# For Developers](https://www.linkedin.com/learning/what-s-new-in-visual-studio-2017-for-f-sharp-for-developers) is a video course that shows some of the newer features for F# in Visual Studio 2017.</span></span> <span data-ttu-id="f41a8-135">Está dirigida a los desarrolladores de Visual Studio que están familiarizados con F #.</span><span class="sxs-lookup"><span data-stu-id="f41a8-135">The target audience is Visual Studio developers who are new to F#.</span></span>

## <a name="other-useful-resources"></a><span data-ttu-id="f41a8-136">Otros recursos útiles</span><span class="sxs-lookup"><span data-stu-id="f41a8-136">Other useful resources</span></span>

<span data-ttu-id="f41a8-137">El [sitio Web de fragmentos de código de F #](http://www.fssnip.net) contiene un conjunto de fragmentos de código que muestra cómo llevar a cabo prácticamente cualquier cosa en F #, comprendido entre principiantes y fragmentos de código muy avanzadas masivo.</span><span class="sxs-lookup"><span data-stu-id="f41a8-137">The [F# Snippets Website](http://www.fssnip.net) contains a massive set of code snippets showing how to do just about anything in F#, ranging from absolute beginner to highly advanced snippets.</span></span>

<span data-ttu-id="f41a8-138">El [F # Software Foundation demora](http://fsharp.org/guides/slack/) es un buen lugar para principiantes y expertos similares, es muy activos y tiene algunos mejor F # los programadores del mundo disponibles para una conversación.</span><span class="sxs-lookup"><span data-stu-id="f41a8-138">The [F# Software Foundation Slack](http://fsharp.org/guides/slack/) is a great place for beginners and experts alike, is highly active, and has some of world's best F# programmers available for a chat.</span></span> <span data-ttu-id="f41a8-139">Se recomienda combinar.</span><span class="sxs-lookup"><span data-stu-id="f41a8-139">We highly recommend joining.</span></span>

## <a name="the-f-software-foundation"></a><span data-ttu-id="f41a8-140">F# Software Foundation</span><span class="sxs-lookup"><span data-stu-id="f41a8-140">The F# Software Foundation</span></span>

<span data-ttu-id="f41a8-141">Aunque Microsoft es el desarrollador principal de sus herramientas en Visual Studio y el lenguaje F #, F # también está respaldado por una Fundación independiente, la F # Software Foundation (FSSF).</span><span class="sxs-lookup"><span data-stu-id="f41a8-141">Although Microsoft is the primary developer of the F# language and its tools in Visual Studio, F# is also backed by an independent foundation, the F# Software Foundation (FSSF).</span></span>

<span data-ttu-id="f41a8-142">La misión de la F# Software Foundation es promover, proteger y hacer avanzar el lenguaje de programación F#, así como respaldar y facilitar el crecimiento de una comunidad internacional y diversa de programadores de F#.</span><span class="sxs-lookup"><span data-stu-id="f41a8-142">The mission of the F# Software Foundation is to promote, protect, and advance the F# programming language, and to support and facilitate the growth of a diverse and international community of F# programmers.</span></span>

<span data-ttu-id="f41a8-143">Para más información y participar, visite [fsharp.org](http://fsharp.org). Es gratuito unir, y la red de desarrolladores de F # en la base es algo que no desea que se pierda!</span><span class="sxs-lookup"><span data-stu-id="f41a8-143">To learn more and get involved, check out [fsharp.org](http://fsharp.org). It's free to join, and the network of F# developers in the foundation is something you don't want to miss out on!</span></span>
