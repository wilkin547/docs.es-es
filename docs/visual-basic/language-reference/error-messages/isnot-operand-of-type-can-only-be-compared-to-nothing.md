---
title: "El operando &#39;IsNot&#39; de tipo &#39;nombreDeTipo&#39; solo se puede comparar con &#39;Nothing&#39;, porque &#39;nombreDeTipo&#39; es un tipo que acepta valores NULL | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc32128"
  - "vbc32128"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32128"
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
caps.latest.revision: 5
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 5
---
# El operando &#39;IsNot&#39; de tipo &#39;nombreDeTipo&#39; solo se puede comparar con &#39;Nothing&#39;, porque &#39;nombreDeTipo&#39; es un tipo que acepta valores NULL
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Se ha comparado una variable declarada como un tipo que acepta valores NULL con una expresión distinta de `Nothing` mediante el operador `IsNot`.  
  
 **Id. de error:** BC32128  
  
### Para corregir este error  
  
1.  Para comparar un tipo que acepta valores NULL con una expresión distinta de `Nothing` mediante el operador `IsNot`, llame al método `GetType` en el tipo que acepta valores NULL y compare el resultado con la expresión, como se muestra en el ejemplo siguiente.  
  
    ```vb#  
    Dim number? As Integer = 5  
  
    If number IsNot Nothing Then  
      If number.GetType() IsNot Type.GetType("System.Int32") Then   
  
      End If  
    End If  
    ```  
  
## Vea también  
 [Tipos de valor que aceptan valores NULL](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)   
 [IsNot \(Operador\)](../../../visual-basic/language-reference/operators/isnot-operator.md)