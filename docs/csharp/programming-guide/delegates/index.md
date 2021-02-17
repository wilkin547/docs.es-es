---
title: 'Delegados: Guía de programación de C#'
description: Un delegado de C# es un tipo que hace referencia a métodos con una lista de parámetros y un tipo de valor devuelto. Los delegados se utilizan para pasar métodos como argumentos a otros métodos.
ms.date: 02/02/2021
helpviewer_keywords:
- C# language, delegates
- delegates [C#]
ms.assetid: 97de039b-c76b-4b9c-a27d-8c1e1c8d93da
ms.openlocfilehash: 0da404146f09028754087c5e24bd05b9289a4220
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100456931"
---
# <a name="delegates-c-programming-guide"></a>Delegados (Guía de programación de C#)

Un [delegado](../../language-reference/builtin-types/reference-types.md) es un tipo que representa referencias a métodos con una lista de parámetros determinada y un tipo de valor devuelto. Cuando se crea una instancia de un delegado, puede asociar su instancia a cualquier método mediante una signatura compatible y un tipo de valor devuelto. Puede invocar (o llamar) al método a través de la instancia del delegado.

Los delegados se utilizan para pasar métodos como argumentos a otros métodos. Los controladores de eventos no son más que métodos que se invocan a través de delegados. Cree un método personalizado y una clase, como un control de Windows, podrá llamar al método cuando se produzca un determinado evento. En el siguiente ejemplo se muestra una declaración de delegado:

[!code-csharp[csProgGuideDelegates#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#20)]

Cualquier método de cualquier clase o struct accesible que coincida con el tipo de delegado se puede asignar al delegado. El método puede ser estático o de instancia. Esta flexibilidad significa que puede cambiar las llamadas de método mediante programación, o bien agregar código nuevo a las clases existentes.

> [!NOTE]
> En el contexto de la sobrecarga de métodos, la signatura de un método no incluye el valor devuelto. Sin embargo, en el contexto de los delegados, la signatura sí lo incluye. En otras palabras, un método debe tener el mismo tipo de valor devuelto que el delegado.

Esta capacidad de hacer referencia a un método como parámetro hace que los delegados sean idóneos para definir métodos de devolución de llamada. Puede escribir un método que compare dos objetos en la aplicación. Ese método se puede usar en un delegado para un algoritmo de ordenación. Como el código de comparación es independiente de la biblioteca, el método de ordenación puede ser más general.

Se han agregado [punteros de función](~/_csharplang/proposals/csharp-9.0/function-pointers.md) a C# 9 para escenarios similares, donde se necesita más control sobre la convención de llamadas. El código asociado a un delegado se invoca mediante un método virtual agregado a un tipo de delegado. Mediante los punteros de función puede especificar otras convenciones.

## <a name="delegates-overview"></a>Información general sobre los delegados

Los delegados tienen las propiedades siguientes:

- Los delegados son similares a los punteros de función de C++, pero los primeros están completamente orientados a objetos y, a diferencia de los punteros de C++ de funciones de miembro, los delegados encapsulan una instancia de objeto y un método.
- Los delegados permiten pasar los métodos como parámetros.
- Los delegados pueden usarse para definir métodos de devolución de llamada.
- Los delegados pueden encadenarse entre sí; por ejemplo, se puede llamar a varios métodos en un solo evento.
- No es necesario que los métodos coincidan exactamente con el tipo de delegado. Para obtener más información, consulte [Usar varianza en delegados](../concepts/covariance-contravariance/using-variance-in-delegates.md).
- Las expresiones lambda son una manera más concisa de escribir bloques de código alineado. En determinados contextos, las expresiones lambda se compilan en tipos de delegado. Para más información sobre las expresiones lambda, consulte [Expresiones lambda](../../language-reference/operators/lambda-expressions.md).

## <a name="in-this-section"></a>En esta sección

- [Utilizar delegados](./using-delegates.md)
- [Cuándo usar delegados en lugar de interfaces (Guía de programación de C#)](/previous-versions/visualstudio/visual-studio-2010/ms173173(v=vs.100))
- [Delegados con métodos con nombre y delegados con métodos anónimos](./delegates-with-named-vs-anonymous-methods.md)
- [Uso de varianza en delegados](../concepts/covariance-contravariance/using-variance-in-delegates.md)
- [Procedimiento para combinar delegados (delegados de multidifusión)](./how-to-combine-delegates-multicast-delegates.md)
- [Procedimiento para declarar un delegado, crear instancias del mismo y usarlo](./how-to-declare-instantiate-and-use-a-delegate.md)

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, vea la sección [Delegados](~/_csharplang/spec/delegates.md) de [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/introduction). La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.

## <a name="featured-book-chapters"></a>Capítulos destacados del libro

- [Delegates, Events, and Lambda Expressions](/previous-versions/visualstudio/visual-studio-2008/ff518994(v=orm.10)) (Delegados, eventos y expresiones lambda) en [C# 3.0 Cookbook, Tercera edición: More than 250 solutions for C# 3.0 programmers](/previous-versions/visualstudio/visual-studio-2008/ff518995(v=orm.10)) (Más de 250 soluciones para programadores de C# 3.0)
- [Delegates and Events](/previous-versions/visualstudio/visual-studio-2008/ff652490(v=orm.10)) (Delegados y eventos) en [Learning C# 3.0: Master the fundamentals of C# 3.0](/previous-versions/visualstudio/visual-studio-2008/ff652493(v=orm.10))

## <a name="see-also"></a>Vea también

- <xref:System.Delegate>
- [Guía de programación de C#](../index.md)
- [Eventos](../events/index.md)
