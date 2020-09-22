---
title: Archivo demasiado grande para su lectura en una matriz de bytes
ms.date: 07/20/2015
ms.assetid: 686630a6-a439-46c7-8d7b-34613ae4c5d8
ms.openlocfilehash: 89459aaf766a70f69008f847dda7ac6e2a1e41d1
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874174"
---
# <a name="file-is-too-large-to-read-into-a-byte-array"></a>Archivo demasiado grande para su lectura en una matriz de bytes

El tamaño del archivo que está intentando leer en una matriz de bytes supera los 4 GB. El `My.Computer.FileSystem.ReadAllBytes` método no puede leer un archivo que supere este tamaño.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Utilice un <xref:System.IO.StreamReader> para leer el archivo. Para obtener más información, vea [conceptos básicos de .NET Framework e/s de archivos y el sistema de archivos (Visual Basic)](../../developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md).  
  
## <a name="see-also"></a>Consulte también

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>
- <xref:System.IO.StreamReader>
- [Acceso a archivos con Visual Basic](../../developing-apps/programming/drives-directories-files/file-access.md)
- [Procedimiento para leer texto de archivos con StreamReader](../../developing-apps/programming/drives-directories-files/how-to-read-text-from-files-with-a-streamreader.md)
