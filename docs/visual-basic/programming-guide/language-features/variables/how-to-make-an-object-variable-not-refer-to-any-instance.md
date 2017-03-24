---
title: "C&#243;mo: Crear una variable de objeto que no haga referencia a ninguna instancia (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Nothing (palabra clave), asignación de variables"
  - "variables de objeto, referencia nula"
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# C&#243;mo: Crear una variable de objeto que no haga referencia a ninguna instancia (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Puede desasociar una variable de objeto de cualquier instancia de objeto estableciéndola en [Nothing](../../../../visual-basic/language-reference/nothing.md).  
  
### Para desasociar una variable de objeto de cualquier instancia de objeto  
  
-   Establezca la variable en `Nothing` en una instrucción de asignación.  
  
    ```  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## Programación eficaz  
 Si su código intenta tener acceso a un miembro de una variable de objeto establecida en `Nothing`, se produce una excepción <xref:System.NullReferenceException>.  Si establece a menudo una variable de objeto en `Nothing` o si es posible que la variable no esté inicializada, resulta conveniente agregar los accesos a los miembros en un bloque `Try...Catch...Finally`.  
  
## Seguridad de .NET Framework  
 Si utiliza una variable para objetos que contienen datos confidenciales o sensibles, puede establecer la variable en `Nothing` cuando no esté tratando activamente uno de esos objetos.  Esto reduce la posibilidad de que código malintencionado tenga acceso a los datos.  
  
## Vea también  
 <xref:System.NullReferenceException>   
 [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Asignación de variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)   
 [Nothing](../../../../visual-basic/language-reference/nothing.md)   
 [Try...Catch...Finally \(Instrucción\)](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)   
 [Solución de problemas de excepciones: System.NullReferenceException](../Topic/Troubleshooting%20Exceptions:%20System.NullReferenceException.md)