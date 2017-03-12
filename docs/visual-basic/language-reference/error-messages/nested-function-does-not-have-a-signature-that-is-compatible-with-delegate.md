---
title: "La funci&#243;n anidada no tiene una signatura compatible con el delegado &#39;&lt;nombreDeDelegado&gt;&#39; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc36532"
  - "bc36532"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36532"
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
caps.latest.revision: 5
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 5
---
# La funci&#243;n anidada no tiene una signatura compatible con el delegado &#39;&lt;nombreDeDelegado&gt;&#39;
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Se ha asignado una expresión lambda a un delegado que tiene una firma incompatible.  Por ejemplo, en el código siguiente, el delegado `Del` tiene dos parámetros enteros.  
  
```vb#  
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer  
```  
  
 Si una expresión lambda con un argumento se declara como tipo `Del`, se producirá el error:  
  
```vb#  
' Neither of these is valid.   
' Dim lambda1 As Del = Function(n As Integer) n + 1  
' Dim lambda2 As Del = Function(n) n + 1  
```  
  
 **Id. de error:** BC36532  
  
### Para corregir este error  
  
-   Ajuste la definición de delegado o la expresión lambda asignada para que las firmas sean compatibles.  
  
## Vea también  
 [Conversión de delegado flexible](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)   
 [Expresiones lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)