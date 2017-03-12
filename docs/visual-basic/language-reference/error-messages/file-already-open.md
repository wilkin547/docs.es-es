---
title: "Archivo ya abierto | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID55"
dev_langs: 
  - "VB"
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
caps.latest.revision: 7
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 7
---
# Archivo ya abierto
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

A veces, es necesario cerrar un archivo antes de que pueda producirse una operación `FileOpen` u otra operación.  Entre las causas posibles de este error están:  
  
-   Se ha ejecutado una operación `FileOpen` en modo de salida secuencial para un archivo que ya está abierto.  
  
-   Una instrucción hace referencia a un archivo abierto.  
  
### Para corregir este error  
  
1.  Cierre el archivo antes de ejecutar la instrucción.  
  
## Vea también  
 <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>