---
title: "No se admiten referencias de entidad XML | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc31180"
  - "bc31180"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31180"
ms.assetid: 2a393327-d8e2-4187-85b1-642b4f53b4ae
caps.latest.revision: 6
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 6
---
# No se admiten referencias de entidad XML
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Una referencia de entidad \(por ejemplo, `©`\) que no se define en la especificación XML 1.0, se incluye como un valor para un literal XML.  Únicamente se admiten las referencias de entidad XML `&`, `"`, `<`, `>`y `'` en literales XML.  
  
 **Id. de error:** BC31180  
  
### Para corregir este error  
  
-   Quite la referencia de entidad no compatible.  
  
## Vea también  
 [Literales XML y la especificación XML 1.0](../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)   
 [Literales XML](../../../visual-basic/language-reference/xml-literals/index.md)   
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)