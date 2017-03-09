---
title: "No se pudo completar la operaci&#243;n porque el directorio de destino se encuentra bajo el directorio de origen | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrIO_CyclicOperation"
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# No se pudo completar la operaci&#243;n porque el directorio de destino se encuentra bajo el directorio de origen
No se pudo realizar una operación cíclica. Las operaciones cíclicas se realizan cíclicamente y, por tanto, no se pueden completar. Por ejemplo, el objeto A puede intentar heredar del objeto B, que a su vez hereda del objeto A.  
  
### Para corregir este error  
  
-   Durante la herencia, asegúrese de que no existe ninguna referencia cíclica.  
  
## Vea también  
 [Tipos de error](../../visual-basic/programming-guide/language-features/error-types.md)   
 [Debugging Basics: Breakpoints](http://msdn.microsoft.com/es-es/752a02c2-0ac7-4c8b-aa1b-4b2b3b21152e)