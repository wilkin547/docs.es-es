---
title: "La relación entre las características de lenguaje y tipos de biblioteca | Documentos de Microsoft"
description: "Características del lenguaje a veces se basan en tipos de biblioteca para la implementación. Conocer dicha relación."
keywords: "Diseño del lenguaje C#, biblioteca estándar"
author: billwagner
ms.author: wiwagn
ms.date: 07/20/2017
ms.topic: article
ms.prod: .net
ms.devlang: devlang-csharp
ms.openlocfilehash: 93fd26a72743fcf45df3904cb8d0c787d8a228a8
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2017
---
# <a name="relationships-between-language-features-and-library-types"></a>Relaciones entre las características de lenguaje y tipos de biblioteca

La definición del lenguaje C# requiere una biblioteca estándar que ciertos tipos y determinados miembros accesibles de acuerdo con esos tipos. El compilador genera código que usa estos miembros y tipos necesarios para muchas características de idioma diferente. Cuando sea necesario, hay paquetes de NuGet que contienen tipos necesarios para las versiones más recientes del lenguaje, al escribir código para entornos donde los tipos o miembros aún no han implementado todavía.

Esta dependencia en la funcionalidad de la biblioteca estándar ha formado parte del lenguaje C# desde su primera versión. En esta versión, ejemplos que se incluyen:

* <xref:System.Exception>-usa para todas las excepciones generadas por el compilador.
* <xref:System.String>-C# `string` tipo es un sinónimo de <xref:System.String>.
* <xref:System.Int32>-sinónimo de `int`.

Esta primera versión fue simple: el compilador y la biblioteca estándar de envía juntos, y se había solo una versión de cada uno.

Las versiones posteriores de C# en ocasiones, han agregado nuevos tipos o miembros a las dependencias. Algunos ejemplos son: <xref:System.Runtime.CompilerServices.INotifyCompletion>, <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> y <xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>. C# 7.0 Esto continúa si se agrega una dependencia en <xref:System.ValueTuple> para implementar la [tuplas](../tuples.md) característica del lenguaje.

El equipo de diseño de lenguaje funciona para minimizar el área expuesta de los tipos y miembros que se requieren en una biblioteca estándar compatible. Ese objetivo se equilibra con un diseño limpio donde se incorporan perfectamente nuevas características de la biblioteca en el idioma. Habrá nuevas características en versiones futuras de C# que requieren nuevos tipos y miembros de una biblioteca estándar. Es importante entender cómo administrar tales dependencias en el trabajo.

## <a name="managing-your-dependencies"></a>Administrar las dependencias

Herramientas del compilador de C# ahora se separan de su ciclo de lanzamiento de las bibliotecas de .NET en las plataformas compatibles. De hecho, distintas bibliotecas de .NET tienen ciclos de lanzamiento distintos: .NET Framework en Windows es relesed como una actualización de Windows, .NET Core se incluye en una programación independiente y las versiones de Xamarin de biblioteca se incluyen las actualizaciones con las herramientas de Xamarin para cada plataforma de destino.

La mayoría del tiempo, no notarás estos cambios. Sin embargo, cuando se trabaja con una versión más reciente del idioma que requiere algunas características no todavía en las bibliotecas de .NET en esa plataforma, podrá hacer referencia los paquetes de NuGet para proporcionar los nuevos tipos.
Como las plataformas que admite su aplicación se actualiza con las nuevas instalaciones de framework, puede quitar la referencia adicional.

Esta separación significa que puede usar nuevas características de lenguaje incluso cuando el destino es máquinas que no tenga el marco de trabajo correspondiente.
