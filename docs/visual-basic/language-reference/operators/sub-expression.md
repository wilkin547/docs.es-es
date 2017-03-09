---
title: "Subexpresi&#243;n (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
helpviewer_keywords: 
  - "lambda (expresiones) [Visual Basic], subexpresión"
  - "Subexpresión [Visual Basic]"
  - "subrutinas [Visual Basic], subexpresiones"
ms.assetid: 36b6bfd1-6539-4d8f-a5eb-6541a745ffde
caps.latest.revision: 6
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 6
---
# Subexpresi&#243;n (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Declara los parámetros y el código que definen una expresión lambda de subrutina.  
  
## Sintaxis  
  
```  
Sub ( [ parameterlist ] ) statement  
- or -  
Sub ( [ parameterlist ] )  
  [ statements ]  
End Sub  
  
```  
  
## Elementos  
  
|||  
|-|-|  
|Término|Definición|  
|`parameterlist`|Opcional.  Lista de nombres de variable local que representan los parámetros del procedimiento.  Los paréntesis deben estar presentes aunque la lista esté vacía.  Para obtener más información, vea [Lista de parámetros](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`statement`|Obligatorio.  Una única instrucción.|  
|`statements`|Obligatorio.  Una lista de instrucciones.|  
  
## Comentarios  
 Una *expresión lambda* es una subrutina que no tiene un nombre y ejecuta una o más instrucciones.  Puede utilizar una expresión lambda en cualquier lugar donde puede utilizar un tipo de delegado, excepto como argumento de `RemoveHandler`.  Para obtener más información sobre los delegados y el uso de expresiones lambda con delegados, vea [Delegate \(Instrucción\)](../../../visual-basic/language-reference/statements/delegate-statement.md) y [Conversión de delegado flexible](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).  
  
## Sintaxis de la expresión lambda  
 La sintaxis de una expresión lambda se parece a la de una subrutina estándar.  Las diferencias son las siguientes:  
  
-   Una expresión lambda no tiene nombre.  
  
-   Las expresiones lambda no pueden tener modificadores, como `Overloads` u `Overrides`.  
  
-   El cuerpo de una expresión lambda de línea simple debe ser una instrucción, no una expresión.  El cuerpo puede estar formado por una llamada a un subprocedimiento, pero no una llamada a un procedimiento de función.  
  
-   En una expresión lambda, todos los parámetros deben haber especificado los tipos de datos o deben deducirse todos los parámetros.  
  
-   Los parámetros opcionales y `ParamArray` no se permiten en las expresiones lambda.  
  
-   Los parámetros genéricos no están permitidos en las expresiones lambda.  
  
## Ejemplo  
 A continuación, se muestra un ejemplo de una expresión lambda que escribe un valor en la consola.  En el ejemplo se muestra la sintaxis de expresiones lambda de una sola línea y de varias líneas para una subrutina.  Para obtener más ejemplos, vea [Expresiones lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbVbalrLambdas#15](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/vbvbalrlambdas/Class1.vb#15)]  
  
## Vea también  
 [Sub \(Instrucción\)](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Expresiones lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)   
 [Operadores y expresiones](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)   
 [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)   
 [Conversión de delegado flexible](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)