---
title: 'Operador ?: (Referencia de C#)'
ms.date: 07/20/2015
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: 150149453a67d8e5319461266865cb25be180347
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43506437"
---
# <a name="-operator-c-reference"></a>Operador ?: (Referencia de C#)
El operador condicional (`?:`), normalmente conocido como un operador condicional ternario, devuelve uno de dos valores según el valor de una expresión booleana. A continuación se muestra la sintaxis del operador condicional.  
  
```  
condition ? first_expression : second_expression;  
```  
  
## <a name="remarks"></a>Comentarios  
 `condition` debe evaluarse como `true` o `false`. Si `condition` es `true`, `first_expression` se evalúa y se convierte en el resultado. Si `condition` es `false`, `second_expression` se evalúa y se convierte en el resultado. Solo se evalúa una de las dos expresiones.  
  
 Tanto el tipo de `first_expression` como el de `second_expression` deben coincidir, o bien debe existir una conversión implícita de un tipo al otro.  
  
 Puede expresar cálculos que, de lo contrario, podrían requerir una construcción `if-else` más concisa mediante el operador condicional. Por ejemplo, el código siguiente usa primero una instrucción `if` y después un operador condicional para clasificar un entero como positivo o negativo.  
  
```csharp
int input = Convert.ToInt32(Console.ReadLine());  
string classify;  
  
// if-else construction.  
if (input > 0)  
    classify = "positive";  
else  
    classify = "negative";  
  
// ?: conditional operator.  
classify = (input > 0) ? "positive" : "negative";  
```  
  
 El operador condicional es asociativo a la derecha. La expresión `a ? b : c ? d : e` se evalúa como `a ? b : (c ? d : e)`, no como `(a ? b : c) ? d : e`.  
  
 El operador condicional no se puede sobrecargar.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csRefOperators#41](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-operator_1.cs)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../../../csharp/language-reference/index.md)  
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Operadores de C#](../../../csharp/language-reference/operators/index.md)  
- [if-else](../../../csharp/language-reference/keywords/if-else.md)  
- [Operadores ?. y ?[]](../../../csharp/language-reference/operators/null-conditional-operators.md)  
- [Operador !](../../../csharp/language-reference/operators/null-coalescing-operator.md)
