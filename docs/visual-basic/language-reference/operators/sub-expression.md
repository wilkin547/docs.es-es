---
title: Expresión Sub
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic], sub expression
- Sub Expression [Visual Basic]
- subroutines [Visual Basic], sub expressions
ms.assetid: 36b6bfd1-6539-4d8f-a5eb-6541a745ffde
ms.openlocfilehash: e564fa3f717fc1a9f4e9961d9b3e961912a4d56b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873330"
---
# <a name="sub-expression-visual-basic"></a>Subexpresión (Visual Basic)

Declara los parámetros y el código que definen una expresión lambda de subrutina.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Sub ( [ parameterlist ] ) statement  
- or -  
Sub ( [ parameterlist ] )  
  [ statements ]  
End Sub  
```  
  
## <a name="parts"></a>Partes  
  
|Término|Definición|  
|---|---|  
|`parameterlist`|Opcional. Una lista de nombres de variables locales que representan los parámetros del procedimiento. Los paréntesis deben estar presentes incluso cuando la lista esté vacía. Para obtener más información, consulta [Parameter List](../statements/parameter-list.md).|  
|`statement`|Obligatorio. Una única instrucción.|  
|`statements`|Obligatorio. Una lista de instrucciones.|  
  
## <a name="remarks"></a>Comentarios  

 Una *expresión lambda* es una subrutina que no tiene un nombre y que ejecuta una o más instrucciones. Puede usar una expresión lambda en cualquier lugar en el que pueda usar un tipo de delegado, excepto como argumento para `RemoveHandler` . Para obtener más información sobre los delegados y el uso de expresiones lambda con delegados, vea [instrucción Delegate](../statements/delegate-statement.md) y [conversión de delegado relajado](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md).  
  
## <a name="lambda-expression-syntax"></a>Sintaxis de la expresión lambda  

 La sintaxis de una expresión lambda es similar a la de una subrutina estándar. Las diferencias son las siguientes:  
  
- Una expresión lambda no tiene un nombre.  
  
- Una expresión lambda no puede tener un modificador, como `Overloads` o `Overrides` .  
  
- El cuerpo de una expresión lambda de una sola línea debe ser una instrucción, no una expresión. El cuerpo puede constar de una llamada a un procedimiento Sub, pero no de una llamada a un procedimiento de función.  
  
- En una expresión lambda, todos los parámetros deben tener tipos de datos especificados o se deben inferir todos los parámetros.  
  
- `ParamArray`Los parámetros opcionales y no se permiten en expresiones lambda.  
  
- Los parámetros genéricos no se permiten en expresiones lambda.  
  
## <a name="example"></a>Ejemplo  

 A continuación se encuentra un ejemplo de una expresión lambda que escribe un valor en la consola. En el ejemplo se muestra la sintaxis de la expresión lambda de una sola línea y de varias líneas para una subrutina. Para obtener más ejemplos, consulte [expresiones lambda](../../programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]  
  
## <a name="see-also"></a>Consulte también

- [Instrucción Sub](../statements/sub-statement.md)
- [Expresiones lambda](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [Operadores y expresiones](../../programming-guide/language-features/operators-and-expressions/index.md)
- [Instrucciones](../../programming-guide/language-features/statements.md)
- [Conversión de delegado flexible](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
