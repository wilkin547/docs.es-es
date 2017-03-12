---
title: "Las expresiones lambda no son v&#225;lidas en la primera expresi&#243;n de una instrucci&#243;n &#39;Select Case&#39; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc36635"
  - "vbc36635"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36635"
ms.assetid: 74609979-9c03-4864-bbce-f588aa2e0917
caps.latest.revision: 6
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 6
---
# Las expresiones lambda no son v&#225;lidas en la primera expresi&#243;n de una instrucci&#243;n &#39;Select Case&#39;
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

No puede usar una expresión lambda para la expresión de prueba en una instrucción `Select Case`.  Las definiciones de la expresión lambda devuelven funciones y la expresión de prueba de una instrucción `Select Case` debe ser un tipo de datos básico.  
  
 El código siguiente genera este error:  
  
```vb#  
' Select Case (Function(arg) arg Is Nothing)  
    ' List of the cases.  
' End Select  
```  
  
 **Id. de error:** BC36635  
  
### Para corregir este error  
  
-   Examine el código para determinar si funcionaría una construcción condicional diferente, como una instrucción `If...Then...Else`.  
  
-   Quizá haya pensado en llamar a la función, tal y como se muestra en el código siguiente:  
  
    ```vb#  
    Dim num? As Integer  
    Select Case ((Function(arg? As Integer) arg Is Nothing)(num))  
        ' List of the cases  
    End Select  
    ```  
  
## Vea también  
 [Expresiones lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)   
 [If...Then...Else \(Instrucción\)](../../../visual-basic/language-reference/statements/if-then-else-statement.md)   
 [Select...Case \(Instrucción\)](../../../visual-basic/language-reference/statements/select-case-statement.md)