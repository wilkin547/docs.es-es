---
title: "Las constantes deben ser de tipo intr&#237;nseco o enumerado; no pueden ser de tipo clase, estructura, par&#225;metro de tipo ni matriz | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30424"
  - "bc30424"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30424"
ms.assetid: 2d402c2f-27ad-428b-b699-d45cd62f7196
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# Las constantes deben ser de tipo intr&#237;nseco o enumerado; no pueden ser de tipo clase, estructura, par&#225;metro de tipo ni matriz
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Ha intentado declarar una constante como una clase, estructura o tipo de matriz o como un parámetro de tipo definido por un tipo genérico contenedor.  
  
 Las constantes deben ser de un tipo intrínseco \(`Boolean`, `Byte`, `Date`, `Decimal`, `Double`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`o `UShort`\) o un tipo `Enum` basado en uno de los tipos enteros.  
  
 **Identificador de error:** BC30424  
  
### Para corregir este error  
  
1.  Declare la constante como de tipo intrínseco o `Enum`.  
  
2.  Una constante también puede ser un valor especial como `True`, `False` o `Nothing`.  El compilador considera que estos valores predefinidos son del tipo intrínseco adecuado.  
  
## Vea también  
 [Constantes y enumeraciones](../../../visual-basic/language-reference/constants-and-enumerations.md)   
 [Tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Tipos de datos](../../../visual-basic/language-reference/data-types/data-type-summary.md)