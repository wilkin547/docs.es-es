---
title: "Implements (Cl&#225;usula, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.ImplementsClause"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Implements (palabra clave)"
  - "Implements (instrucción), acerca de Implements"
  - "implementación de interfaces, Implements (palabra clave)"
  - "implementación de interfaces, segunda implementación"
  - "miembros de interfaz"
  - "miembros de interfaz, implementar"
  - "miembros de interfaz, Implements (palabra clave)"
  - "miembros de interfaz, segunda implementación"
  - "miembros, implementar"
  - "miembros, Implements (palabra clave)"
  - "miembros, segunda implementación"
  - "segunda implementación"
ms.assetid: 5252cdf9-964d-4fc6-af0f-0449b7126b5a
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Implements (Cl&#225;usula, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Indica que un miembro de clase o de estructura proporciona la implementación para un miembro definido en una interfaz.  
  
## Comentarios  
 La palabra clave `Implements` no es lo mismo que [Implements \(Instrucción\)](../../../visual-basic/language-reference/statements/implements-statement.md).  Se utiliza la instrucción `Implements` para especificar que una clase o estructura implementa una o varias interfaces y luego, para cada miembro, se utiliza la palabra clave `Implements` para especificar las interfaces y los miembros que implementa.  
  
 Si una clase o estructura implementa una interfaz, debe incluir la instrucción `Implements` inmediatamente después de [Class \(Instrucción\)](../../../visual-basic/language-reference/statements/class-statement.md) o [Structure \(Instrucción\)](../../../visual-basic/language-reference/statements/structure-statement.md) y debe implementar todos los miembros definidos por la interfaz.  
  
## Reimplementación  
 En una clase derivada, puede reimplementar un miembro de interfaz que la clase base ya ha implementado.  Esto es diferente de reemplazar el miembro de clase base en los aspectos siguientes:  
  
-   El miembro de clase base no necesita ser [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) para ser reimplementado.  
  
-   Puede reimplementar el miembro con un nombre diferente.  
  
 La palabra clave `Implements` se puede utilizar en estos contextos:  
  
 [Event \(Instrucción\)](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Function \(Instrucción\)](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property \(Instrucción\)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub \(Instrucción\)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## Vea también  
 [Implements \(Instrucción\)](../../../visual-basic/language-reference/statements/implements-statement.md)   
 [Interface \(Instrucción\)](../../../visual-basic/language-reference/statements/interface-statement.md)   
 [Class \(Instrucción\)](../../../visual-basic/language-reference/statements/class-statement.md)   
 [Structure \(Instrucción\)](../../../visual-basic/language-reference/statements/structure-statement.md)