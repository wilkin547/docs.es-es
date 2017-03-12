---
title: "&#39;&lt;palabraClave&gt;&#39; s&#243;lo es v&#225;lida en un m&#233;todo de instancia | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30043"
  - "vbc30043"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30043"
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# &#39;&lt;palabraClave&gt;&#39; s&#243;lo es v&#225;lida en un m&#233;todo de instancia
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Las palabras clave `Me`,`MyClass` y `MyBase` hacen referencia a instancias de clase específicas.  No se pueden utilizar dentro de un procedimiento `Function` o `Sub`.  
  
 **Identificador de error:** BC30043  
  
### Para corregir este error  
  
-   Quite la palabra clave del procedimiento o quite la palabra clave `Shared` de la declaración del procedimiento.  
  
## Vea también  
 [Asignación de variables de objeto](../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)   
 [Me, My, MyBase y MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)   
 [Fundamentos de la herencia](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)