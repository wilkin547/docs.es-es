---
title: 'struct: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- struct_CSharpKeyword
helpviewer_keywords:
- struct keyword [C#]
- structs [C#], struct keyword
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
ms.openlocfilehash: 5317ea403575dca7ed64a5784fa9c993fa8d2f64
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633838"
---
# <a name="struct-c-reference"></a>struct (Referencia de C#)

Un tipo `struct` es un tipo de valor que normalmente se usa para encapsular pequeños grupos de variables relacionadas, como las coordenadas de un rectángulo o las características de un elemento en un inventario. En el siguiente ejemplo se muestra una declaración de struct simple:

```csharp
public struct Book
{
    public decimal price;
    public string title;
    public string author;
}
```

## <a name="remarks"></a>Comentarios

Los structs también pueden contener [constructores](../../programming-guide/classes-and-structs/constructors.md), [constantes](../../programming-guide/classes-and-structs/constants.md), [campos](../../programming-guide/classes-and-structs/fields.md), [métodos](../../programming-guide/classes-and-structs/methods.md), [propiedades](../../programming-guide/classes-and-structs/properties.md), [indexadores](../../programming-guide/indexers/index.md), [operadores](../../programming-guide/statements-expressions-operators/operators.md), [eventos](../../programming-guide/events/index.md) y [tipos anidados](../../programming-guide/classes-and-structs/nested-types.md), aunque si se necesitan varios de estos miembros, puede considerar la posibilidad de crear su propio tipo de clase.

Para obtener ejemplos, vea [Usar estructuras](../../programming-guide/classes-and-structs/using-structs.md).

Los structs pueden implementar una interfaz, pero no pueden heredar de otro struct. Por ese motivo, los miembros de struct no se pueden declarar como `protected`.

Para obtener más información, vea [Structs](../../programming-guide/classes-and-structs/structs.md).

## <a name="examples"></a>Ejemplos

Para obtener ejemplos y más información, vea [Usar estructuras](../../programming-guide/classes-and-structs/using-structs.md).

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener ejemplos, vea [Usar estructuras](../../programming-guide/classes-and-structs/using-structs.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [Tabla de valores predeterminados](default-values-table.md)
- [Tabla de tipos integrados](built-in-types-table.md)
- [Tipos](types.md)
- [Tipos de valor](value-types.md)
- [class](class.md)
- [interface](interface.md)
- [Clases y structs](../../programming-guide/classes-and-structs/index.md)
