---
title: Palabra clave readonly (Referencia de C#)
ms.date: 06/21/2018
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: 96607f1dd7f019169446e29a08496fb54e1ed493
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2018
ms.locfileid: "37961188"
---
# <a name="readonly-c-reference"></a>readonly (Referencia de C#)

La palabra clave `readonly` es un modificador que se puede usar en tres contextos:

- En una [declaración de campo](#readonly-field-example), `readonly` indica que la asignación a un campo solo se puede producir como parte de la declaración o en un constructor de la misma clase.
- En una [definición de `readonly struct`](#readonly-struct-example), `readonly` indica que `struct` es inmutable.
- En una [devolución del método `ref readonly`](#ref-readonly-return-example), el modificador `readonly` indica que el método devuelve una referencia y las operaciones de escritura no se permiten en esa referencia.

Los dos contextos finales se agregaron en C# 7.2.

## <a name="readonly-field-example"></a>Ejemplo de campo readonly  

En este ejemplo, el valor del campo `year` no se puede cambiar en el método `ChangeYear`, aunque se asigne un valor en el constructor de clase:  
  
[!code-csharp[Readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyField)]  
  
Solo se puede asignar un valor a un campo `readonly` en los siguientes contextos:  
  
- Cuando la variable se inicializa en la declaración, por ejemplo:  

```csharp
public readonly int y = 5;  
```

- En un constructor de instancia de la clase que contiene la declaración de campo de instancia.
- En el constructor estático de la clase que contiene la declaración de campo estático.

Estos contextos de constructor son también los únicos en los que es válido pasar un campo `readonly` como parámetro [out](out-parameter-modifier.md) o [ref](ref.md).  
  
> [!NOTE]
> La palabra clave `readonly` es diferente de la palabra clave [const](const.md). Un campo `const` solo se puede inicializar en la declaración del campo. Un campo `readonly` se puede inicializar en la declaración o en un constructor. Por lo tanto, los campos `readonly` pueden tener diferentes valores en función del constructor que se use. Además, mientras que un campo `const` es una constante en tiempo de compilación, el campo `readonly` puede usarse para constantes en tiempo de ejecución, como muestra el siguiente ejemplo:  

```csharp
public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;  
```

[!code-csharp[Initialize readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#InitReadonlyField)]  
  
En el ejemplo anterior, si se usa una instrucción como el ejemplo siguiente:  
  
`p2.y = 66;        // Error`  
  
se obtendrá el siguiente mensaje de error del compilador:  
  
`The left-hand side of an assignment must be an l-value`  
  
que es el mismo error que se obtiene al intentar asignar un valor a una constante.  

## <a name="readonly-struct-example"></a>Ejemplo de estructura de solo lectura

El modificador `readonly` en una definición `struct` declara que la estructura es **inmutable**. Todos los campos de instancia de `struct` se deben marcar como `readonly`, como se muestra en el ejemplo siguiente:

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyStruct)]  

En el ejemplo anterior se usan [propiedades automáticas de solo lectura](../../properties.md#read-only) para declarar su almacenamiento. Eso indica al compilador que cree campos de respaldo `readonly` para esas propiedades. También se podrían declarar campos `readonly` directamente:

```csharp
public readonly struct Point
{
    public readonly double X;
    public readonly double Y;

    public Point(double x, double y) => (X, Y) = (x, y);

    public override string ToString() => $"({X}, {Y})";
}
```

La adición de un campo `readonly` no marcado genera el error del compilador `CS8340`: "Los campos de instancia de las estructuras readonly deben ser readonly".

## <a name="ref-readonly-return-example"></a>Ejemplo de devolución de Ref readonly

El modificador `readonly` en una `ref return` indica que la referencia devuelta no se puede modificar. En el ejemplo siguiente se devuelve una referencia al origen. Usa el modificador `readonly` para indicar que los autores de la llamada no pueden modificar el origen:

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyReturn)]  
No es necesario que el tipo devuelto sea una `readonly struct`. Cualquier tipo que `ref` pueda devolver `ref readonly` también puede devolver.

## <a name="c-language-specification"></a>Especificación del lenguaje C#  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
[Referencia de C#](../../../csharp/language-reference/index.md)  
[Guía de programación de C#](../../../csharp/programming-guide/index.md)  
[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)  
[Modificadores](../../../csharp/language-reference/keywords/modifiers.md)  
[const](../../../csharp/language-reference/keywords/const.md)  
[Campos](../../../csharp/programming-guide/classes-and-structs/fields.md)
