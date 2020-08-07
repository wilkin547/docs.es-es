---
title: 'Implementación de interfaz explícita: Guía de programación de C#'
description: Una clase puede implementar interfaces que contengan un miembro con la misma firma en C#. La implementación explícita crea un miembro de clase específico de una interfaz.
ms.date: 01/24/2020
helpviewer_keywords:
- explicit interfaces [C#]
- interfaces [C#], explicit
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
ms.openlocfilehash: a6ec328c08d1da84a11431d9400a094df8c72223
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303092"
---
# <a name="explicit-interface-implementation-c-programming-guide"></a>Implementación de interfaz explícita (Guía de programación de C#)

Si una [clase](../../language-reference/keywords/class.md) implementa dos interfaces que contienen un miembro con la misma firma, entonces al implementar ese miembro en la clase ambas interfaces usarán ese miembro como su implementación. En el ejemplo siguiente, todas las llamadas a `Paint` invocan el mismo método. En este primer ejemplo se definen los tipos:

[!code-csharp[DefineSimpleTypes](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#DefineTypes)]

En el ejemplo siguiente se llama a los métodos:

[!code-csharp[DefineSimpleTypes](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallMethods)]

Cuando dos miembros de interfaz no realizan la misma función, puede provocar una implementación incorrecta de una o ambas interfaces. Es posible implementar un miembro de interfaz de manera explícita: mediante la creación de un miembro de clase que solo se llama a través de la interfaz, y es específico de esa interfaz. Asigne al miembro de clase el nombre de la interfaz y un punto. Por ejemplo:

[!code-csharp[DefineExplicitImplementation](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#ExplicitImplementation)]

El miembro de clase `IControl.Paint` solo está disponible a través de la interfaz `IControl`, y `ISurface.Paint` solo está disponible mediante `ISurface`. Las dos implementaciones de método son independientes, y ninguna está disponible directamente en la clase. Por ejemplo:

[!code-csharp[CallExplicitImplementation](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallExplicitImplementation)]

La implementación explícita también se usa para resolver casos donde dos interfaces declaran miembros diferentes del mismo nombre como una propiedad y un método. Para implementar ambas interfaces, una clase tiene que usar la implementación explícita para la propiedad `P` o el método `P`, o ambos, para evitar un error del compilador. Por ejemplo:

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#NameCollision)]

A partir de [C# 8.0](../../whats-new/csharp-8.md#default-interface-methods), se puede definir una implementación para los miembros declarados en una interfaz. Si una clase hereda una implementación de método de una interfaz, ese método solo es accesible a través de una referencia del tipo de interfaz. El miembro heredado no aparece como parte de la interfaz pública. En el ejemplo siguiente se define una implementación predeterminada para un método de interfaz:

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#DefaultImplementation)]

En el ejemplo siguiente se invoca la implementación predeterminada:

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallDefaultImplementation)]

Cualquier clase que implemente la interfaz `IControl` puede invalidar el método `Paint` predeterminado, ya sea como un método público, o bien como una implementación de interfaz explícita.

## <a name="see-also"></a>Consulte también

- [Guía de programación de C#](../index.md)
- [Clases y structs](../classes-and-structs/index.md)
- [Interfaces](./index.md)
- [Herencia](../classes-and-structs/inheritance.md)
