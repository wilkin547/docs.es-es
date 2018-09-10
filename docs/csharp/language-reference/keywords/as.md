---
title: as (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- as_CSharpKeyword
- as
helpviewer_keywords:
- type conversion [C#], as keyword
- as keyword [C#]
ms.assetid: a9be126b-cbf4-4990-a70d-d0e1983cad0e
ms.openlocfilehash: aee80b3262ccd9432d7c311dddec47185b66d05f
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44098876"
---
# <a name="as-c-reference"></a>as (Referencia de C#)
Se puede usar el operador `as` para realizar ciertos tipos de conversiones entre tipos de referencia compatibles o [tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/index.md). En el código siguiente se muestra un ejemplo.  
  
[!code-csharp[csrefKeywordsOperator#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#1)]
  
## <a name="remarks"></a>Comentarios  
 El operador `as` es como una operación de conversión. Pero si la conversión no es posible, `as` devuelve `null` en lugar de generar una excepción. Considere el ejemplo siguiente:  
  
```csharp  
expression as type  
```  
  
 El código es equivalente a la siguiente expresión, salvo que la variable `expression` solo se evalúa una vez.  
  
```csharp  
expression is type ? (type)expression : (type)null  
```  
  
 Tenga en cuenta que el operador `as` realiza solo las conversiones de referencia, las conversiones que aceptan valores NULL y las conversiones boxing. El operador `as` no puede realizar otras conversiones, como las conversiones definidas por el usuario, que en su lugar se deben realizar mediante expresiones de conversión.  
  
## <a name="example"></a>Ejemplo  

[!code-csharp[csrefKeywordsOperator#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#2)]
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
- [Referencia de C#](../../../csharp/language-reference/index.md)  
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)  
- [is](../../../csharp/language-reference/keywords/is.md)  
- [Operador ?](../../../csharp/language-reference/operators/conditional-operator.md)  
- [Palabras clave de operador](../../../csharp/language-reference/keywords/operator-keywords.md)
