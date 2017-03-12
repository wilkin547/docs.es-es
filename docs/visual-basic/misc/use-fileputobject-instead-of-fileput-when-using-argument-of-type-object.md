---
title: "Use &#39;FilePutObject&#39; en lugar de &#39;FilePut&#39; al usar el argumento de tipo &#39;Object&#39;. | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrUseFilePutObject"
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Use &#39;FilePutObject&#39; en lugar de &#39;FilePut&#39; al usar el argumento de tipo &#39;Object&#39;.
El método `FilePut` incluye un argumento de tipo `Object`. Debe usarse `FilePutObject` en lugar de `FilePut` para evitar ambigüedades.  
  
### Para corregir este error  
  
-   Reemplace `FilePut` por `FilePutObject`.  
  
-   Convierta el argumento `Object` a un tipo más específico.  
  
-   Use la funcionalidad disponible en el objeto `My.Computer.FileSystem`.  
  
## Vea también  
 [NO ESTÁ EN LA COMPILACIÓN: Función FilePutObject](http://msdn.microsoft.com/es-es/a0f52a1c-5ecc-4945-b18c-03147af61d6b)   
 [My.Computer.FileSystem \(Objeto\)](../../visual-basic/language-reference/objects/my-computer-filesystem-object.md)   
 [Método My.Computer.FileSystem.WriteAllBytes](http://msdn.microsoft.com/es-es/b1a24dc1-eac8-4e22-8ffa-cc3bacbaf826)