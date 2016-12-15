---
title: "/highentropyva (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "/highentropyva (opción del compilador) (Visual Basic)"
  - "highentropyva (opción del compilador) (Visual Basic)"
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /highentropyva (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Indica si un ejecutable 64 bits o un ejecutable que está marcada por la opción del compilador [\/platform: anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) admite el alto diseño Randomization \(ASLR\) del espacio de direcciones de la entropía.  
  
## Sintaxis  
  
```  
/highentropyva[+ | -]  
```  
  
## Argumentos  
 `+` &#124; `-`  
 Opcional.  La opción está desactivada de forma predeterminada o si especifica `/highentropyva-`.  La opción está activada si especifica `/highentropyva` o `/highentropyva+`.  
  
## Comentarios  
 Si se especifica esta opción, las versiones compatibles del kernel de Windows pueden utilizar grados superiores de entropía cuando kernel aleatoriza el diseño del espacio de direcciones de un proceso como parte de ASLR.  Si el kernel utiliza grados superiores de entropía, un número mayor de direcciones puede ser asignado a las regiones de memoria como pilas y pilas.  Como resultado, es más difícil ver la ubicación de una región de memoria concreta.  
  
 Cuando la opción está activada, el destino ejecutable y cualquier agente de los que depende deben ser capaces de controlar los valores de puntero que son mayores de 4 gigabytes \(GB\) cuando esos módulos se ejecutan como procesos de 64 bits.  
  
 Para obtener más información sobre ASLR, vea [Mitigar vulnerabilidades de software](http://go.microsoft.com/fwlink/?LinkId=226234).  
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)