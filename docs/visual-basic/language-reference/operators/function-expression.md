---
title: Expresión de función (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Function expression [Visual Basic]
- functions [Visual Basic], function expressions
- lambda expressions [Visual Basic], function expression
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
ms.openlocfilehash: 29bf95a336b6f6ed5c9c310c9ea7575a91089361
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604892"
---
# <a name="function-expression-visual-basic"></a>Expresión de función (Visual Basic)
Declara los parámetros y el código que definen una expresión lambda de función.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Function ( [ parameterlist ] ) expression  
- or -  
Function ( [ parameterlist ] )  
  [ statements ]  
End Function  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`parameterlist`|Opcional. Una lista de nombres de variables locales que representan los parámetros de este procedimiento. Los paréntesis deben estar presentes incluso cuando la lista está vacía. Vea [lista de parámetros](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`expression`|Requerido. Una sola expresión. El tipo de la expresión es el tipo de valor devuelto de la función.|  
|`statements`|Requerido. Una lista de instrucciones que devuelve un valor mediante la `Return` instrucción. (Consulte [Return (instrucción)](../../../visual-basic/language-reference/statements/return-statement.md).) El tipo de valor devuelto es el tipo de valor devuelto de la función.|  
  
## <a name="remarks"></a>Comentarios  
 A *expresión lambda* es una función sin un nombre que calcule y devuelva un valor. Puede usar una expresión lambda en cualquier lugar puede utilizar un tipo de delegado, excepto como argumento a `RemoveHandler`. Para obtener más información sobre los delegados y el uso de expresiones lambda con delegados, vea [instrucción Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md) y [conversión de delegado flexible](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).  
  
## <a name="lambda-expression-syntax"></a>Sintaxis de la expresión lambda  
 La sintaxis de una expresión lambda es similar a la de una función estándar. Las diferencias son los siguientes:  
  
-   Una expresión lambda no tiene un nombre.  
  
-   Las expresiones lambda no pueden tener modificadores, como `Overloads` o `Overrides`.  
  
-   Las expresiones lambda no utilizan una `As` cláusula para designar el tipo de valor devuelto de la función. En su lugar, el tipo se deduce del valor que se evalúa como el cuerpo de una expresión lambda de línea o el valor devuelto de una expresión lambda de varias líneas. Por ejemplo, si el cuerpo de una expresión lambda de línea `Where cust.City = "London"`, su tipo de valor devuelto es `Boolean`.  
  
-   El cuerpo de una expresión lambda de línea debe ser una expresión, no una instrucción. El cuerpo puede constar de una llamada a un procedimiento de función, pero no es una llamada a un procedimiento sub.  
  
-   Deben haber especificado todos los parámetros deben deducir los tipos de datos o todos.  
  
-   No se permiten parámetros Optional y Paramarray.  
  
-   No se permiten parámetros genéricos.  
  
## <a name="example"></a>Ejemplo  
 Los ejemplos siguientes muestran dos maneras de crear expresiones lambda simples. El primer ejemplo usa un `Dim` para proporcionar un nombre para la función. Para llamar a la función, enviar un valor para el parámetro.  
  
 [!code-vb[VbVbalrLambdas#1](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_1.vb)]  
  
 [!code-vb[VbVbalrLambdas#2](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_2.vb)]  
  
## <a name="example"></a>Ejemplo  
 Como alternativa, puede declarar y ejecutar la función a la vez.  
  
 [!code-vb[VbVbalrLambdas#3](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_3.vb)]  
  
## <a name="example"></a>Ejemplo  
 Aquí te mostramos un ejemplo de una expresión lambda que incrementa su argumento y devuelve el valor. En el ejemplo se muestra la sintaxis de expresiones lambda de varias líneas y de línea para una función. Para obtener más ejemplos, vea [expresiones Lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbVbalrLambdas#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_4.vb)]  
  
## <a name="example"></a>Ejemplo  
 Las expresiones lambda subyacen a muchos de los operadores de consulta en [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]y puede utilizarse de forma explícita en consultas basadas en métodos. En el ejemplo siguiente se muestra una típica [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] consulta, seguido por la traducción de la consulta en formato de método.  
  
```vb  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 Para obtener más información acerca de los métodos de consulta, vea [consultas](../../../visual-basic/language-reference/queries/queries.md). Para obtener más información acerca de los operadores de consulta estándar, vea [información general sobre operadores de consulta estándar](../../programming-guide/concepts/linq/standard-query-operators-overview.md).  
  
## <a name="see-also"></a>Vea también  
 [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Expresiones lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [Operadores y expresiones](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)  
 [Comparaciones de valores](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [Expresiones booleanas](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)  
 [If (operador)](../../../visual-basic/language-reference/operators/if-operator.md)  
 [Conversión de delegado flexible](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
