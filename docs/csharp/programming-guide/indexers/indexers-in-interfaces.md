---
title: 'Indizadores en interfaces: Guía de programación de C#'
description: Los indexadores se pueden declarar en una interfaz de C#. Conozca de qué modo los descriptores de acceso de los indexadores de interfaz se diferencian de los descriptores de acceso de los indexadores de clase.
ms.date: 02/08/2020
helpviewer_keywords:
- indexers [C#], in interfaces
- accessors [C#], indexers
ms.assetid: e16b54bd-4a83-4f52-bd75-65819fca79e8
ms.openlocfilehash: ec77843bdf3181a543bd6c02cfb034b21ded1ae7
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303106"
---
# <a name="indexers-in-interfaces-c-programming-guide"></a>Indizadores en interfaces (Guía de programación de C#)

Los indexadores se pueden declarar en una [interfaz](../../language-reference/keywords/interface.md). Los descriptores de acceso de los indexadores de interfaz se diferencian de los descriptores de acceso de los indexadores de [clase](../../language-reference/keywords/class.md) de las maneras siguientes:

- Los descriptores de acceso de interfaz no usan modificadores.
- Normalmente, un descriptor de acceso de interfaz no tiene un cuerpo.

El propósito del descriptor de acceso es indicar si el indizador es de lectura y escritura, de solo lectura o de solo escritura. Puede proporcionar una implementación para un indizador definido en una interfaz, pero esto es poco frecuente. Los indizadores suelen definir una API para acceder a los campos de datos y los campos de datos no se pueden definir en una interfaz.

A continuación tiene un ejemplo de un descriptor de acceso de indexador de interfaz:

[!code-csharp[DefineInterface](~/samples/snippets/csharp/interfaces/indexers.cs#DefineIndexer)]

La firma de un indexador debe ser diferente de las firmas de los demás indexadores declarados en la misma interfaz.

## <a name="example"></a>Ejemplo

En el siguiente ejemplo, se muestra cómo implementar indexadores de interfaz.

[!code-csharp[Implement](~/samples/snippets/csharp/interfaces/indexers.cs#ImplementInterface)]

[!code-csharp[DefineInterface](~/samples/snippets/csharp/interfaces/indexers.cs#ExampleCode)]

En el ejemplo anterior, podría usar la implementación del miembro de interfaz explícita al usar el nombre completo del miembro de interfaz. Por ejemplo

```csharp
string IIndexInterface.this[int index]
{
}
```

En cambio, el nombre completo solo es necesario para evitar la ambigüedad cuando la clase implementa más de una interfaz con la misma firma de indexador. Por ejemplo, si una clase `Employee` implementa dos interfaces `ICitizen` y `IEmployee` y ambas interfaces tienen la misma firma de indexador, la implementación del miembro de interfaz explícita es necesaria. Es decir, la siguiente declaración de indexador:

```csharp
string IEmployee.this[int index]
{
}
```

implementa el indexador en la interfaz `IEmployee`, mientras que la siguiente declaración:

```csharp
string ICitizen.this[int index]
{
}
```

implementa el indexador en la interfaz `ICitizen`.

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Indizadores](./index.md)
- [Propiedades](../classes-and-structs/properties.md)
- [Interfaces](../interfaces/index.md)
