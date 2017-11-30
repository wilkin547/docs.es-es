---
title: Archivo demasiado grande para su lectura en una matriz de bytes
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: 686630a6-a439-46c7-8d7b-34613ae4c5d8
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2bbdb5a4dcaa22ca84428ef28c8838a6d9a0ee1b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="file-is-too-large-to-read-into-a-byte-array"></a>Archivo demasiado grande para su lectura en una matriz de bytes
El tamaño del archivo que está intentando leer en una matriz de bytes supera 4 GB. El `My.Computer.FileSystem.ReadAllBytes` método no puede leer un archivo que supera este tamaño.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Use un <xref:System.IO.StreamReader> para leer el archivo. Para obtener más información, consulte [conceptos básicos de .NET Framework E/S de archivos y el sistema de archivos (Visual Basic)](../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>  
 <xref:System.IO.StreamReader>  
 [Acceso a archivos con Visual Basic](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)  
 [Leer texto de archivos con StreamReader](../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-text-from-files-with-a-streamreader.md)
