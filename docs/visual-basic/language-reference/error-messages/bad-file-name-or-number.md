---
title: "N&#250;mero o nombre de archivo incorrecto | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbrID52"
dev_langs: 
  - "VB"
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# N&#250;mero o nombre de archivo incorrecto
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Error al intentar obtener acceso al archivo especificado.  Entre las causas posibles de este error están:  
  
-   La instrucción hace referencia a un archivo con un nombre o número que no se ha especificado en la instrucción `FileOpen` o que se ha especificado en la instrucción `FileOpen` pero que no se ha cerrado posteriormente.  
  
-   La instrucción hace referencia a un archivo con un número que está fuera del intervalo de números de archivo.  
  
-   La sentencia hace referencia a un nombre o número de archivo que no es válido.  
  
### Para corregir este error  
  
1.  Asegúrese de que se ha especificado en la instrucción `FileOpen` el nombre de archivo.  Recuerde que si invocó la instrucción `FileClose` sin argumentos, puede haber cerrado todos los archivos abiertos sin darse cuenta.  
  
2.  Si el código genera números de archivo mediante algoritmos, asegúrese de que los números son válidos.  
  
3.  Compruebe los nombres de archivo para asegurarse de que cumplen las convenciones del sistema operativo.  
  
## Vea también  
 <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>   
 [Convenciones de nomenclatura de Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)