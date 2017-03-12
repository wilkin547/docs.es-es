---
title: "No hay un mouse presente. | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrMouse_NoMouseIsPresent"
ms.assetid: 4472fd57-4217-4463-9d3c-dc4a8fe88f1b
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# No hay un mouse presente.
Se llamó a una de las propiedades del objeto `My.Computer.Mouse`, pero el equipo no tiene ningún mouse o puerto de mouse instalado.  
  
### Para corregir este error  
  
-   Agregue un bloque `Try...Catch` alrededor de la llamada a la propiedad del objeto `My.Computer.Mouse`.  
  
     o  
  
-   Instale un mouse en el equipo.  
  
## Vea también  
 [My.Computer.Mouse \(Objeto\)](../../visual-basic/language-reference/objects/my-computer-mouse-object.md)   
 [Control de excepciones y errores en Visual Basic](http://msdn.microsoft.com/es-es/3e351e73-cf23-40ab-8b60-05794160529e)   
 [Try...Catch...Finally \(Instrucción\)](../../visual-basic/language-reference/statements/try-catch-finally-statement.md)