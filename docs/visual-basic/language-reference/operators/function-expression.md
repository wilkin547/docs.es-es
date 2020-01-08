---
title: Expresión Function
ms.date: 07/20/2015
helpviewer_keywords:
- Function expression [Visual Basic]
- functions [Visual Basic], function expressions
- lambda expressions [Visual Basic], function expression
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
ms.openlocfilehash: 454c4e3d926640934a8edc4fcb16e4308a89dd50
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2020
ms.locfileid: "75632342"
---
# <a name="function-expression-visual-basic"></a>Expresión de función (Visual Basic)
Declara los parámetros y el código que definen una expresión lambda de función.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Function ( [ parameterlist ] ) expression  
- or -  
Function ( [ parameterlist ] )  
  [ statements ]  
End Function  
```  
  
## <a name="parts"></a>Componentes de  
  
|Término|de esquema JSON|  
|---|---|  
|`parameterlist`|Opcional. Una lista de nombres de variables locales que representan los parámetros de este procedimiento. Los paréntesis deben estar presentes incluso cuando la lista esté vacía. Vea [lista de parámetros](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`expression`|Obligatoria. Expresión única. El tipo de la expresión es el tipo de valor devuelto de la función.|  
|`statements`|Obligatoria. Una lista de instrucciones que devuelven un valor mediante la instrucción `Return`. (Consulte la [instrucción return](../../../visual-basic/language-reference/statements/return-statement.md)). El tipo del valor devuelto es el tipo de valor devuelto de la función.|  
  
## <a name="remarks"></a>Notas  
 Una *expresión lambda* es una función sin un nombre que calcula y devuelve un valor. Puede usar una expresión lambda en cualquier lugar en el que pueda usar un tipo de delegado, excepto como argumento para `RemoveHandler`. Para obtener más información sobre los delegados y el uso de expresiones lambda con delegados, vea [instrucción Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md) y [conversión de delegado relajado](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).  
  
## <a name="lambda-expression-syntax"></a>Sintaxis de la expresión lambda  
 La sintaxis de una expresión lambda es similar a la de una función estándar. Las diferencias son las siguientes:  
  
- Una expresión lambda no tiene un nombre.  
  
- Las expresiones lambda no pueden tener modificadores, como `Overloads` o `Overrides`.  
  
- Las expresiones lambda no usan una cláusula `As` para designar el tipo de valor devuelto de la función. En su lugar, el tipo se deduce del valor que el cuerpo de una expresión lambda de una sola línea evalúa como, o el valor devuelto de una expresión lambda de varias líneas. Por ejemplo, si el cuerpo de una expresión lambda de una sola línea es `Where cust.City = "London"`, su tipo de valor devuelto es `Boolean`.  
  
- El cuerpo de una expresión lambda de una sola línea debe ser una expresión, no una instrucción. El cuerpo puede constar de una llamada a un procedimiento de función, pero no una llamada a un procedimiento Sub.  
  
- Todos los parámetros deben tener tipos de datos especificados o todos deben ser inferidos.  
  
- No se permiten parámetros opcionales y ParamArray.  
  
- No se permiten parámetros genéricos.  
  
## <a name="example"></a>Ejemplo  
 En los ejemplos siguientes se muestran dos maneras de crear expresiones lambda simples. El primero usa un `Dim` para proporcionar un nombre para la función. Para llamar a la función, envíe un valor para el parámetro.  
  
 [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
 [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
## <a name="example"></a>Ejemplo  
 Como alternativa, puede declarar y ejecutar la función al mismo tiempo.  
  
 [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
## <a name="example"></a>Ejemplo  
 A continuación se muestra un ejemplo de una expresión lambda que incrementa su argumento y devuelve el valor. En el ejemplo se muestra la sintaxis de la expresión lambda de una sola línea y de varias líneas para una función. Para obtener más ejemplos, consulte [expresiones lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]  
  
## <a name="example"></a>Ejemplo  
 Las expresiones lambda subyacen a muchos de los operadores de consulta en Language-Integrated Query (LINQ) y se pueden usar explícitamente en las consultas basadas en métodos. En el ejemplo siguiente se muestra una consulta LINQ típica, seguida de la conversión de la consulta en formato de método.  
  
```vb  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 Para obtener más información sobre los métodos de consulta, vea [consultas](../../../visual-basic/language-reference/queries/index.md). Para obtener más información acerca de los operadores de consulta estándar, vea [información general sobre operadores de consulta estándar](../../programming-guide/concepts/linq/standard-query-operators-overview.md).  
  
## <a name="see-also"></a>Vea también

- [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)
- [Expresiones lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [Operadores y expresiones](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)
- [Comparaciones de valores](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [Expresiones booleanas](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [If (operador)](../../../visual-basic/language-reference/operators/if-operator.md)
- [Conversión de delegado flexible](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
