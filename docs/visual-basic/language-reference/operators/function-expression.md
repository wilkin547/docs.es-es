---
title: "Expresión (Visual Basic) de la función | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Function expression [Visual Basic]
- functions [Visual Basic], function expressions
- lambda expressions [Visual Basic], function expression
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
caps.latest.revision: 18
author: stevehoag
ms.author: shoag
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9b181b18a28a8b92a392fffdc10e08690d54f545
ms.lasthandoff: 03/13/2017

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
|`parameterlist`|Opcional. Una lista de nombres de variables locales que representan los parámetros de este procedimiento. Los paréntesis deben estar presentes aunque la lista está vacía. Consulte [lista de parámetros](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`expression`|Obligatorio. Una expresión única. El tipo de la expresión es el tipo de valor devuelto de la función.|  
|`statements`|Obligatorio. Una lista de instrucciones que devuelve un valor mediante la `Return` instrucción. (Consulte [Return (instrucción)](../../../visual-basic/language-reference/statements/return-statement.md).) El tipo de valor devuelto es el tipo de valor devuelto de la función.|  
  
## <a name="remarks"></a>Comentarios  
 Un *expresión lambda* es una función sin nombre que se calcula y devuelve un valor. Puede usar una expresión lambda en cualquier lugar puede utilizar un tipo de delegado, salvo como argumento a `RemoveHandler`. Para obtener más información sobre los delegados y el uso de expresiones lambda con delegados, vea [instrucción Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md) y [la conversión de delegado no estricta](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).  
  
## <a name="lambda-expression-syntax"></a>Sintaxis de la expresión lambda  
 La sintaxis de una expresión lambda es similar al de una función estándar. Las diferencias son:  
  
-   Una expresión lambda no tiene un nombre.  
  
-   Las expresiones lambda no pueden tener modificadores, como `Overloads` o `Overrides`.  
  
-   Las expresiones lambda no utilizan una `As` cláusula para designar el tipo de valor devuelto de la función. En su lugar, el tipo se deduce del valor que se evalúa como el cuerpo de una expresión lambda de línea o el valor devuelto de una expresión lambda de varias líneas. Por ejemplo, si el cuerpo de una expresión lambda de una línea es `Where cust.City = "London"`, su tipo de valor devuelto es `Boolean`.  
  
-   El cuerpo de una expresión lambda de línea debe ser una expresión, no una instrucción. El cuerpo puede constar de una llamada a un procedimiento de función, pero no es una llamada a un procedimiento sub.  
  
-   Deben haber especificado todos los parámetros deben deducir los tipos de datos o todos.  
  
-   No se permiten parámetros Optional y Paramarray.  
  
-   No se permiten parámetros genéricos.  
  
## <a name="example"></a>Ejemplo  
 Los ejemplos siguientes muestran dos maneras de crear expresiones lambda simples. La primera utiliza un `Dim` para proporcionar un nombre para la función. Para llamar a la función, enviar un valor para el parámetro.  
  
 [!code-vb[1 VbVbalrLambdas](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_1.vb)]  
  
 [!code-vb[VbVbalrLambdas&#2;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_2.vb)]  
  
## <a name="example"></a>Ejemplo  
 Como alternativa, puede declarar y ejecutar la función al mismo tiempo.  
  
 [!code-vb[VbVbalrLambdas&3;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_3.vb)]  
  
## <a name="example"></a>Ejemplo  
 Siguiente es un ejemplo de una expresión lambda que incrementa su argumento y devuelve el valor. El ejemplo muestra la sintaxis de expresiones lambda de línea y multilínea para una función. Para obtener más ejemplos, vea [expresiones Lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbVbalrLambdas&#14;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_4.vb)]  
  
## <a name="example"></a>Ejemplo  
 Las expresiones lambda subyacen a muchos de los operadores de consulta en [!INCLUDE[vbteclinqext](../../../csharp/getting-started/includes/vbteclinqext_md.md)]y pueden utilizar explícitamente en consultas basadas en métodos. En el ejemplo siguiente se muestra una típica [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)] consulta, seguido de la traducción de la consulta al formato de método.  
  
```vb  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 Para obtener más información acerca de los métodos de consulta, vea [consultas](../../../visual-basic/language-reference/queries/queries.md). Para obtener más información acerca de los operadores de consulta estándar, vea [información general sobre operadores de consulta estándar](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).  
  
## <a name="see-also"></a>Vea también  
 [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Expresiones lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)   
 [Operadores y expresiones](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)   
 [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)   
 [Comparaciones de valores](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)   
 [Expresiones booleanas](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)   
 [Si (operador)](../../../visual-basic/language-reference/operators/if-operator.md)   
 [Conversión de delegado flexible](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
