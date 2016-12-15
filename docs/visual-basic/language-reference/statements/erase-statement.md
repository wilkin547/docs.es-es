---
title: "Erase (Instrucci&#243;n, Visual Basic) | Microsoft Docs"
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
  - "vb.Erase"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Erase (palabra clave)"
  - "Erase (instrucción)"
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Erase (Instrucci&#243;n, Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Se utiliza para liberar variables de matriz y desasignar la memoria utilizada para sus elementos.  
  
## Sintaxis  
  
```  
Erase arraylist  
```  
  
## Elementos  
 `arraylist`  
 Obligatorio.  Lista de variables de matriz que se van a borrar.  Las variables múltiples se separan con comas.  
  
## Comentarios  
 La instrucción `Erase` sólo puede aparecer en el nivel de procedimiento.  Esto significa que se pueden liberar matrices dentro de un procedimiento, pero no en el nivel de clase o módulo.  
  
 La instrucción `Erase` es equivalente a asignar `Nothing` a cada variable de matriz.  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza la instrucción `Erase` para borrar dos matrices y liberar su memoria \(1000 y 100 elementos de almacenamiento, respectivamente\).  La instrucción `ReDim` después asigna una instancia de matriz nueva a la matriz de tres dimensiones.  
  
 [!code-vb[VbVbalrStatements#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/erase-statement_1.vb)]  
  
## Vea también  
 [Nothing](../../../visual-basic/language-reference/nothing.md)   
 [ReDim \(Instrucción\)](../../../visual-basic/language-reference/statements/redim-statement.md)