---
title: "No se puede aplicar &#39;&lt;atributo&gt;&#39; porque el formato del GUID &#39;&lt;n&#250;mero&gt;&#39; no es correcto | Microsoft Docs"
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
  - "vbc32500"
  - "bc32500"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32500"
ms.assetid: 6fa34c55-368e-4d7d-b488-07a3fffe045f
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# No se puede aplicar &#39;&lt;atributo&gt;&#39; porque el formato del GUID &#39;&lt;n&#250;mero&gt;&#39; no es correcto
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Un bloque de atributos `COMClassAttribute` especifica un identificador único global \(GUID\) que no es conforme al formato correcto de un GUID.  `COMClassAttribute` utiliza identificadores GUID para identificar de manera única la clase, la interfaz y el evento de creación.  
  
 Un GUID consta de 16 bytes, de los cuales los ocho primeros son numéricos y el resto son binarios.  Se genera mediante utilidades de Microsoft como uuidgen.exe y garantiza su exclusividad en el espacio y el tiempo.  
  
 **Identificador de error:** BC32500  
  
### Para corregir este error  
  
1.  Determine el GUID o GUIDs correctos necesarios para identificar el objeto COM.  
  
2.  Asegúrese de que las cadenas del GUID presentadas al bloque de atributos `COMClassAttribute` se copian correctamente.  
  
## Vea también  
 <xref:System.Guid>   
 [Atributos](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)