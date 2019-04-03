---
title: Archivo demasiado grande para su lectura en una matriz de bytes
ms.date: 07/20/2015
ms.assetid: 686630a6-a439-46c7-8d7b-34613ae4c5d8
ms.openlocfilehash: 0c7d35e08eeb42e35c4c40e47434a64393d829b1
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58831519"
---
# <a name="file-is-too-large-to-read-into-a-byte-array"></a>Archivo demasiado grande para su lectura en una matriz de bytes
El tamaño del archivo que está intentando leer en una matriz de bytes supera los 4 GB. El `My.Computer.FileSystem.ReadAllBytes` método no puede leer un archivo que supera este tamaño.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Use un <xref:System.IO.StreamReader> para leer el archivo. Para obtener más información, consulte [conceptos básicos de .NET Framework de E/S de archivos y el sistema de archivos (Visual Basic)](../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md).  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>
- <xref:System.IO.StreamReader>
- [Acceso a archivos con Visual Basic](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)
- [Cómo: Leer texto de archivos con StreamReader](../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-text-from-files-with-a-streamreader.md)
