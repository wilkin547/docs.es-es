---
title: 'as: Referencia de C#'
ms.custom: seodec18
ms.date: 10/11/2018
f1_keywords:
- as_CSharpKeyword
- as
helpviewer_keywords:
- type conversion [C#], as keyword
- as keyword [C#]
ms.assetid: a9be126b-cbf4-4990-a70d-d0e1983cad0e
ms.openlocfilehash: 7559c24151a3c9acc79c0554112c923a23a88564
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244354"
---
# <a name="as-c-reference"></a>as (Referencia de C#)
Se puede usar el operador `as` para realizar ciertos tipos de conversiones entre tipos de referencia compatibles o [tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/index.md). En el código siguiente se muestra un ejemplo.  
  
[!code-csharp[csrefKeywordsOperator#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#1)]

Como se muestra en el ejemplo, se necesita comparar el resultado de la expresión `as` con `null` para comprobar si una conversión es correcta. A partir C# 7.0, puede usar la expresión [is](is.md) para tanto para probar que una conversión se realiza correctamente, como para asignar condicionalmente una variable cuando la conversión se realiza correctamente. En muchos escenarios, es más conciso que el uso del operador `as`. Para más información, consulte sección [Patrón de tipo](is.md#type)del artículo de [`is` (operador)](is.md).
  
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

Para obtener más información, vea la sección [El operador as](~/_csharplang/spec/expressions.md#the-as-operator) de la [Especificación del lenguaje C#](../language-specification/index.md). La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.
 
## <a name="see-also"></a>Vea también  
- [Referencia de C#](../../../csharp/language-reference/index.md)  
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)  
- [is](../../../csharp/language-reference/keywords/is.md)  
- [?: !](../../../csharp/language-reference/operators/conditional-operator.md)  
- [Palabras clave de operador](../../../csharp/language-reference/keywords/operator-keywords.md)
