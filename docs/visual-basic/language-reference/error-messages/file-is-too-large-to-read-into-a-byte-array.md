---
description: 'Más información acerca de: el archivo es demasiado grande para leerlo en una matriz de bytes'
title: Archivo demasiado grande para su lectura en una matriz de bytes
ms.date: 07/20/2015
ms.assetid: 686630a6-a439-46c7-8d7b-34613ae4c5d8
ms.openlocfilehash: 8b2eb7bcbbea42c56d607147e55d6c02695c5670
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796293"
---
# <a name="file-is-too-large-to-read-into-a-byte-array"></a>Archivo demasiado grande para su lectura en una matriz de bytes

El tamaño del archivo que está intentando leer en una matriz de bytes supera los 4 GB. El `My.Computer.FileSystem.ReadAllBytes` método no puede leer un archivo que supere este tamaño.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Utilice un <xref:System.IO.StreamReader> para leer el archivo. Para obtener más información, vea [conceptos básicos de .NET Framework e/s de archivos y el sistema de archivos (Visual Basic)](../../developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md).  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>
- <xref:System.IO.StreamReader>
- [Acceso a archivos con Visual Basic](../../developing-apps/programming/drives-directories-files/file-access.md)
- [Procedimiento para leer texto de archivos con StreamReader](../../developing-apps/programming/drives-directories-files/how-to-read-text-from-files-with-a-streamreader.md)
