---
title: "Modo de archivo incorrecto | Microsoft Docs"
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
  - "vbrID54"
dev_langs: 
  - "VB"
ms.assetid: 74891e96-884b-4c8d-872d-cd11ae272372
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Modo de archivo incorrecto
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Las instrucciones que se utilizan para manipular el contenido de los archivos deben ser adecuadas para el modo en que se ha abierto el archivo.  Entre las posibles causas se incluyen:  
  
-   La instrucción `FilePutObject` o `FileGetObject` especifica un archivo secuencial.  
  
-   La instrucción `Print` especifica un archivo abierto para otro modo de acceso que no sea `Output` o `Append`.  
  
-   La instrucción `Input` especifica un archivo abierto para otro modo de acceso que no sea `Input`.  
  
-   Se intentó escribir en un archivo de sólo lectura.  
  
### Para corregir este error  
  
-   Asegúrese de que `FilePutObject` y `FileGetObject` sólo hacen referencia a archivos abiertos para acceso `Random` o `Binary`.  
  
-   Asegúrese de que `Print` especifica un archivo abierto para el modo de acceso `Output` o `Append`.  Si no es así, utilice otra instrucción para incluir datos en el archivo, o vuelva a abrir el archivo en un modo adecuado.  
  
-   Asegúrese de que `Input` especifica un archivo abierto para `Input`.  Si no es así, utilice otra instrucción para incluir datos en el archivo, o vuelva a abrir el archivo en un modo adecuado.  
  
-   Si está escribiendo en un archivo de sólo lectura, cambie el estado de lectura\/escritura del archivo o no intente escribir en él.  
  
-   Utilice la funcionalidad disponible en el objeto `My.Computer.FileSystem`.  
  
## Vea también  
 <xref:Microsoft.VisualBasic.FileSystem>   
 [Solución de problemas: Leer y escribir en archivos de texto](../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)