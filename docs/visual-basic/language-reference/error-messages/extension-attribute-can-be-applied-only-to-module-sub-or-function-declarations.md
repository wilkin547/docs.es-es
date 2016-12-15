---
title: "El atributo &#39;Extension&#39; s&#243;lo se puede aplicar a las declaraciones &#39;Module&#39;, &#39;Sub&#39; o &#39;Function&#39; | Microsoft Docs"
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
  - "bc36550"
  - "vbc36550"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36550"
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# El atributo &#39;Extension&#39; s&#243;lo se puede aplicar a las declaraciones &#39;Module&#39;, &#39;Sub&#39; o &#39;Function&#39;
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

La única manera de extender un tipo de datos en Visual Basic es definir un método de extensión dentro de un módulo estándar.  El método de extensión puede ser un procedimiento `Sub` o un procedimiento `Function`.  Todos los métodos de extensión se deben marcar con el atributo de extensión, `<Extension()>`, del espacio de nombres <xref:System.Runtime.CompilerServices?displayProperty=fullName>.  Opcionalmente, se puede marcar de la misma manera un módulo que contiene un método de extensión.  Ningún otro uso del atributo de extensión es válido.  
  
 **Id. de error:** BC36550  
  
### Para corregir este error  
  
-   Quite el atributo de extensión.  
  
-   Vuelva a diseñar la extensión como un método, definido dentro de un módulo.  
  
## Ejemplo  
 En el siguiente ejemplo se define un método `Print` para el tipo de datos `String`.  
  
```  
Imports StringUtility  
Imports System.Runtime.CompilerServices  
Namespace StringUtility  
    <Extension()>   
    Module StringExtensions  
        <Extension()>   
        Public Sub Print (ByVal str As String)  
            Console.WriteLine(str)  
        End Sub  
    End Module  
End Namespace  
  
```  
  
## Vea también  
 [Atributos](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)   
 [métodos de extensión.](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)   
 [Module \(Instrucción\)](../../../visual-basic/language-reference/statements/module-statement.md)