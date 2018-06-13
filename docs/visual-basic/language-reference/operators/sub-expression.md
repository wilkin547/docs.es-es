---
title: Subexpresión (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic], sub expression
- Sub Expression [Visual Basic]
- subroutines [Visual Basic], sub expressions
ms.assetid: 36b6bfd1-6539-4d8f-a5eb-6541a745ffde
ms.openlocfilehash: 602212e664fa3362742fb1ba0dc033610272d3af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603540"
---
# <a name="sub-expression-visual-basic"></a>Subexpresión (Visual Basic)
Declara los parámetros y el código que definen una expresión lambda de subrutina.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Sub ( [ parameterlist ] ) statement  
- or -  
Sub ( [ parameterlist ] )  
  [ statements ]  
End Sub  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`parameterlist`|Opcional. Una lista de nombres de variables locales que representan los parámetros del procedimiento. Los paréntesis deben estar presentes incluso cuando la lista está vacía. Para obtener más información, consulte [lista de parámetros](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`statement`|Requerido. Una sola instrucción.|  
|`statements`|Requerido. Una lista de instrucciones.|  
  
## <a name="remarks"></a>Comentarios  
 A *expresión lambda* es una subrutina que no tiene un nombre y que ejecuta una o varias instrucciones. Puede usar una expresión lambda en cualquier lugar que puede usar un tipo de delegado, salvo como argumento a `RemoveHandler`. Para obtener más información sobre los delegados y el uso de expresiones lambda con delegados, vea [instrucción Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md) y [conversión de delegado flexible](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).  
  
## <a name="lambda-expression-syntax"></a>Sintaxis de la expresión lambda  
 La sintaxis de una expresión lambda es similar a la de una subrutina estándar. Las diferencias son los siguientes:  
  
-   Una expresión lambda no tiene un nombre.  
  
-   Una expresión lambda no puede tener un modificador, como `Overloads` o `Overrides`.  
  
-   El cuerpo de una expresión lambda de línea debe ser una instrucción, no una expresión. El cuerpo puede constar de una llamada a un procedimiento sub, pero no es una llamada a un procedimiento de función.  
  
-   En una expresión lambda, deben haber especificado todos los parámetros deben deducirse todos los parámetros o tipos de datos.  
  
-   Opcional y `ParamArray` parámetros no se permiten en las expresiones lambda.  
  
-   Parámetros genéricos no se permiten en las expresiones lambda.  
  
## <a name="example"></a>Ejemplo  
 Aquí te mostramos un ejemplo de una expresión lambda que escribe un valor en la consola. En el ejemplo se muestra la sintaxis de expresiones lambda de varias líneas y de línea de una subrutina. Para obtener más ejemplos, vea [expresiones Lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbVbalrLambdas#15](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/sub-expression_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Expresiones lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [Operadores y expresiones](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)  
 [Conversión de delegado flexible](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
