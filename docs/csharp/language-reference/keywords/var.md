---
description: 'var: Referencia de C#'
title: 'var: Referencia de C#'
ms.date: 10/02/2020
f1_keywords:
- var
- var_CSharpKeyword
helpviewer_keywords:
- var keyword [C#]
ms.assetid: 0777850a-2691-4e3e-927f-0c850f5efe15
ms.openlocfilehash: d04bea9bcf5be726d3e81a1a53abed31f59330a0
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "91608717"
---
# <a name="var-c-reference"></a>var (Referencia de C#)

A partir de C# 3, las variables que se declaran en el ámbito de método pueden tener un "tipo" `var` implícito. Una variable local con tipo implícito es fuertemente tipada exactamente igual que si hubiera declarado el tipo, solo que en este caso es el compilador el que lo determina. Las dos declaraciones siguientes de `i` tienen una función equivalente:

```csharp
var i = 10; // Implicitly typed.
int i = 10; // Explicitly typed.
```

> [!IMPORTANT]
> Cuando `var` se usa con [tipos de referencia que aceptan valores NULL](../builtin-types/nullable-reference-types.md), siempre implica un tipo de referencia que acepta valores NULL, aunque el tipo de expresión no los acepte.

Un uso común de la palabra clave `var` es con las expresiones de invocación del constructor. El uso de `var` permite no repetir un nombre de tipo en una declaración de variable y una creación de instancias de objeto, como se muestra en el ejemplo siguiente:

```csharp
var xs = new List<int>();
```

A partir de C# 9.0, se puede usar una [expresión `new`](../operators/new-operator.md) de con tipo de destino como alternativa:

```csharp
List<int> xs = new();
List<int>? ys = new();
```

## <a name="example"></a>Ejemplo

En el siguiente ejemplo se muestran dos expresiones de consulta. En la primera expresión, el uso de `var` se permite pero no es necesario, ya que el tipo del resultado de la consulta se puede indicar explícitamente como `IEnumerable<string>`. En cambio, en la segunda expresión, `var` permite que el resultado sea una colección de tipos anónimos y solo el compilador puede tener acceso al nombre de ese tipo. El uso de `var` elimina la necesidad de crear una nueva clase para el resultado. Tenga en cuenta que, en el ejemplo 2, la variable de iteración `foreach``item` también debe tener tipo implícito.

[!code-csharp[csrefKeywordsTypes#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#18)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Variables locales con asignación implícita de tipos](../../programming-guide/classes-and-structs/implicitly-typed-local-variables.md)
- [Relaciones entre tipos en las operaciones de consulta LINQ](../../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)
