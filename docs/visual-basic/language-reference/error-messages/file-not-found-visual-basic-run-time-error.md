---
title: "No se encuentra el archivo (error en tiempo de ejecuci&#243;n de Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID53"
dev_langs: 
  - "VB"
ms.assetid: 57addb16-6f9a-444d-8af8-dda52431daca
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# No se encuentra el archivo (error en tiempo de ejecuci&#243;n de Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

No se ha encontrado el archivo donde está especificado.  Este error tiene las causas posibles siguientes:  
  
-   La instrucción hace referencia a un archivo que no existe.  
  
-   Se ha intentado llamar a un procedimiento en una biblioteca de vínculos dinámicos \(DLL\), pero la biblioteca especificada en la cláusula `Lib` de la instrucción `Declare` no se puede encontrar.  
  
-   Ha intentado abrir un proyecto o cargar un archivo de texto que no existe.  
  
### Para corregir este error  
  
1.  Compruebe que ha escrito correctamente la especificación de nombre de archivo y la ruta de acceso.  
  
## Vea también  
 [Declare \(Instrucción\)](../../../visual-basic/language-reference/statements/declare-statement.md)