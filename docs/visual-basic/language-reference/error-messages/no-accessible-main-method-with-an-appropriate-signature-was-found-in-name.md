---
title: "No se encontr&#243; ning&#250;n m&#233;todo &#39;Main&#39; accesible con una firma apropiada en &#39;&lt;nombre&gt;&#39; | Microsoft Docs"
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
  - "bc30737"
  - "vbc30737"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30737"
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# No se encontr&#243; ning&#250;n m&#233;todo &#39;Main&#39; accesible con una firma apropiada en &#39;&lt;nombre&gt;&#39;
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Las aplicaciones de línea de comandos deben tener un procedimiento `Sub Main` definido.  `Main` se debe declarar como `Public Shared` si está definido en una clase o como `Public` si está definido en un módulo.  
  
 Para obtener más información sobre `Main`, consulte [Versión de Visual Basic del programa Hola a todos](http://msdn.microsoft.com/es-es/9d030b60-e148-4366-a462-69532f02294c).  
  
 **Identificador de error:** BC30737  
  
### Para corregir este error  
  
-   Defina un procedimiento `Public Sub Main` para el proyecto.  Declárelo como `Shared` sólo si lo define dentro de una clase.  
  
## Vea también  
 [Versión de Visual Basic del programa Hola a todos](http://msdn.microsoft.com/es-es/9d030b60-e148-4366-a462-69532f02294c)   
 [Estructura de un programa de Visual Basic](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)   
 [Procedimientos](../../../visual-basic/programming-guide/language-features/procedures/index.md)