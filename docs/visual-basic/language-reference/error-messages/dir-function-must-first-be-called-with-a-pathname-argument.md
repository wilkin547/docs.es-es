---
title: "Se debe llamar primero a la funci&#243;n &#39;Dir&#39; con un argumento &#39;Pathname&#39; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrDIR_IllegalCall"
dev_langs: 
  - "VB"
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
caps.latest.revision: 7
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 7
---
# Se debe llamar primero a la funci&#243;n &#39;Dir&#39; con un argumento &#39;Pathname&#39;
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Una llamada inicial a la función `Dir` no incluye el argumento `PathName`.  La primera llamada a `Dir` debe incluir un `PathName`, pero las llamadas posteriores a `Dir` no necesitan incluir parámetros para recuperar el siguiente elemento.  
  
### Para corregir este error  
  
1.  Proporcione un argumento `PathName` en la llamada a función.  
  
## Vea también  
 <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>