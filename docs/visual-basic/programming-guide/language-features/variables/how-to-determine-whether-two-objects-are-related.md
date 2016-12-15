---
title: "C&#243;mo: Determinar si dos objetos est&#225;n relacionados (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "herencia, objetos en Visual Basic"
  - "variables de objeto, determinar la relación"
  - "objetos [Visual Basic], herencia"
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Determinar si dos objetos est&#225;n relacionados (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Puede comprar dos objetos para determinar la relación que hay, si existe, entre las clases a partir de las cuales se crearon.  El método <xref:System.Type.IsInstanceOfType%2A> de la clase <xref:System.Type?displayProperty=fullName> devuelve `True` si la clase especificada se hereda de la clase actual o si el tipo actual es una interfaz compatible con la clase especificada.  
  
### Para determinar si un objeto hereda de la clase o interfaz de otro objeto  
  
1.  En el objeto que piensa que podría ser del tipo base, invoque el método <xref:System.Object.GetType%2A>.  
  
2.  En el objeto <xref:System.Type?displayProperty=fullName> devuelto por <xref:System.Object.GetType%2A>, invoque el método <xref:System.Type.IsInstanceOfType%2A>.  
  
3.  En la lista de argumentos para <xref:System.Type.IsInstanceOfType%2A>, especifique el objeto que piensa que podría ser del tipo derivado.  
  
     <xref:System.Type.IsInstanceOfType%2A> devuelve `True` si su tipo de argumento hereda del tipo de objeto <xref:System.Type?displayProperty=fullName>.  
  
## Ejemplo  
 El ejemplo siguiente determina si un objeto representa una clase derivada de la clase de otro objeto.  
  
```  
Public Class baseClass  
End Class  
Public Class derivedClass : Inherits baseClass  
End Class  
Public Class testTheseClasses  
    Public Sub seeIfRelated()  
        Dim baseObj As Object = New baseClass()  
        Dim derivedObj As Object = New derivedClass()  
        Dim related As Boolean  
        related = baseObj.GetType().IsInstanceOfType(derivedObj)  
        MsgBox(CStr(related))  
    End Sub  
End Class  
```  
  
 Observe la posición inesperada de las dos variables de objeto en la llamada a <xref:System.Type.IsInstanceOfType%2A>.  El tipo base supuesto se utiliza para generar la clase <xref:System.Type?displayProperty=fullName> y el tipo derivado supuesto se pasa como argumento al método <xref:System.Type.IsInstanceOfType%2A>.  
  
## Vea también  
 <xref:System.Object.GetType%2A>   
 <xref:System.Type?displayProperty=fullName>   
 <xref:System.Type.IsInstanceOfType%2A>   
 [Object \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/object-data-type.md)   
 [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Valores de las variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)   
 [Cómo: Determinar si dos objetos son idénticos](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)