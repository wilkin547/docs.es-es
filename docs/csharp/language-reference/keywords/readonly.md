---
title: readonly (palabra clave) - Referencia de C#
ms.date: 06/21/2018
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: 165b6287e1610e013b289601e1535a08fdd3b5c9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398128"
---
# <a name="readonly-c-reference"></a>readonly (Referencia de C#)

La palabra clave `readonly` es un modificador que se puede usar en cuatro contextos:

- En una [declaración de campo](#readonly-field-example), `readonly` indica que la asignación a un campo solo se puede producir como parte de la declaración o en un constructor de la misma clase. Se puede asignar y reasignar varias veces un campo de solo lectura dentro de la declaración de campo y el constructor.
  
  No se puede asignar un campo `readonly` después de que el constructor salga. Esta regla tiene diferentes implicaciones para los tipos de valor y tipos de referencia:
  
  - Debido a que los tipos de valor contienen directamente sus datos, un campo que es un tipo de valor `readonly` es inmutable.
  - Dado que los tipos de referencia contienen una referencia a sus datos, un campo que es un tipo de referencia `readonly` debe referirse siempre al mismo objeto. Ese objeto no es inmutable. El modificador `readonly` evita que el campo se reemplace por una instancia diferente del tipo de referencia. Sin embargo, el modificador no impide que los datos de instancia del campo se modifiquen a través del campo de solo lectura.

  > [!WARNING]
  > Un tipo visible externamente que contenga un campo de solo lectura visible externamente que sea un tipo de referencia mutable puede ser una vulnerabilidad de seguridad y puede desencadenar la advertencia [CA2104](/visualstudio/code-quality/ca2104): "No declarar tipos de referencias mutables de solo lectura".

- En una [definición de `readonly struct`](#readonly-struct-example), `readonly` indica que `struct` es inmutable.
- En un [miembro de definición `readonly`](#readonly-member-examples), `readonly` indica que un miembro de un elemento `struct` no mutará el estado interno de la estructura.
- En una [devolución del método `ref readonly`](#ref-readonly-return-example), el modificador `readonly` indica que el método devuelve una referencia y las operaciones de escritura no se permiten en esa referencia.

Los contextos `readonly struct` y `ref readonly` se han agregado en C# 7.2. Los miembros de estructura `readonly` se han agregado en C# 8.0.

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
> La palabra clave `readonly` es diferente de la palabra clave [const](const.md). Un campo `const` solo se puede inicializar en la declaración del campo. Un campo `readonly` se puede asignar varias veces en la declaración de campo y en cualquier constructor. Por lo tanto, los campos `readonly` pueden tener diferentes valores en función del constructor que se use. Además, mientras que un campo `const` es una constante en tiempo de compilación, el campo `readonly` puede usarse para constantes en tiempo de ejecución, como muestra el siguiente ejemplo:
>
> ```csharp
> public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;
> ```

[!code-csharp[Initialize readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#InitReadonlyField)]

En el ejemplo anterior, si se usa una instrucción como el ejemplo siguiente:

```csharp
p2.y = 66;        // Error
```

se obtendrá el siguiente mensaje de error del compilador:

**No se puede asignar un campo de solo lectura (excepto en un constructor o inicializador de variable)** .

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

La adición de un campo no marcado `readonly` genera el error del compilador `CS8340`: "Los campos de instancia de las estructuras readonly deben ser readonly".

## <a name="readonly-member-examples"></a>Ejemplos de miembros de solo lectura

Otras veces, se puede crear una estructura que admita la mutación. En esos casos, es probable que algunos de los miembros de instancia no modifiquen el estado interno de la estructura. Se pueden declarar esos miembros de instancia con el modificador `readonly`. El compilador aplica su intención. Si ese miembro modifica el estado directamente o tiene acceso a un miembro que no se declara tampoco con el modificador `readonly`, el resultado es un error en tiempo de compilación. El modificador `readonly` es válido en miembros de `struct`, no en declaraciones de miembros de `class` o `interface`.

Para obtener dos ventajas, aplique el modificador `readonly` a los métodos `struct` aplicables. Lo más importante es que el compilador aplique su intención. El código que modifica el estado no es válido en un método `readonly`. El compilador también puede usar el modificador `readonly` para habilitar las optimizaciones de rendimiento. Cuando la referencia `in` pasa tipos de `struct` grandes, el compilador debe generar una copia defensiva si se puede modificar el estado de la estructura. Si solo se tiene acceso a los miembros de `readonly`, es posible que el compilador no cree la copia defensiva.

El modificador `readonly` es válido en la mayoría de miembros de un elemento `struct`, incluidos los métodos que invalidan los métodos declarados en <xref:System.Object?displayProperty=nameWithType>. Existen algunas restricciones:

- No se pueden declarar propiedades o métodos estáticos `readonly`.
- No se pueden declarar constructores `readonly`.

Puede Agregar el modificador `readonly` a una declaración de propiedad o de indizador:

```csharp
readonly public int Counter
{
  get { return 0; }
  set {} // not useful, but legal
}
```

También puede agregar el modificador `readonly` a los descriptores de acceso individuales `get` o `set` de una propiedad o indizador:

```csharp
public int Counter
{
  readonly get { return _counter; }
  set { _counter = value; }
}
int _counter;
```

No se puede Agregar el modificador `readonly` a una propiedad y a uno o varios de los descriptores de acceso de esa misma propiedad. Esa misma restricción se aplica a los indizadores.

El compilador aplica implícitamente el modificador `readonly` a las propiedades implementadas automáticamente donde el código implementado por el compilador no modifica el estado. Es equivalente a las declaraciones siguientes:

```csharp
public readonly int Index { get; }
// Or:
public int Number { readonly get; }
public string Message { readonly get; set; }
```

Se puede agregar el modificador `readonly` en esas ubicaciones, pero esta acción no tendrá ningún efecto significativo. No se puede agregar el modificador `readonly` a un establecedor de propiedad implementado automáticamente o a una propiedad implementada automáticamente de lectura o escritura.

## <a name="ref-readonly-return-example"></a>Ejemplo de devolución de Ref readonly

El modificador `readonly` en un elemento `ref return` indica que la referencia devuelta no se puede modificar. En el ejemplo siguiente se devuelve una referencia al origen. Usa el modificador `readonly` para indicar que los autores de la llamada no pueden modificar el origen:

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyReturn)]
No es necesario que el tipo devuelto sea una `readonly struct`. Cualquier tipo que pueda devolver `ref` también puede devolver `ref readonly`.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

También puede ver las propuestas de especificación del lenguaje:

- [referencia de solo lectura y estructura de solo lectura](~/_csharplang/proposals/csharp-7.2/readonly-ref.md)
- [miembros de estructura de solo lectura](~/_csharplang/proposals/csharp-8.0/readonly-instance-members.md)

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [Modificadores](index.md)
- [const](const.md)
- [Campos](../../programming-guide/classes-and-structs/fields.md)
