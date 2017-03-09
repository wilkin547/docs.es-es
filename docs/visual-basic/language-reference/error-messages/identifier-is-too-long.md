---
title: "El identificador es demasiado largo | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30033"
  - "vbc30033"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30033"
ms.assetid: 3d07f6d0-9a2f-49ca-94e8-1e354932e855
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# El identificador es demasiado largo
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

El nombre o identificador de cada elemento de programación tiene un límite de 1023 caracteres.  Además, un nombre completo no puede superar los 1023 caracteres.  Esto significa que la cadena completa del identificador \(`<namespace>.<...>.<namespace>.<class>.<element>`\) no puede ser superior a 1023 caracteres, incluido el operador de acceso a miembros \(`.`\).  
  
 **Identificador de error:** BC30033  
  
### Para corregir este error  
  
-   Reduzca la longitud del identificador.  
  
## Vea también  
 [Nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)