---
title: "WithEvents (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.WithEvents"
  - "WithEvents"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "WithEvents (palabra clave)"
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# WithEvents (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Especifica que una o más variable miembro  declaradas hacen referencia a una instancia de una clase que puede provocar eventos.  
  
## Comentarios  
 Cuando una variable se define utilizando `WithEvents`, puede especificar mediante declaración que un método controla los eventos de la variable mediante la palabra clave `Handles`.  
  
 Sólo puede utilizar `WithEvents` en el nivel de clase o de módulo.  Esto significa que el contexto de declaración de una variable `WithEvents` debe ser una clase o un módulo, y no un archivo de código fuente, un espacio de nombres o un procedimiento.  
  
 No puede utilizar `WithEvents` dentro de un miembro de estructura.  
  
 Con `WithEvents` sólo se pueden declarar variables individuales \(no matrices\).  
  
## Reglas  
  
-   **Tipos de elementos.** Debe declarar las variables `WithEvents` para que sean variables de objeto y que puedan aceptar instancias de clase.  Sin embargo, no puede declararlas como `Object`.  Debe declararlas como la clase específica que puede provocar los eventos.  
  
 El modificador `WithEvents` se puede utilizar en este contexto: [Dim \(Instrucción\)](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## Vea también  
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)   
 [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)   
 [Eventos](../../../visual-basic/programming-guide/language-features/events/events.md)