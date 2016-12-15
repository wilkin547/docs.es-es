---
title: "La instrucci&#243;n no es v&#225;lida dentro de un m&#233;todo o una expresi&#243;n lambda de varias l&#237;neas | Microsoft Docs"
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
  - "vbc30024"
  - "bc30024"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30024"
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# La instrucci&#243;n no es v&#225;lida dentro de un m&#233;todo o una expresi&#243;n lambda de varias l&#237;neas
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

La instrucción no es válida dentro de un procedimiento `Sub`, `Function`, `Get` propiedad o `Set` propiedad.  Algunas instrucciones se pueden colocar en el nivel de módulo o clase.  Otras, como `Option Strict`, deben estar en el nivel de espacio de nombres y preceder al resto de declaraciones.  
  
 **Identificador de error:** BC30024  
  
### Para corregir este error  
  
-   Quite la instrucción del procedimiento.  
  
## Vea también  
 [Sub \(Instrucción\)](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Function \(Instrucción\)](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Get \(Instrucción\)](../../../visual-basic/language-reference/statements/get-statement.md)   
 [Set \(Instrucción\)](../../../visual-basic/language-reference/statements/set-statement.md)