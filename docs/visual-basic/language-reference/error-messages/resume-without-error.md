---
title: "Reanudar sin error | Microsoft Docs"
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
  - "vbrID20"
dev_langs: 
  - "VB"
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Reanudar sin error
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Ha aparecido una instrucción `Resume` fuera del código de control de errores o el código pasó directamente al controlador de eventos aunque no se había producido ningún error.  
  
### Para corregir este error  
  
1.  Mueva la instrucción `Resume`a un controlador de errores o elimínela.  
  
2.  Los saltos a etiquetas no se pueden producir en los procedimientos, de modo que busque la etiqueta que identifique el controlador de errores en el procedimiento.  Si encuentra una etiqueta duplicada especificada como destino de una instrucción `GoTo` que no sea una instrucción `On Error GoTo`, cambie la etiqueta de la línea para que coincida con el destino deseado.  
  
## Vea también  
 [Resume \(Instrucción\)](../../../visual-basic/language-reference/statements/resume-statement.md)   
 [On Error \(Instrucción\)](../../../visual-basic/language-reference/statements/on-error-statement.md)