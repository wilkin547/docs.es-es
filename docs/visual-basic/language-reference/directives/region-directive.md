---
title: "#Region (Directiva) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Region"
  - "vb.#Region"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "#region (directiva)"
  - "#Region (palabra clave)"
  - "region: directiva (#region)"
  - "compilador de Visual Basic, directivas de compilador"
ms.assetid: 90a6a104-3cbf-47d0-bdc4-b585d0921b87
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# #Region (Directiva)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Contrae y oculta secciones de código en archivos de Visual Basic.  
  
## Sintaxis  
  
```  
  
        #Region "identifier_string"  
#End Region  
```  
  
## Elementos  
  
|||  
|-|-|  
|Término|Definición|  
|`identifier_string`|Requerido.  Cadena que actúa como título de una región cuando esta se contrae.  Las regiones están contraídas de forma predeterminada.|  
|`#End Region`|Finaliza el bloque `#Region`.|  
  
## Comentarios  
 La directiva `#Region` permite especificar un bloque de código que se puede expandir o contraer cuando se usa la característica de esquematización del Editor de código de Visual Studio.  Si desea agrupar regiones similares, puede situar o *anidar* unas regiones dentro de otras.  
  
## Ejemplo  
 En este ejemplo se usa la directiva `#Region`.  
  
 [!code-vb[VbVbalrConditionalComp#4](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/region-directive_1.vb)]  
  
## Vea también  
 [\#If...Then...\#Else \(Directivas\)](../../../visual-basic/language-reference/directives/if-then-else-directives.md)   
 [Esquematización](/visual-studio/ide/outlining)   
 [Cómo: Contraer y ocultar secciones de código](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)