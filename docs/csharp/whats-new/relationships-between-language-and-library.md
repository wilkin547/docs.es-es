---
title: Relación entre características de lenguaje y tipos de biblioteca | Microsoft Docs
description: Las características de lenguaje suelen basarse en tipos de biblioteca para la implementación. Entienda esa relación.
ms.date: 07/20/2017
ms.openlocfilehash: dfae7972af0a251a92700d7d33bd6f971eb1870e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "61706031"
---
# <a name="relationships-between-language-features-and-library-types"></a>Relaciones entre características de lenguaje y tipos de biblioteca

La definición del lenguaje C# exige que una biblioteca estándar tenga determinados tipos y determinados miembros accesibles en esos tipos. El compilador genera código que usa estos miembros y tipos necesarios para muchas características de lenguaje diferentes. En caso necesario, hay paquetes NuGet que contienen tipos necesarios para las versiones más recientes del lenguaje al escribir código para entornos donde esos tipos o miembros aún no se han implementado.

Esta dependencia de la funcionalidad de la biblioteca estándar ha formado parte del lenguaje C# desde su primera versión. En esa versión, los ejemplos incluían:

* <xref:System.Exception>: usado para todas las excepciones generadas por el compilador.
* <xref:System.String>: el tipo `string` de C# es sinónimo de <xref:System.String>.
* <xref:System.Int32>: sinónimo de `int`.

Esa primera versión era simple: el compilador y la biblioteca estándar se distribuían juntos y solo había una versión de cada uno.

Las versiones posteriores de C# a veces han agregado nuevos tipos o miembros a las dependencias. Los ejemplos incluyen: <xref:System.Runtime.CompilerServices.INotifyCompletion>, <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> y <xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>. C# 7.0 continúa esta tendencia al agregar una dependencia a <xref:System.ValueTuple> para implementar la característica de lenguaje [tuplas](../tuples.md).

El equipo de diseño del lenguaje se esfuerza por minimizar el área expuesta de los tipos y miembros necesarios en una biblioteca estándar compatible. Ese objetivo está equilibrado con un diseño limpio donde las nuevas características de la biblioteca se han incorporado sin problemas al lenguaje. Habrá nuevas características en versiones futuras de C# que exijan nuevos tipos y miembros en una biblioteca estándar. Es importante entender cómo administrar esas dependencias en el trabajo.

## <a name="managing-your-dependencies"></a>Administración de dependencias

Las herramientas del compilador de C# ahora se han desvinculado del ciclo de versiones de las bibliotecas de .NET en las plataformas compatibles. De hecho, las distintas bibliotecas de .NET tienen ciclos de versiones diferentes: .NET Framework en Windows se distribuye como una actualización de Windows, .NET Core se distribuye conforme a una programación independiente y las versiones de Xamarin de actualizaciones de la biblioteca se incluyen en las herramientas de Xamarin de cada plataforma de destino.

En la mayoría de las ocasiones estos cambios no son perceptibles. Pero cuando trabaje con una versión más reciente del lenguaje que requiera características aún no incluidas en las bibliotecas de .NET de esa plataforma, haga referencia a los paquetes NuGet para proporcionar esos nuevos tipos.
A medida que las plataformas que admite la aplicación se actualicen con las nuevas instalaciones del marco de trabajo, puede quitar la referencia adicional.

Esta desvinculación significa que puede usar nuevas características de lenguaje aun cuando el destino sean equipos que no tengan el marco de trabajo correspondiente.
