---
title: 'dynamic: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- dynamic_CSharpKeyword
helpviewer_keywords:
- dynamic [C#]
- dynamic keyword [C#]
ms.assetid: 9e797102-cc83-4964-bf58-afe4f54d16bc
ms.openlocfilehash: c8748f1869e8e2d5246910fac0100a6c70790579
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/21/2019
ms.locfileid: "67306646"
---
# <a name="dynamic-c-reference"></a>dynamic (Referencia de C#)

El tipo `dynamic` permite que las operaciones en las que se produce omitan la comprobación de tipo en tiempo de compilación. En su lugar, se resuelven estas operaciones en tiempo de ejecución. El tipo `dynamic` simplifica el acceso a las API de COM como las API de automatización de Office y también a API dinámicas como las bibliotecas de IronPython, y a Document Object Model (DOM) HTML.

El tipo `dynamic` se comporta como el tipo `object` en la mayoría de las circunstancias. En cambio, el compilador no resuelve o no comprueba el tipo de las operaciones que contienen expresiones de tipo `dynamic`. El compilador empaqueta información sobre la operación y esa información se usa después para evaluar la operación en tiempo de ejecución. Como parte del proceso, las variables de tipo `dynamic` están compiladas en las variables de tipo `object`. Por consiguiente, el tipo `dynamic` solo existe en tiempo de compilación, no en tiempo de ejecución.

En el siguiente ejemplo se contrasta una variable de tipo `dynamic` con una variable de tipo `object`. Para comprobar el tipo de cada variable en tiempo de compilación, coloque el puntero del mouse sobre `dyn` u `obj` en las instrucciones `WriteLine`. IntelliSense muestra **dynamic** para `dyn` y **object** para `obj`.

[!code-csharp[csrefKeywordsTypes#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic1.cs#21)]

Las instrucciones `WriteLine` muestran los tipos en tiempo de ejecución de `dyn` y `obj`. En ese punto, ambos tienen el mismo tipo, entero. Se produce el siguiente resultado:

`System.Int32`

`System.Int32`

Para ver la diferencia entre `dyn` y `obj` en tiempo de compilación, agregue las dos líneas siguientes entre las declaraciones y las instrucciones `WriteLine` en el ejemplo anterior.

```csharp
dyn = dyn + 3;
obj = obj + 3;
```

 Un error del compilador se notifica para el intento de suma de un entero y un objeto en la expresión `obj + 3`. En cambio, no se notifica ningún error para `dyn + 3`. En tiempo de compilación no se comprueba la expresión que contiene `dyn` porque el tipo de `dyn` es `dynamic`.

## <a name="context"></a>Contexto

La palabra clave `dynamic` puede aparecer directamente o como un componente de un tipo construido en las siguientes situaciones:

- En declaraciones, como el tipo de una propiedad, un campo, un indexador, un parámetro, un valor devuelto, una variable local o una restricción de tipo. La siguiente definición de clase usa `dynamic` en varias declaraciones diferentes.

    [!code-csharp[csrefKeywordsTypes#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic1.cs#22)]

- En conversiones de tipos explícitas, como el tipo de destino de una conversión.

    [!code-csharp[csrefKeywordsTypes#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic1.cs#23)]

- En cualquier contexto donde los tipos actúen como valores, por ejemplo, en el lado derecho de un operador `is` o un operador `as`, o como argumento de `typeof` como parte de un tipo construido. Por ejemplo, se puede usar `dynamic` en las siguientes expresiones.

    [!code-csharp[csrefKeywordsTypes#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic1.cs#24)]

## <a name="example"></a>Ejemplo

El ejemplo siguiente usa `dynamic` en varias declaraciones. El método `Main` también contrasta la comprobación de tipo en tiempo de compilación con la comprobación de tipo en tiempo de ejecución.

[!code-csharp[csrefKeywordsTypes#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic2.cs#25)]

Para obtener más información y ejemplos, vea [Uso de tipo dinámico (Guía de programación de C#)](../../../csharp/programming-guide/types/using-type-dynamic.md).

## <a name="see-also"></a>Vea también

- <xref:System.Dynamic.ExpandoObject?displayProperty=nameWithType>
- <xref:System.Dynamic.DynamicObject?displayProperty=nameWithType>
- [Uso de tipo dinámico](../../programming-guide/types/using-type-dynamic.md)
- [object](object.md)
- [is](../operators/type-testing-and-conversion-operators.md#is-operator)
- [as](../operators/type-testing-and-conversion-operators.md#as-operator)
- [typeof](../operators/type-testing-and-conversion-operators.md#typeof-operator)
- [Cómo: Convertir de forma segura mediante la coincidencia de patrones y los operadores is y as](../../how-to/safely-cast-using-pattern-matching-is-and-as-operators.md)
- [Tutorial: Crear y usar objetos dinámicos (C# y Visual Basic)](../../programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)
