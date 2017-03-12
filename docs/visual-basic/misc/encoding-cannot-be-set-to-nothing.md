---
title: "La codificaci&#243;n no se puede establecer en Nothing | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
ms.assetid: 59f7c731-8291-4a85-bf51-c225e48cdc84
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# La codificaci&#243;n no se puede establecer en Nothing
Error en un intento de leer un archivo o escribir en él porque el parámetro `encoding` se ha establecido en `Nothing` pero requiere un valor válido.  
  
 <xref:System.Text.Encoding> se usa para determinar qué codificación se debe usar al escribir en un archivo. El valor predeterminado es UTF\-8.  
  
### Para corregir este error  
  
-   Proporcione un valor válido para el parámetro `encoding`.  
  
## Vea también  
 [Codificaciones de archivos](../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md)   
 [Leer archivos](../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)   
 [Escribir en archivos](../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)   
 [My.Computer.FileSystem.ReadAllText \(Método\)](http://msdn.microsoft.com/es-es/3a7ac8be-fb1d-4087-bc65-167d6754d57f)   
 [My.Computer.FileSystem.WriteAllText \(Método\)](http://msdn.microsoft.com/es-es/f507460c-87d9-4504-b74f-3ff825c7d5c4)