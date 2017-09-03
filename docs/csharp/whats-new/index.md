---
title: "Novedades de C# - Guía de C#"
description: "Cómo evoluciona el lenguaje C#"
keywords: "C#, Características más recientes, Novedades, Roslyn"
author: BillWagner
ms.author: wiwagn
ms.date: 03/21/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 77deec51-a14d-46d4-9bb3-faf449477149
ms.translationtype: HT
ms.sourcegitcommit: df0438dd742db802bb0f935d840006236d5d9bf9
ms.openlocfilehash: 0a328f62a02aea223340fcc00e839e841041a7d6
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---

# <a name="whats-new-in-c"></a>Novedades de C# #

En esta página se brinda una guía básica de las características nueva de cada versión importante del lenguaje C#. Los vínculos a continuación proporcionan información detallada sobre las características principales que se agregaron en cada versión.

> [!IMPORTANT]
> El lenguaje C# se basa en tipos y métodos de una *biblioteca estándar* para algunas de las características. Un ejemplo es el procesamiento de excepciones. Cada expresión o instrucción `throw` se comprueba para asegurarse de que el objeto que se genera deriva de @System.Exception. Del mismo modo, cada `catch` se comprueba para asegurarse de que el tipo que se captura deriva de @System.Exception. Cada versión puede agregar requisitos nuevos. Para usar las características más recientes del lenguaje en entornos anteriores, es posible que tenga que instalar bibliotecas específicas. Estas están documentadas en la página de cada versión específica. Puede obtener más información sobre las [relaciones entre lenguaje y biblioteca](relationships-between-language-and-library.md) para tener más antecedentes sobre esta dependencia. 

* [C# 7.1](csharp-7-1.md):
    - En esta página se describen las características más recientes del lenguaje C#. En esta sección se trata C# 7.1, disponible actualmente en la [versión 15.3 de Visual Studio 2017](https://www.visualstudio.com/vs/whatsnew/) y el [SDK de .NET Core 2.0](../../core/whats-new/index.md).

* [C# 7](csharp-7.md):
    - En esta página se describen las características que se han agregado en C# 7. Esto es lo que se ha incorporado a [Visual Studio 2017](https://www.visualstudio.com/vs/whatsnew/) y [.NET Core 1.0](../../core/whats-new/index.md) o versiones posteriores.
     
* [C# 6](csharp-6.md):
    - En esta página se describen las características que se agregaron en C# 6. Estas características están disponibles en Visual Studio 2015 para desarrolladores de Windows y en .NET Core 1.0 para desarrolladores que exploran C# en macOS y Linux.

<!--* [C# Interactive](../interactive/index.md): 
    - This page describes C# Interactive, an interactive Read Eval Print Loop (REPL) that you can use to explore the C# language. You can use it to write code interactively and see it execute immediately, without any compile or build step.
-->
* [Compatibilidad multiplataforma](../../core/index.md):
    - C#, mediante la compatibilidad con .NET Core, se ejecuta en varias plataformas. Si está interesado en probar C# en macOS o en alguna de las muchas distribuciones de Linux compatibles, puede obtener más información sobre .NET Core.

<!--
- [.NET Compiler Platform SDK](../roslyn/index.md):
    - The .NET Compiler Platform SDK enables you to write code that performs static analysis on C# code. You can use these APIs to find potential errors, or bad practices, suggest fixes, and even implement those fixes.
-->
  
## <a name="previous-versions"></a>Versiones anteriores
A continuación se enumeran las características clave que se presentaron en versiones anteriores del lenguaje C# y Visual Studio .NET.  
  
 * Visual Studio .NET 2013: 
     - En esta versión de Visual Studio se incluyen correcciones de errores, mejoras de rendimiento y vistas previas de tecnología de .NET Compiler Platform (“Roslyn”), que pasó a ser el <!--Link to ../roslyn/index.md-->SDK de la plataforma de compilación .NET.

 * C# 5, Visual Studio .NET 2012: 
     - Atributos `Async` / `await` e [información del llamador](../programming-guide/concepts/caller-information.md).

 * C# 4, Visual Studio .NET 2010: 
     - `Dynamic`, [argumentos con nombre](../programming-guide/classes-and-structs/named-and-optional-arguments.md), parámetros opcionales y [covarianza y contravariancia](../programming-guide/concepts/covariance-contravariance/index.md) genéricas.

 * C# 3, Visual Studio .NET 2008: 
     - Inicializadores de objeto y colección, expresiones lambda, métodos de extensión, tipos anónimos, propiedades automáticas, inferencia de tipo `var` local y [Language Integrated Query (LINQ)](../programming-guide/concepts/linq/index.md).

 * C# 2, Visual Studio .NET 2005: 
     - Métodos anónimos, genéricos, tipos que aceptan valores NULL, iteradores/rendimiento, clases `static`, covarianza y contravarianza para delegados.

 * C# 1.1, Visual Studio .NET 2003: 
     - Pragma `#line` y comentarios de documentos xml.

 * C# 1, Visual Studio .NET 2002: 
     - La primera versión de [C#](../csharp.md).   

