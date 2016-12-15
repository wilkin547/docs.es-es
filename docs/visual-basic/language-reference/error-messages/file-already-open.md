---
title: "Archivo ya abierto | Microsoft Docs"
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
  - "vbrID55"
dev_langs: 
  - "VB"
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Archivo ya abierto
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

A veces, es necesario cerrar un archivo antes de que pueda producirse una operación `FileOpen` u otra operación.  Entre las causas posibles de este error están:  
  
-   Se ha ejecutado una operación `FileOpen` en modo de salida secuencial para un archivo que ya está abierto.  
  
-   Una instrucción hace referencia a un archivo abierto.  
  
### Para corregir este error  
  
1.  Cierre el archivo antes de ejecutar la instrucción.  
  
## Vea también  
 <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>