---
title: "Formato del Portapapeles no v&#225;lido | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID460"
dev_langs: 
  - "VB"
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Formato del Portapapeles no v&#225;lido
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

El formato del Portapapeles especificado es incompatible con el método que está en ejecución.  Entre las causas posibles de este error están:  
  
-   Utilizar el método `GetText` o `SetText` del Portapapeles con un formato de Portapapeles distinto de `vbCFText` o `vbCFLink`.  
  
-   Utilizar el método `GetData` o `SetData` del Portapapeles con un formato de Portapapeles distinto de `vbCFBitmap`, `vbCFDIB` o `vbCFMetafile`.  
  
-   Utilizar el método `DataObject` `GetData` o el método `SetData` con un formato de Portapapeles en el intervalo reservado por Microsoft Windows para formatos registrados \(&HC000\-&HFFFF\), cuando ese formato de Portapapeles no está registrado en Microsoft Windows.  
  
### Para corregir este error  
  
-   Quite el formato no válido y especifique uno válido.  
  
## Vea también  
 [Portapapeles: Agregar otros formatos](../Topic/Clipboard:%20Adding%20Other%20Formats.md)