---
title: typeof (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- typeof
- typeof_CSharpKeyword
helpviewer_keywords:
- typeof keyword [C#]
ms.assetid: 0c08d880-515e-46bb-8cd2-48b8dd62c08d
ms.openlocfilehash: 039294d17d25d1d8775e7f92f46f5f57f2ac3212
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53146685"
---
# <a name="typeof-c-reference"></a>typeof (Referencia de C#)

Se usa para obtener el objeto `System.Type` de un tipo. Una expresión `typeof` tiene el formato siguiente:

```csharp
System.Type type = typeof(int);
```

## <a name="remarks"></a>Comentarios

Para obtener el tipo en tiempo de ejecución de una expresión, puede usar el método <xref:System.Object.GetType%2A> de .NET Framework, como en el ejemplo siguiente:

```csharp
int i = 0;
System.Type type = i.GetType();
```

El operador `typeof` no se puede sobrecargar.

El operador `typeof` también puede usarse en tipos genéricos abiertos. Los tipos con más de un parámetro de tipo deben incluir el número correspondiente de comas en la especificación. En el ejemplo siguiente se muestra cómo determinar si el tipo de valor devuelto de un método es un <xref:System.Collections.Generic.IEnumerable%601> genérico. <xref:System.Type.GetInterface%2A?displayProperty=nameWithType> devolverá `null` si el tipo de valor devuelto no es un tipo genérico <xref:System.Collections.Generic.IEnumerable%601>.

[!code-csharp[typeof_3.cs](~/samples/snippets/csharp/keywords/typeof/typeof_3.cs)]

## <a name="example"></a>Ejemplo

[!code-csharp[csrefKeywordsOperator#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#12)] 

## <a name="example"></a>Ejemplo

En este ejemplo se usa el método <xref:System.Object.GetType%2A> para determinar el tipo que se usa para contener el resultado de un cálculo numérico. Esto varía en función de los requisitos de almacenamiento del número resultante.

[!code-csharp[csrefKeywordsOperator#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#13)]

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, vea la sección [El operador typeof](~/_csharplang/spec/expressions.md#the-typeof-operator) de la [Especificación del lenguaje C#](../language-specification/index.md). La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.

## <a name="see-also"></a>Vea también

- <xref:System.Type?displayProperty=nameWithType>
- [Referencia de C#](../../../csharp/language-reference/index.md)
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)
- [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)
- [is](../../../csharp/language-reference/keywords/is.md)
- [Palabras clave de operador](../../../csharp/language-reference/keywords/operator-keywords.md)