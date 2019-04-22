---
title: Subexpresión (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic], sub expression
- Sub Expression [Visual Basic]
- subroutines [Visual Basic], sub expressions
ms.assetid: 36b6bfd1-6539-4d8f-a5eb-6541a745ffde
ms.openlocfilehash: 5b26a091dc8eb7415702c3c2853a569324def7d5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58824616"
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
|`parameterlist`|Opcional. Una lista de nombres de variables locales que representan los parámetros del procedimiento. Los paréntesis deben estar presentes incluso cuando la lista está vacía. Para obtener más información, consulta [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`statement`|Obligatorio. Una sola instrucción.|  
|`statements`|Obligatorio. Una lista de instrucciones.|  
  
## <a name="remarks"></a>Comentarios  
 Un *expresión lambda* es una subrutina que no tiene un nombre y que ejecuta una o varias instrucciones. Puede usar una expresión lambda en cualquier lugar que puede usar un tipo de delegado, excepto como argumento a `RemoveHandler`. Para obtener más información sobre los delegados y el uso de expresiones lambda con delegados, vea [instrucción Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md) y [conversión de delegado flexible](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).  
  
## <a name="lambda-expression-syntax"></a>Sintaxis de la expresión lambda  
 La sintaxis de una expresión lambda es similar al de una subrutina estándar. Las diferencias son como sigue:  
  
-   Una expresión lambda no tiene un nombre.  
  
-   Una expresión lambda no puede tener un modificador, como `Overloads` o `Overrides`.  
  
-   El cuerpo de una expresión lambda de línea debe ser una instrucción, no una expresión. El cuerpo puede constar de una llamada a un procedimiento sub, pero no es una llamada a un procedimiento function.  
  
-   En una expresión lambda, deben haber especificado todos los parámetros deben deducir los tipos de datos o todos los parámetros.  
  
-   Opcional y `ParamArray` parámetros no se permiten en las expresiones lambda.  
  
-   Los parámetros genéricos no se permiten en las expresiones lambda.  
  
## <a name="example"></a>Ejemplo  
 La siguiente es un ejemplo de una expresión lambda que escribe un valor en la consola. El ejemplo muestra la sintaxis de expresiones lambda de varias líneas y de línea de una subrutina. Para obtener más ejemplos, vea [expresiones Lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]  
  
## <a name="see-also"></a>Vea también

- [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Expresiones lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [Operadores y expresiones](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)
- [Conversión de delegado flexible](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
