---
title: "Demasiados clientes de aplicaci&#243;n DLL | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID47"
ms.assetid: 4b87780b-67ad-4c96-9253-db954a751dad
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Demasiados clientes de aplicaci&#243;n DLL
La biblioteca de vínculos dinámicos \(DLL\) de [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] solo puede admitir el acceso de un número limitado de aplicaciones host. La aplicación y otras aplicaciones que son hosts de [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] \(es posible que su aplicación acceda a algunos de estos\) están intentando acceder a la DLL de [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] al mismo tiempo.  
  
### Para corregir este error  
  
-   Reduzca el número de aplicaciones abiertas que acceden a [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
## Vea también  
 [Tipos de error](../../visual-basic/programming-guide/language-features/error-types.md)