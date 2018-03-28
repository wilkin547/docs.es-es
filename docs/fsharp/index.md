---
title: Guía de F#
description: 'Esta guía proporciona información general de los distintos materiales de aprendizaje en F #, un lenguaje de programación funcional que se ejecuta en. NET.'
author: jackfoxy
ms.author: phcart
ms.date: 03/19/2018
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: ea27fb37-dad1-4bd4-a3cc-4f5c70767ae9
ms.openlocfilehash: a101233f396368c0bc25937c49f77699cb9f8cf2
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="f-guide"></a>Guía de F#

F # es un lenguaje de programación funcional que se ejecuta en. NET. También tiene compatibilidad completa para los objetos, permitiéndole blend funcional y programación de objeto práctico soluciones para cualquier problema.

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

F # es sobre la productividad en su centro. La compatibilidad con herramientas de F # es ubicuo y completa de características avanzadas.

## <a name="learning-f"></a>Aprendizaje de F # #

[Paseo de F #](tour.md) ofrezca una visión general de las características del idioma principal con una gran cantidad de ejemplos de código. Esto se recomienda si está familiarizado con F # y desea tener una idea de cómo funciona el lenguaje.

[Empezar a trabajar con F # en Visual Studio](get-started/get-started-visual-studio.md) si está en Windows y desea que la experiencia completa del IDE de Visual Studio (entorno de desarrollo de Integraded).

[Empezar a trabajar con F # en Visual Studio para Mac](get-started/get-started-with-visual-studio-for-mac.md) si está en macOS y desea usar un IDE de Visual Studio.

[Empezar a trabajar con F # en Visual Studio Code](get-started/get-started-vscode.md) si desea una ligera, multiplataforma y experiencia de IDE lleno de características.

[Empezar a trabajar con F # con la CLI de núcleo de .NET](get-started/get-started-command-line.md) si desea utilizar las herramientas de línea de comandos.

[Empezar a trabajar con F # y Xamarin](https://docs.microsoft.com/xamarin/cross-platform/platform/fsharp/) para móvil programar con F #.

## <a name="references"></a>Referencias

[Referencia del lenguaje F #](language-reference/index.md) es la referencia completa, oficial para todas las características del lenguaje F #. Cada artículo explica la sintaxis y ejemplos de código muestra. También puede utilizar la barra de filtro en la tabla de contenido para buscar artículos específicos.

[Referencia de biblioteca básica de F #](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference) es la referencia de API para la biblioteca básica de F #.


## <a name="additional-guides"></a>Guías adicionales

[F # para diversión y ganancias](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/) es un libro muy detallado y completa sobre aprendizaje F #. El contenido y el autor son amadas por la Comunidad de F #. La audiencia de destino es principalmente los programadores con un fondo de programación orientada a objetos.

[Wikibook de programación de F #](https://en.wikibooks.org/wiki/F_Sharp_Programming) es un wikibook acerca de cómo aprender F #. También es un producto de la Comunidad de F #. Está dirigida a personas que son nuevos en F #, con un poco de conocimientos de programación orientada a objetos.

## <a name="learn-f-through-videos"></a>Obtenga información acerca de F # a través de vídeos

[Tutorial de F # en YouTube](https://www.youtube.com/watch?v=c7eNDJN758U) es una buena introducción a F # mediante Visual Studio, que muestra una gran cantidad de buenos ejemplos a lo largo de 1,5 horas. Está dirigida a los desarrolladores de Visual Studio que están familiarizados con F #.

[Introducción a la programación con F #](https://www.youtube.com/watch?v=Teak30_pXHk&list=PLEoMzSkcN8oNiJ67Hd7oRGgD1d4YBxYGC) es una serie de vídeos excelente que usa código de Visual Studio como el editor principal. La serie de vídeos de nada se inicia y finaliza con la creación de un juego de vídeo RPG basado en texto. Está dirigida a los programadores que prefieren código de Visual Studio (o un IDE ligera) y son nuevos en F #.

[Novedades de Visual Studio de 2017 para F # para los desarrolladores](https://www.linkedin.com/learning/what-s-new-in-visual-studio-2017-for-f-sharp-for-developers) es un curso de vídeo que muestra algunas de las nuevas características de F # en Visual Studio de 2017. Está dirigida a los desarrolladores de Visual Studio que están familiarizados con F #.

## <a name="other-useful-resources"></a>Otros recursos útiles

El [sitio Web de fragmentos de código de F #](http://www.fssnip.net) contiene un conjunto de fragmentos de código que muestra cómo llevar a cabo prácticamente cualquier cosa en F #, comprendido entre principiantes y fragmentos de código muy avanzadas masivo.

El [F # Software Foundation demora](http://fsharp.org/guides/slack/) es un buen lugar para principiantes y expertos similares, es muy activos y tiene algunos mejor F # los programadores del mundo disponibles para una conversación. Se recomienda combinar.

## <a name="the-f-software-foundation"></a>F# Software Foundation

Aunque Microsoft es el desarrollador principal de sus herramientas en Visual Studio y el lenguaje F #, F # también está respaldado por una Fundación independiente, la F # Software Foundation (FSSF).

La misión de la F# Software Foundation es promover, proteger y hacer avanzar el lenguaje de programación F#, así como respaldar y facilitar el crecimiento de una comunidad internacional y diversa de programadores de F#.

Para más información y participar, visite [fsharp.org](http://fsharp.org). Es gratuito unir, y la red de desarrolladores de F # en la base es algo que no desea que se pierda!
