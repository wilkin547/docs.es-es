---
title: "Archivo demasiado grande para su lectura en una matriz de bytes | Microsoft Docs"
ms.custom: ""
ms.date: "12/08/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
ms.assetid: 686630a6-a439-46c7-8d7b-34613ae4c5d8
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Archivo demasiado grande para su lectura en una matriz de bytes
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

El tamaño del archivo que está intentando leer en una matriz de bytes supera 4 GB.  El método `My.Computer.FileSystem.ReadAllBytes` no puede leer un archivo que supere este tamaño.  
  
### Para corregir este error  
  
-   Utilice <xref:System.IO.StreamReader> para leer el archivo.  Para obtener más información, vea [Fundamentos del sistema de archivos y la E\/S de archivos en .NET Framework \(Visual Basic\)](../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md).  
  
## Vea también  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>   
 <xref:System.IO.StreamReader>   
 [Acceso a archivos con Visual Basic](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)   
 [Cómo: Leer texto de archivos con StreamReader](../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-text-from-files-with-a-streamreader.md)