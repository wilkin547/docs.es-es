---
title: "Se esperaba el fin de instrucci&#243;n | Microsoft Docs"
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
  - "bc30205"
  - "vbc30205"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30205"
ms.assetid: 53c7f825-a737-4b76-a1fa-f67745b8bd40
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Se esperaba el fin de instrucci&#243;n
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

La instrucción está completa sintácticamente, pero un elemento de programación adicional sigue al elemento que completa la instrucción.  Se requiere un terminador de línea al final de cada instrucción.  
  
 Un terminador de línea divide los caracteres de un archivo de código fuente de Visual Basic en líneas.  Los ejemplos de terminadores de línea son el carácter de retorno de carro Unicode \(&HD\), el carácter de avance de línea Unicode \(&HA\), y el carácter de retorno de carro Unicode seguido del carácter de avance de línea Unicode.  Para obtener más información sobre los terminadores de línea, vea [Especificación del lenguaje de Visual Basic](../../../visual-basic/reference/language-specification.md).  
  
 **Identificador de error:** BC30205  
  
### Para corregir este error  
  
1.  Compruebe si se colocaron por error dos instrucciones diferentes en la misma línea.  
  
2.  Inserte un terminador de línea después del elemento que completa la instrucción.  
  
## Vea también  
 [Cómo: Interrumpir y combinar instrucciones en código](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)   
 [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)