---
title: "La variable utiliza un tipo de automatizaci&#243;n no compatible con Visual Basic | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID458"
dev_langs: 
  - "VB"
ms.assetid: bde4f4da-493b-452c-b6e4-1d370edba4cd
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# La variable utiliza un tipo de automatizaci&#243;n no compatible con Visual Basic
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Ha intentado utilizar una variable definida en una biblioteca de tipos o de objetos que posee un tipo de datos que no es compatible con [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
### Para corregir este error  
  
-   Use una variable de un tipo que [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] reconozca.  
  
     O bien  
  
-   Si se encuentra este error al utilizar `FileGet` o `FileGetOBject`, asegúrese de que el archivo que intenta utilizar se ha escrito con `FilePut` o `FilePutObject`.  
  
## Vea también  
 [Tipos de datos](../../../visual-basic/language-reference/data-types/data-type-summary.md)