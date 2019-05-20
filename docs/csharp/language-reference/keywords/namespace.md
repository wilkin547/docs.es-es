---
title: 'Palabra clave namespace: Referencia de C#'
ms.custom: seoapril2019
ms.date: 07/20/2015
f1_keywords:
- namespace_CSharpKeyword
- namespace
helpviewer_keywords:
- namespace keyword [C#]
- scope [C#]
ms.assetid: 0a788423-9110-42e0-97d9-bda41ca4870f
ms.openlocfilehash: f938e49267faad8aebbf4c22fc921f305d160123
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633435"
---
# <a name="namespace-c-reference"></a>espacio de nombres (Referencia de C#)

La palabra clave `namespace` se usa para declarar un ámbito que contiene un conjunto de objetos relacionados. Puede usar un espacio de nombres para organizar los elementos de código y crear tipos únicos globales.

[!code-csharp[csrefKeywordsNamespace#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#1)]

## <a name="remarks"></a>Comentarios

En un espacio de nombres, se pueden declarar cero o más de los siguientes tipos:

- otro espacio de nombres

- [class](class.md)

- [interface](interface.md)

- [struct](struct.md)

- [enum](enum.md)

- [delegate](delegate.md)

Tanto si se declara explícitamente un espacio de nombres en un archivo de código fuente de C# como si no, el compilador agrega un espacio de nombres predeterminado. Este espacio de nombres sin nombre, que a veces se denomina espacio de nombres global, está presente en todos los archivos. Todos los identificadores del espacio de nombres global están disponibles para su uso en un espacio de nombres con nombre.

Los espacios de nombres tienen implícitamente acceso público y esto no se puede modificar. Para ver una descripción de los modificadores de acceso que se pueden asignar a los elementos de un espacio de nombres, vea [Modificadores de acceso](access-modifiers.md).

Es posible definir un espacio de nombres en dos o más declaraciones. Por ejemplo, en el ejemplo siguiente se definen dos clases como parte del espacio de nombres `MyCompany`:

[!code-csharp[csrefKeywordsNamespace#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#2)]

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo llamar a un método estático en un espacio de nombres anidado.

[!code-csharp[csrefKeywordsNamespace#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#3)]

## <a name="related-resources"></a>Recursos relacionados

Para obtener más información sobre el uso de los espacios de nombres, vea los temas siguientes:

- [Espacios de nombres](../../programming-guide/namespaces/index.md)

- [Utilizar espacios de nombres](../../programming-guide/namespaces/using-namespaces.md)

- [Cómo: Utilizar el alias del espacio de nombres global](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)

## <a name="c-language-specification"></a>Especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../../language-reference/index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [Palabras clave del espacio de nombres](namespace-keywords.md)
- [using](using-directive.md)
- [using static](using-static.md)
