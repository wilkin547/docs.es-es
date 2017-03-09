---
title: "#ExternalSource (Directiva) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "#Externalsource"
  - "#ExternalSource"
  - "vb.ExternalSource"
  - "Externalsource"
  - "vb.#ExternalSource"
  - "ExternalSource"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "#ExternalSource (directiva)"
  - "ExternalSource (directiva): #ExternalSource"
ms.assetid: 243bc6a2-34c3-4eeb-a776-9fd2bf988149
caps.latest.revision: 160
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 160
---
# #ExternalSource (Directiva)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Indica una asignación entre líneas específicas de código fuente y texto externo al código fuente.  
  
## Sintaxis  
  
```  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## Elementos  
 `StringLiteral`  
 La ruta del código fuente externo.  
  
 `IntLiteral`  
 El número de línea de la primera línea del código fuente externo.  
  
 `LogicalLine`  
 La línea en la que se produce el error en el código fuente externo.  
  
 `#End ExternalSource`  
 Termina el bloque `#ExternalSource`.  
  
## Comentarios  
 Únicamente el compilador y el depurador utilizan esta directiva.  
  
 Un archivo de código fuente puede incluir directivas de origen externo, que indican una asignación entre líneas de código específicas de dicho archivo y texto externo al código fuente, como un archivo .aspx.  Si se encuentran errores en el código fuente designado durante la compilación, se identifican como provenientes del código fuente externo.  
  
 Las directivas de código fuente externo no tienen efecto en la compilación y no se pueden anidar.  Están pensadas sólo para el uso interno de la aplicación.  
  
## Vea también  
 [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)