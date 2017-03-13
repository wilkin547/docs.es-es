---
title: "Expresi&#243;n de funci&#243;n (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Expresión de función [Visual Basic]"
  - "funciones [Visual Basic], expresiones de función"
  - "lambda (expresiones) [Visual Basic], expresión de función"
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Expresi&#243;n de funci&#243;n (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Declara los parámetros y el código que definen una expresión lambda de función.  
  
## Sintaxis  
  
```  
Function ( [ parameterlist ] ) expression  
- or -  
Function ( [ parameterlist ] )  
  [ statements ]  
End Function  
  
```  
  
## Elementos  
  
|||  
|-|-|  
|Término|Definición|  
|`parameterlist`|Opcional.  Lista de nombres de variable local que representan los parámetros de este procedimiento.  Los paréntesis deben estar presentes aunque la lista esté vacía.  Vea [Lista de parámetros](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`expression`|Obligatorio.  Una expresión única.  El tipo de la expresión es el tipo de valor devuelto de la función.|  
|`statements`|Obligatorio.  Una lista de declaraciones que devuelve un valor mediante la instrucción `Return` .  \(Vea [Return \(Instrucción\)](../../../visual-basic/language-reference/statements/return-statement.md).\) El tipo del valor devuelto es el tipo de valor devuelto de la función.|  
  
## Comentarios  
 Una *expresión lambda* es una función sin nombre que calcula y devuelve un valor.  Puede utilizar una expresión lambda en cualquier lugar donde puede utilizar un tipo de delegado, excepto como argumento de `RemoveHandler`.  Para obtener más información sobre los delegados y el uso de expresiones lambda con delegados, vea [Delegate \(Instrucción\)](../../../visual-basic/language-reference/statements/delegate-statement.md) y [Conversión de delegado flexible](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).  
  
## Sintaxis de la expresión lambda  
 La sintaxis de una expresión lambda se parece a la de una función estándar.  Las diferencias son las siguientes:  
  
-   Una expresión lambda no tiene nombre.  
  
-   Las expresiones lambda no pueden tener modificadores, como `Overloads` u `Overrides`.  
  
-   Las expresiones lambda no utilizan una cláusula `As` para designar el tipo de valor devuelto de la función.  En su lugar, el tipo se deduce del valor al que se evalúa el cuerpo de una expresión lambda de línea única, o del valor devuelto de una expresión lambda multilínea.  Por ejemplo, si el cuerpo de una expresión lambda de una única línea es `Where cust.City = "London"`, su tipo de valor devuelto es `Boolean`.  
  
-   El cuerpo de una expresión lambda de línea simple debe ser una expresión, no una instrucción.  El cuerpo puede estar formado por una llamada a un procedimiento de función, pero no una llamada a un subprocedimiento.  
  
-   Todos los parámetros deben de tener tipos de datos especificados o se deben deducir.  
  
-   No se permite los parámetros Optional y ParamArray.  
  
-   No se permiten los parámetros Generic.  
  
## Ejemplo  
 En los ejemplos siguientes se muestran dos maneras de crear expresiones lambda simples.  El primero utiliza `Dim` para proporcionar un nombre para la función.  Para llamar a la función, envíe un valor al parámetro.  
  
 [!code-vb[VbVbalrLambdas#1](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_1.vb)]  
  
 [!code-vb[VbVbalrLambdas#2](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_2.vb)]  
  
## Ejemplo  
 O bien, puede declarar y ejecutar la función al mismo tiempo.  
  
 [!code-vb[VbVbalrLambdas#3](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_3.vb)]  
  
## Ejemplo  
 A continuación, se muestra un ejemplo de una expresión lambda que incrementa su argumento y devuelve el valor.  En el ejemplo se muestra la sintaxis de expresiones lambda de una sola línea y de varias líneas para una función.  Para obtener más ejemplos, vea [Expresiones lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbVbalrLambdas#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_4.vb)]  
  
## Ejemplo  
 Las expresiones lambda están debajo de muchos de los operadores de consulta de [!INCLUDE[vbteclinqext](../../../csharp/getting-started/includes/vbteclinqext-md.md)] y se pueden utilizar explícitamente en consultas basadas en método.  En el ejemplo siguiente se muestra una consulta [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)] típica, seguida por la traducción de la consulta al formato de método.  
  
```vb#  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 Para obtener más información sobre métodos de consulta, vea [Consultas](../../../visual-basic/language-reference/queries/queries.md).  Para obtener más información sobre los operadores de consulta estándar, vea [Standard Query Operators Overview](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).  
  
## Vea también  
 [Function \(Instrucción\)](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Expresiones lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)   
 [Operadores y expresiones](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)   
 [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)   
 [Comparaciones de valores](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)   
 [Expresiones booleanas](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)   
 [If \(operador\)](../../../visual-basic/language-reference/operators/if-operator.md)   
 [Conversión de delegado flexible](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)