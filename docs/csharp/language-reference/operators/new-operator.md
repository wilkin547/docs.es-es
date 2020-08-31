---
description: 'Operador new: referencia de C#'
title: 'Operador new: referencia de C#'
ms.date: 06/25/2019
f1_keywords:
- new_CSharpKeyword
helpviewer_keywords:
- new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
ms.openlocfilehash: 88ec929317d4e6c6651233c1a1aa0ce8a8cce611
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89118278"
---
# <a name="new-operator-c-reference"></a>Operador new (referencia de C#)

El operador `new` crea una nueva instancia de un tipo.

También puede usar la palabra clave `new` como un [modificador de declaración de miembro](../keywords/new-modifier.md) o una [restricción de tipo genérico](../keywords/new-constraint.md).

## <a name="constructor-invocation"></a>Invocación del constructor

Para crear una nueva instancia de un tipo, normalmente se invoca uno de los [constructores](../../programming-guide/classes-and-structs/constructors.md) de ese tipo mediante el operador `new`:

[!code-csharp-interactive[invoke constructor](snippets/shared/NewOperator.cs#Constructor)]

Puede usar un [inicializador de colección u objeto](../../programming-guide/classes-and-structs/object-and-collection-initializers.md) con el operador`new` para crear una instancia e inicializar un objeto en una sola instrucción, como se muestra en el ejemplo siguiente:

[!code-csharp-interactive[constructor with initializer](snippets/shared/NewOperator.cs#ConstructorWithInitializer)]

## <a name="array-creation"></a>creación de matriz

También se usa el operador `new` para crear una instancia de matriz, como se muestra en el ejemplo siguiente:

[!code-csharp-interactive[create array](snippets/shared/NewOperator.cs#Array)]

Utilice la sintaxis de inicialización de matriz para crear una instancia de matriz y rellenarla con los elementos en una sola instrucción. En el ejemplo siguiente se muestran varias maneras de hacerlo:

[!code-csharp-interactive[initialize array](snippets/shared/NewOperator.cs#ArrayInitialization)]

Para obtener más información sobre las matrices, consulte [Matrices](../../programming-guide/arrays/index.md).

## <a name="instantiation-of-anonymous-types"></a>Creación de instancias de tipos anónimos

Para crear una instancia de un [tipo anónimo](../../programming-guide/classes-and-structs/anonymous-types.md), utilice el operador `new` y la sintaxis de inicializador de objeto:

[!code-csharp-interactive[anonymous type](snippets/shared/NewOperator.cs#AnonymousType)]

## <a name="destruction-of-type-instances"></a>Destrucción de instancias de tipo

No tiene que destruir instancias de tipo creadas anteriormente. Las instancias de tipos de valor y referencia se destruyen automáticamente. Las instancias de tipos de valor se destruyen en cuanto se destruye el contexto que los contiene. Las instancias de tipos de referencia los destruye el [recolector de elementos no utilizados](../../../standard/garbage-collection/index.md) en un momento no especificado después de eliminarse la última referencia a ellos.

Para los tipos de instancia que contienen recursos no administrados, como un identificador de archivo, se recomienda realizar una limpieza determinista para asegurarse de que los recursos que contienen se liberan tan pronto como sea posible. Para más información, vea la referencia de la API <xref:System.IDisposable?displayProperty=nameWithType> y el artículo sobre la [instrucción using](../keywords/using-statement.md).

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

Un tipo definido por el usuario no puede sobrecargar el operador `new`.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, vea la sección [El operador new](~/_csharplang/spec/expressions.md#the-new-operator) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Operadores y expresiones de C#](index.md)
- [Inicializadores de objeto y colección](../../programming-guide/classes-and-structs/object-and-collection-initializers.md)
