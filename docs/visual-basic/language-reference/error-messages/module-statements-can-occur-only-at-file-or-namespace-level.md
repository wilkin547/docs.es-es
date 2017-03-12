---
title: "Las instrucciones &#39;Module&#39; s&#243;lo pueden ocurrir en el nivel de archivo o de espacio de nombres | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30617"
  - "vbc30617"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30617"
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Las instrucciones &#39;Module&#39; s&#243;lo pueden ocurrir en el nivel de archivo o de espacio de nombres
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Las instrucciones `Module` deben aparecer al principio del archivo de código fuente inmediatamente después de las instrucciones `Option` e `Imports`, los atributos globales y las declaraciones de espacios de nombres, pero antes que el resto de declaraciones.  
  
 **Identificador de error:** BC30617  
  
### Para corregir este error  
  
-   Mueva la instrucción `Module` al principio de la declaración de espacios de nombres o del archivo de código fuente.  
  
## Vea también  
 [Module \(Instrucción\)](../../../visual-basic/language-reference/statements/module-statement.md)