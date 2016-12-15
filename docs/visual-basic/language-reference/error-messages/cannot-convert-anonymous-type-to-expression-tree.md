---
title: "No se puede convertir un tipo an&#243;nimo en un &#225;rbol de expresi&#243;n porque contiene un campo que se usa en la inicializaci&#243;n de otro campo | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc36548"
  - "vbc36548"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36548"
ms.assetid: 27de068f-080e-4160-86bf-1ec23fd1925a
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# No se puede convertir un tipo an&#243;nimo en un &#225;rbol de expresi&#243;n porque contiene un campo que se usa en la inicializaci&#243;n de otro campo
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

El compilador no acepta la conversión de un anónimo a un árbol de expresión cuando una propiedad del tipo anónimo se usa para inicializar otra propiedad del tipo anónimo.  Por ejemplo, en el código siguiente, `Prop1` se declara en la lista de inicializaciones y, a continuación, se usa como valor inicial para `Prop2`.  
  
```vb#  
Module M2  
  
    Sub ExpressionExample(Of T)(ByVal x As Expressions.Expression(Of Func(Of T)))  
    End Sub  
  
    Sub Main()  
        ' The following line causes the error.  
        ' ExpressionExample(Function() New With {.Prop1 = 2, .Prop2 = .Prop1})  
  
    End Sub  
End Module  
```  
  
 **Id. de error:** BC36548  
  
### Para corregir este error  
  
-   Asigne el valor inicial para `Prop1` a una variable local.  Asigne esta variable a `Prop1` y `Prop2`, como se muestra en el código siguiente.  
  
    ```  
    Sub Main()  
  
        Dim temp = 2  
        ExpressionExample(Function() New With {.Prop1 = temp, .Prop2 = temp})  
  
    End Sub  
    ```  
  
## Vea también  
 [Tipos anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Árboles de expresión](../Topic/Expression%20Trees%20\(C%23%20and%20Visual%20Basic\).md)   
 [Cómo: Usar árboles de expresión para crear consultas dinámicas](../Topic/How%20to:%20Use%20Expression%20Trees%20to%20Build%20Dynamic%20Queries%20\(C%23%20and%20Visual%20Basic\).md)