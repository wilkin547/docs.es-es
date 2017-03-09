---
title: "Se sobrepas&#243; el final del archivo | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID62"
dev_langs: 
  - "VB"
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Se sobrepas&#243; el final del archivo
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

O la instrucción `Input` lee un archivo que está vacío o uno en el que todos los datos se han utilizado, o bien, ha utilizado la función `EOF` con un archivo abierto para acceso binario.  
  
### Para corregir este error  
  
1.  Utilice la función `EOF` inmediatamente antes de la instrucción `Input` para detectar el final del archivo.  
  
2.  Si el archivo se ha abierto para acceso binario, utilice `Seek` y `Loc`.  
  
## Vea también  
 <xref:Microsoft.VisualBasic.FileSystem.Input%2A>   
 <xref:Microsoft.VisualBasic.FileSystem.EOF%2A>   
 <xref:Microsoft.VisualBasic.FileSystem.Seek%2A>   
 <xref:Microsoft.VisualBasic.FileSystem.Loc%2A>