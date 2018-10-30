---
title: Novedades de C# - Guía de C#
description: Cómo evoluciona el lenguaje C#
ms.date: 11/13/2017
ms.assetid: 77deec51-a14d-46d4-9bb3-faf449477149
ms.openlocfilehash: b079c21ee90a797b038b96ae68123a538464c382
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2018
ms.locfileid: "50201444"
---
# <a name="whats-new-in-c"></a>Novedades de C# #

En esta página se brinda una guía básica de las características nueva de cada versión importante del lenguaje C#. Los artículos vinculados proporcionan información detallada sobre las características principales que se agregaron en cada versión. Encontrará información sobre las nuevas características que se han publicado en una versión general o en una versión preliminar pública. Se puede encontrar información sobre el estado detallado de las características de lenguaje, incluidas las características consideradas para las próximas versiones, [en el repositorio dotnet/roslyn](https://github.com/dotnet/roslyn/blob/master/docs/Language%20Feature%20Status.md) de GitHub.

> [!IMPORTANT]
> El lenguaje C# se basa en tipos y métodos de una *biblioteca estándar* para algunas de las características. Un ejemplo es el procesamiento de excepciones. Cada expresión o instrucción `throw` se comprueba para asegurarse de que el objeto que se genera deriva de <xref:System.Exception>. Del mismo modo, cada `catch` se comprueba para asegurarse de que el tipo que se captura deriva de <xref:System.Exception>. Cada versión puede agregar requisitos nuevos. Para usar las características más recientes del lenguaje en entornos anteriores, es posible que tenga que instalar bibliotecas específicas. Estas dependencias están documentadas en la página de cada versión específica. Puede obtener más información sobre las [relaciones entre lenguaje y biblioteca](relationships-between-language-and-library.md) para tener más antecedentes sobre esta dependencia. 

Para usar las características más recientes en una versión secundaria, tendrá que [configurar la versión del idioma de compilador](../language-reference/configure-language-version.md) y seleccionar la versión.

* [C# 7.3](csharp-7-3.md):
  - En esta página se describen las características más recientes del lenguaje C#. C# 7.3 se encuentra disponible actualmente en la [versión 15.7 de Visual Studio 2017](https://visualstudio.microsoft.com/vs/whatsnew/) y en el [SDK 2.1.300 RC1 de .NET Core 2.1](../../core/whats-new/index.md).
* [C# 7.2](csharp-7-2.md):
  - En esta página se describen las características que se han agregado en el lenguaje C#. C# 7.2 se encuentra disponible actualmente en la [versión 15.5 de Visual Studio 2017](https://visualstudio.microsoft.com/vs/whatsnew/) y en el [SDK de .NET Core 2.0](../../core/whats-new/index.md).
* [C# 7.1](csharp-7-1.md):
  - En esta página se describen las características que se han agregado en C# 7.1. Estas características se agregaron en la [versión 15.3 de Visual Studio 2017](https://visualstudio.microsoft.com/vs/whatsnew/) y en el [SDK de .NET Core 2.0](../../core/whats-new/index.md).
* [C# 7.0](csharp-7.md):
  - En esta página se describen las características que se han agregado en C# 7.0. Estas características se agregaron a [Visual Studio 2017](https://visualstudio.microsoft.com/vs/whatsnew/) y [.NET Core 1.0](../../core/whats-new/index.md) y versiones posteriores.
* [C# 6](csharp-6.md):
  - En esta página se describen las características que se agregaron en C# 6. Estas características están disponibles en Visual Studio 2015 para desarrolladores de Windows y en .NET Core 1.0 para desarrolladores que exploran C# en macOS y Linux.
* [Compatibilidad multiplataforma](../../core/index.md):
  - C#, mediante la compatibilidad con .NET Core, se ejecuta en varias plataformas. Si está interesado en probar C# en macOS o en alguna de las muchas distribuciones de Linux compatibles, puede obtener más información sobre .NET Core.
* [SDK de .NET Compiler Platform](../roslyn-sdk/index.md):
  - El SDK de .NET Compiler Platform permite escribir código que realiza análisis estadísticos sobre el código C#. Puede utilizar estas API para buscar posibles errores o prácticas incorrectas, sugerir correcciones e incluso implementar esas correcciones.

## <a name="previous-versions"></a>Versiones anteriores

A continuación se enumeran las características clave que se presentaron en versiones anteriores del lenguaje C# y Visual Studio .NET.

* Visual Studio .NET 2013:
  - En esta versión de Visual Studio se incluyen correcciones de errores, mejoras de rendimiento y vistas previas de tecnología de .NET Compiler Platform (“Roslyn”), que pasó a ser el [SDK de la plataforma de compilación .NET](../roslyn-sdk/index.md).
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
