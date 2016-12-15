---
title: "Convenci&#243;n de llamada a archivo DLL no v&#225;lida | Microsoft Docs"
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
  - "vbrID49"
dev_langs: 
  - "VB"
ms.assetid: 7c7def45-b0ab-450f-ad3f-4383dfd9aed7
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Convenci&#243;n de llamada a archivo DLL no v&#225;lida
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Los argumentos pasados a la biblioteca de vínculos dinámicos \(DLL\) deben coincidir exactamente con los especificados por la rutina.  Las convenciones de llamada se ocupan del número, tipo y orden de los argumentos.  Puede que el programa esté llamando a una rutina de una DLL a la que se está pasando el tipo o el número de argumentos incorrecto.  
  
### Para corregir este error  
  
1.  Asegúrese de que todos los tipos de argumentos coinciden con los especificados en la declaración de la rutina que está llamando.  
  
2.  Asegúrese de que está pasando el mismo número de argumentos indicados en la declaración de la rutina a la que está llamando.  
  
3.  Si la rutina de la DLL espera argumentos por valor, asegúrese de que se ha especificado `ByVal` en aquellos argumentos de la declaración para la rutina.  
  
## Vea también  
 [Tipos de error](../../../visual-basic/programming-guide/language-features/error-types.md)   
 [Call \(Instrucción\)](../../../visual-basic/language-reference/statements/call-statement.md)   
 [Declare \(Instrucción\)](../../../visual-basic/language-reference/statements/declare-statement.md)