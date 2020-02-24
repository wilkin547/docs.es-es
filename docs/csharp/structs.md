---
title: 'Structs: Guía de C#'
description: Obtenga información sobre el tipo struct y cómo se crea.
ms.date: 10/12/2016
ms.technology: csharp-fundamentals
ms.assetid: a7094b8c-7229-4b6f-82fc-824d0ea0ec40
ms.openlocfilehash: 540742ea6a215e09f0cc31b218ac10fbf6192352
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503990"
---
# <a name="structs"></a>Estructuras

Un *struct* es un tipo de valor. Cuando se crea un struct, la variable a la que se asigna el struct contiene los datos reales del struct. Cuando la estructura se asigna a una nueva variable, se copia. Por lo tanto, la nueva variable y la variable original contienen dos copias independientes de los mismos datos. Los cambios realizados en una copia no afectan a la otra copia.

Las variables de tipo de valor contienen directamente sus valores, lo que significa que la memoria se asigna insertada en cualquier contexto en el que se declare la variable. No se produce ninguna asignación del montón independiente ni sobrecarga de la recolección de elementos no utilizados para las variables de tipo de valor.

Existen dos categorías de tipos de valor: [struct](language-reference/keywords/struct.md) y [enum](language-reference/builtin-types/enum.md).

Los tipos numéricos integrados son structs y tienen propiedades y métodos a los que se puede obtener acceso:

[!code-csharp[Static Method](../../samples/snippets/csharp/concepts/structs/static-method.cs)]

Pero se declaran y se les asignan valores como si fueran tipos simples no agregados:

[!code-csharp[Assign Values](../../samples/snippets/csharp/concepts/structs/assign-value.cs)]

Los tipos de valor están *sellados*, lo que significa que, por ejemplo, no puede derivar un tipo de <xref:System.Int32>, y no puede definir un struct para que herede de cualquier clase o struct definido por el usuario, porque un struct solo puede heredar de <xref:System.ValueType>. A pesar de ello, un struct puede implementar una o más interfaces. Puede convertir un tipo struct en un tipo de interfaz. Esto hace que una operación de conversión *boxing* encapsule el struct dentro de un objeto de tipo de referencia en el montón administrado. Las operaciones de conversión boxing se producen cuando se pasa un tipo de valor a un método que toma <xref:System.Object> como parámetro de entrada. Para obtener más información, vea [Conversión boxing y unboxing](./programming-guide/types/boxing-and-unboxing.md ).

Puede usar la palabra clave [struct](./language-reference/keywords/struct.md) para crear sus propios tipos de valor personalizados. Normalmente, un struct se usa como un contenedor para un pequeño conjunto de variables relacionadas, como se muestra en el ejemplo siguiente:

[!code-csharp[Struct Keyword](../../samples/snippets/csharp/concepts/structs/struct-keyword.cs)]

Para obtener más información sobre los tipos de valor de .NET Framework, vea [Sistema de tipos comunes](../standard/common-type-system.md).

Los structs comparten la mayoría de la sintaxis con las clases, aunque están más limitados que estas:

- Dentro de una declaración de struct, los campos no se pueden inicializar a menos que se declaren como `const` o `static`.

- Un struct no puede declarar un constructor sin parámetros ni un finalizador.

- Los structs se copian en la asignación. Cuando se asigna un struct a una variable nueva, se copian todos los datos y las modificaciones que se realicen en la nueva copia no cambiarán los datos de la copia original. Es importante que lo recuerde al trabajar con colecciones de tipos de valor como Dictionary<string, myStruct>.

- Los structs son tipos de valor y las clases son tipos de referencia.

- A diferencia de las clases, se pueden crear instancias de structs sin usar un operador `new`.

- Los structs pueden declarar constructores que tengan parámetros.

- Así, un struct no puede heredar de otra clase o de otro struct, como tampoco puede ser la base de una clase. Todos los structs heredan directamente de <xref:System.ValueType>, que hereda de <xref:System.Object>.

- Un struct, como una clase, puede implementar interfaces.

## <a name="nullable-value-types"></a>Tipos de valor que aceptan valores NULL

Los tipos de valor normales no pueden tener un valor [null](language-reference/keywords/null.md), pero se pueden crear tipos de valor que aceptan valores NULL mediante la adición de `?` después del tipo. Por ejemplo, `int?` es un tipo `int` que también puede tener el valor [null](./language-reference/keywords/null.md). Los tipos que admiten un valor NULL son instancias del tipo struct genérico <xref:System.Nullable%601>. Los tipos que admiten un valor NULL son especialmente útiles cuando hay un intercambio de datos con bases de datos en las que los valores numéricos podrían ser nulos o no definidos. Para más información, consulte [Tipos que admiten un valor NULL](language-reference/builtin-types/nullable-value-types.md).

## <a name="see-also"></a>Vea también

- [Clases](programming-guide/classes-and-structs/classes.md)
- [Tipos básicos](basic-types.md)
