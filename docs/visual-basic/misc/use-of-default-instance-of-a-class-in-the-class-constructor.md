---
title: "El uso de la instancia predeterminada de una clase en el constructor de la clase puede provocar una llamada recursiva infinita | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
ms.assetid: 9645b47f-7de5-46d0-bb45-d5fdaa8aaa2a
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# El uso de la instancia predeterminada de una clase en el constructor de la clase puede provocar una llamada recursiva infinita
Se usó una instancia predeterminada de una clase en el constructor de la clase. Esto puede derivar en una llamada recursiva infinita, también conocido como bucle infinito.  
  
### Para corregir este error  
  
-   Quite la instancia predeterminada del constructor de la clase.  
  
## Vea también  
 [NO ESTÁ EN LA COMPILACIÓN: Usar constructores y destructores](http://msdn.microsoft.com/es-es/548eebe1-86c4-4377-b2f5-447cb8be3d90)