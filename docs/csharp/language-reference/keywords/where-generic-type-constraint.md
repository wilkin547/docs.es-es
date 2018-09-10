---
title: where (restricción de tipo genérico) (Referencia de C#)
ms.date: 04/12/2018
f1_keywords:
- whereconstraint
- whereconstraint_CSharpKeyword
helpviewer_keywords:
- where (generic type constraint) [C#]
ms.openlocfilehash: 34246824fb8ff28e47ea424c78eca38e999a30b6
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43500829"
---
# <a name="where-generic-type-constraint-c-reference"></a>where (restricción de tipo genérico) (Referencia de C#)

La cláusula `where` en una definición genérica especifica restricciones en los tipos que se usan como argumentos para los parámetros de tipo en un tipo genérico, método, delegado o función local. Las restricciones pueden especificar interfaces o clases base, o bien requerir que un tipo genérico sea una referencia, un valor o un tipo no administrado. Declaran las funcionalidades que debe poseer el argumento de tipo.

Por ejemplo, se puede declarar una clase genérica, `MyGenericClass`, de modo que el parámetro de tipo `T` implemente la interfaz <xref:System.IComparable%601>:

[!code-csharp[using an interface constraint](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#1)]

> [!NOTE]
> Para obtener más información sobre la cláusula where en una expresión de consulta, vea [where (Cláusula)](where-clause.md).

La cláusula `where` también puede incluir una restricción de clase base. La restricción de clase base indica que un tipo que se usará como argumento de tipo para ese tipo genérico tiene la clase especificada como clase base (o es la clase base) para que se use como argumento de tipo para ese tipo genérico. Si se usa la restricción de clase base, debe aparecer antes que cualquier otra restricción de ese parámetro de tipo. Algunos tipos no están permitidos como restricción de clase base: <xref:System.Object>, <xref:System.Array> y <xref:System.ValueType>. Antes de C# 7.3, tampoco se permitían <xref:System.Enum>, <xref:System.Delegate> y <xref:System.MulticastDelegate> como restricciones de clase base. En el ejemplo siguiente se muestran los tipos que ahora se pueden especificar como clase base:

[!code-csharp[using an interface constraint](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#2)]

La cláusula `where` puede especificar que el tipo es `class` o `struct`. La restricción `struct` elimina la necesidad de especificar una restricción de clase base de `System.ValueType`. El tipo `System.ValueType` no se puede usar como restricción de clase base. En el ejemplo siguiente se muestran las restricciones `class` y `struct`:

[!code-csharp[using the class and struct constraints](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#3)]

La cláusula `where` también podría incluir una restricción `unmanaged`. La restricción `unmanaged` limita el parámetro de tipo a los tipos conocidos como **tipos no administrados**. Un **tipo no administrado** es un tipo que no es un tipo de referencia y no contiene campos de tipo de referencia en ningún nivel de anidamiento. La restricción `unmanaged` hace que sea más fácil escribir código de interoperabilidad de bajo nivel en C#. Esta restricción habilita las rutinas reutilizables en todos los tipos no administrados. La restricción `unmanaged` no se puede combinar con las restricciones `class` o `struct`. La restricción `unmanaged` exige que el tipo sea `struct`:

[!code-csharp[using the unmanaged constraint](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#4)]

La cláusula `where` también podría incluir una restricción de constructor, `new()`. Esta restricción hace posible crear una instancia de un parámetro de tipo con el operador `new`. La [restricción new()](new-constraint.md) permite que el compilador sepa que cualquier argumento de tipo especificado debe tener accesible un constructor sin parámetros o el constructor predeterminado. Por ejemplo:

[!code-csharp[using the new constraint](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#5)]

La restricción `new()` aparece en último lugar en la cláusula `where`. La restricción `new()` no se puede combinar con las restricciones `struct` o `unmanaged`. Todos los tipos que cumplan esas restricciones deben tener un constructor sin parámetros accesible, lo que hace que la restricción `new()` sea redundante.

Con varios parámetros de tipo, use una cláusula `where` para cada parámetro de tipo, por ejemplo:

[!code-csharp[using multiple where constraints](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#6)]

También puede asociar restricciones a parámetros de tipo de métodos genéricos, como se muestra en el ejemplo siguiente:

[!code-csharp[where constraints with generic methods](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#7)]

Observe que la sintaxis para describir las restricciones de parámetro de tipo en delegados es igual que la de métodos:

[!code-csharp[where constraints with generic methods](../../../../samples/snippets/csharp/keywords/GenericWhereConstraints.cs#8)]

Para obtener información sobre los delegados genéricos, vea [Delegados genéricos](../../../csharp/programming-guide/generics/generic-delegates.md).

Para obtener más información sobre la sintaxis y el uso de restricciones, vea [Restricciones de tipos de parámetros](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).

## <a name="c-language-specification"></a>especificación del lenguaje C#

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../../../csharp/language-reference/index.md)  
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Introducción a los genéricos](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
- [new (restricción)](../../../csharp/language-reference/keywords/new-constraint.md)  
- [Restricciones de tipos de parámetros](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)  
