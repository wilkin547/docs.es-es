---
title: "Stop (Instrucci&#243;n, Visual Basic) | Microsoft Docs"
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
  - "vb.Stop"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "puntos de interrupción, Stop (instrucciones)"
  - "ejecución, detener"
  - "ejecución, suspender"
  - "procesos, interrumpir"
  - "procesar, interrumpir"
  - "Stop (instrucciones)"
  - "Stop (instrucciones), sintaxis"
ms.assetid: c9a9fde0-d649-4662-9bef-bd0146ebc2a7
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Stop (Instrucci&#243;n, Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Suspende la ejecución.  
  
## Sintaxis  
  
```  
Stop  
```  
  
## Comentarios  
 Se pueden colocar instrucciones `Stop` en cualquier parte de los procedimientos para suspender la ejecución.  El uso de la instrucción `Stop` es similar a establecer un punto de interrupción en el código.  
  
 La instrucción `Stop` suspende la ejecución, pero a diferencia de `End` no cierra ningún archivo ni borra variables, a menos que se encuentre en un archivo ejecutable compilado \(.exe\).  
  
> [!NOTE]
>  Si la instrucción `Stop` se encuentra en código que se está ejecutando fuera del entorno de desarrollo integrado \(IDE\), se invoca el depurador.  Esto es así independientemente de si el código se compiló en modo de depuración o en modo comercial.  
  
## Ejemplo  
 En este ejemplo se utiliza la instrucción `Stop` para suspender la ejecución para cada iteración a través del bucle `For...Next`.  
  
 [!code-vb[VbVbalrStatements#56](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/stop-statement_1.vb)]  
  
## Vea también  
 [End \(Instrucción\)](../../../visual-basic/language-reference/statements/end-statement.md)