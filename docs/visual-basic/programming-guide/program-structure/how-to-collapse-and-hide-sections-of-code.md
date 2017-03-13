---
title: "C&#243;mo: Contraer y ocultar secciones de c&#243;digo (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "código de Visual Basic, contraer y ocultar"
  - "Visual Basic, contracción de código"
  - "Visual Basic, ocultación de código"
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# C&#243;mo: Contraer y ocultar secciones de c&#243;digo (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

La directiva `#Region` permite contraer y ocultar secciones de código en archivos de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  La directiva `#Region` permite especificar un bloque de código que se puede expandir o contraer al utilizar el editor de código de [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)].  La capacidad para ocultar código de forma selectiva facilita la administración del código y su lectura.  Para obtener más información, vea [Esquematización](/visual-studio/ide/outlining).  
  
 Las directivas `#Region` admiten la semántica de bloque de código como `#If...#End If`.  Es decir, no pueden empezar en un bloque y terminar en otro; su principio y su fin deben estar en el mismo bloque.  Las directivas `#Region` no se admiten en las funciones.  
  
### Para contraer y esconder secciones de código  
  
-   Sitúe la sección de código entre las instrucciones `#Region` y `#End Region`, como en el siguiente ejemplo:  
  
     [!code-vb[VbVbalrConditionalComp#6](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/how-to-collapse-and-hide-sections-of-code_1.vb)]  
  
     El bloque `#Region` puede utilizarse varias veces en un archivo de código; de esta forma, los usuarios pueden definir sus propios bloques de procedimientos y clases que, a su vez, pueden contraerse.  Los bloques `#Region` también pueden anidarse dentro de otros bloques `#Region`.  
  
    > [!NOTE]
    >  Al ocultar el código no evita que éste se compile, y no afecta a las instrucciones `#If...#End If`.  
  
## Vea también  
 [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)   
 [\#Region \(Directiva\)](../../../visual-basic/language-reference/directives/region-directive.md)   
 [\#If...Then...\#Else \(Directivas\)](../../../visual-basic/language-reference/directives/if-then-else-directives.md)   
 [Esquematización](/visual-studio/ide/outlining)