---
title: 'Enumeraciones de C#: un paseo por el lenguaje C#'
description: Obtenga información sobre enumeraciones, constantes con nombre discretas en C#
ms.date: 08/10/2016
ms.assetid: 7faba1cc-6ea9-4a19-adb9-0335e4b132e5
ms.openlocfilehash: 7fe2626381cb90e55842e3be17dd450eb73d5a5b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33353359"
---
# <a name="enums"></a>Enumeraciones

Un ***tipo de enumeración*** es un tipo de valor distinto con un conjunto de constantes con nombre. Las enumeraciones se definen cuando se necesita fijar un tipo que pueda tener un conjunto de valores discretos. Usan uno de los tipos de valor integral como almacenamiento subyacente. Proporcionan significado semántico a los valores discretos.

En el ejemplo siguiente se declara y usa un tipo `enum` denominado `Color` con tres valores constantes, `Red`, `Green` y `Blue`.

[!code-csharp[EnumExample](../../../samples/snippets/csharp/tour/enums/Program.cs#L3-L36)]

A cada tipo `enum` le corresponde un tipo entero conocido como el ***tipo subyacente*** del tipo `enum`. Un tipo `enum` que no declara explícitamente un tipo subyacente tiene un tipo subyacente de `int`. El formato de almacenamiento de un tipo `enum` y el intervalo de valores posibles se determinan por el tipo subyacente. El conjunto de valores que un tipo `enum` puede asumir no está limitado por sus miembros `enum`. En concreto, cualquier valor del tipo subyacente de un tipo `enum` puede convertirse en el tipo `enum` y es un valor válido distinto de ese tipo `enum`.

En el ejemplo siguiente se declara un tipo `enum` denominado `Alignment` con un tipo subyacente de `sbyte`.

[!code-csharp[EnumStorage](../../../samples/snippets/csharp/tour/enums/Program.cs#L38-L43)]

Como se muestra en el ejemplo anterior, una declaración de miembro `enum` puede incluir una expresión constante que especifica el valor del miembro. El valor constante para cada miembro `enum` debe estar en el intervalo del tipo subyacente de `enum`. Cuando una declaración de miembro `enum` no especifica explícitamente un valor, al miembro se le asigna el valor cero (si es el primer miembro en el tipo `enum`) o el valor del miembro textualmente anterior `enum` más uno.

Los valores `Enum` se pueden convertir a valores integrales y viceversa, usando las conversiones de tipo. Por ejemplo:

[!code-csharp[EnumStorage](../../../samples/snippets/csharp/tour/enums/Program.cs#L49-L50)]

El valor predeterminado de cualquier tipo `enum` es el valor integral cero convertido al tipo `enum`. En los casos donde las variables se inicializan automáticamente en un valor predeterminado, este es el valor que se le asigna a las variables de tipos `enum`. Para que el valor predeterminado de un tipo `enum` esté fácilmente disponible, el literal `0` se convierte implícitamente a cualquier tipo `enum`. Por tanto, el siguiente código es válido.

[!code-csharp[EnumZero](../../../samples/snippets/csharp/tour/enums/Program.cs#L58-L58)]

>[!div class="step-by-step"]
[Anterior](interfaces.md)
[Siguiente](delegates.md)
