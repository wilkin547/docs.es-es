---
title: "El primer operando de una expresi&#243;n &#39;If&#39; binaria debe ser un tipo que acepte valores NULL o un tipo de referencia | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc33107"
  - "vbc33107"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC33107"
ms.assetid: 493c8899-3f6b-4471-8eb6-9284e8492768
caps.latest.revision: 5
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 5
---
# El primer operando de una expresi&#243;n &#39;If&#39; binaria debe ser un tipo que acepte valores NULL o un tipo de referencia
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Una expresión `If` puede tener dos o tres argumentos.  Al enviar sólo dos argumentos, el primer argumento debe ser un tipo de referencia o un tipo que acepta valores NULL.  Si el primer argumento se evalúa en otra opción que no sea `Nothing`, se devuelve su valor.  Si el primer argumento se evalúa en `Nothing`, se evalúa y devuelve el segundo argumento.  
  
 Por ejemplo, el código siguiente contiene dos expresiones `If`, uno con tres argumentos y uno con dos argumentos.  Las expresiones calculan y devuelven el mismo valor.  
  
```vb#  
' firstChoice is a nullable value type.  
Dim firstChoice? As Integer = Nothing  
Dim secondChoice As Integer = 1128  
' If expression with three arguments.  
Console.WriteLine(If(firstChoice IsNot Nothing, firstChoice, secondChoice))  
' If expression with two arguments.  
Console.WriteLine(If(firstChoice, secondChoice))  
```  
  
 Las expresiones siguientes producen este error:  
  
```vb#  
Dim choice1 = 4  
Dim choice2 = 5  
Dim booleanVar = True  
  
' Not valid.  
'Console.WriteLine(If(choice1 < choice2, 1))  
' Not valid.  
'Console.WriteLine(If(booleanVar, "Test returns True."))  
```  
  
 **Id. de error:** BC33107  
  
### Para corregir este error  
  
-   Si no puede cambiar el código para que el primer argumento sea un tipo que acepta valores NULL o un tipo de referencia, considere la posibilidad de convertir a una expresión `If` de tres argumentos o a una instrucción `If...Then...Else`.  
  
    ```vb#  
    Console.WriteLine(If(choice1 < choice2, 1, 2))  
    Console.WriteLine(If(booleanVar, "Test returns True.", "Test returns False."))  
    ```  
  
## Vea también  
 [If \(operador\)](../../../visual-basic/language-reference/operators/if-operator.md)   
 [If...Then...Else \(Instrucción\)](../../../visual-basic/language-reference/statements/if-then-else-statement.md)   
 [Tipos de valor que aceptan valores NULL](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)