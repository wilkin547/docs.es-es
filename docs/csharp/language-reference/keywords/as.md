---
title: as (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- as_CSharpKeyword
- as
dev_langs:
- CSharp
helpviewer_keywords:
- type conversion [C#], as keyword
- as keyword [C#]
ms.assetid: a9be126b-cbf4-4990-a70d-d0e1983cad0e
caps.latest.revision: 24
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 7a55c696ac295eee8d5d35ed56038f3c4a90b215
ms.contentlocale: es-es
ms.lasthandoff: 09/25/2017

---
# <a name="as-c-reference"></a>as (Referencia de C#)
Se puede usar el operador `as` para realizar ciertos tipos de conversiones entre tipos de referencia compatibles o [tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/index.md). En el código siguiente se muestra un ejemplo.  
  
 [!code-cs[csrefKeywordsOperator#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_1.cs)]  
  
## <a name="remarks"></a>Comentarios  
 El operador `as` es como una operación de conversión. Pero si la conversión no es posible, `as` devuelve `null` en lugar de generar una excepción. Considere el ejemplo siguiente:  
  
```  
expression as type  
```  
  
 El código es equivalente a la siguiente expresión, salvo que la variable `expression` solo se evalúa una vez.  
  
```  
expression is type ? (type)expression : (type)null  
```  
  
 Tenga en cuenta que el operador `as` realiza solo las conversiones de referencia, las conversiones que aceptan valores NULL y las conversiones boxing. El operador `as` no puede realizar otras conversiones, como las conversiones definidas por el usuario, que en su lugar se deben realizar mediante expresiones de conversión.  
  
## <a name="example"></a>Ejemplo  
 [!code-cs[csrefKeywordsOperator#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_2.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [is](../../../csharp/language-reference/keywords/is.md)   
 [Operador ?](../../../csharp/language-reference/operators/conditional-operator.md)   
 [Palabras clave de operador](../../../csharp/language-reference/keywords/operator-keywords.md)

