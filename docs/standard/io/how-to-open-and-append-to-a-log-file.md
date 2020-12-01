---
title: Procedimiento Abrir y anexar a un archivo de registro
description: Abra y anexe a un archivo de registro con las clases StreamWriter y StreamReader en .NET, que escriben y leen caracteres en las secuencias.
ms.date: 01/21/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- log files, opening
- streams, opening and appending to log file
- log files, appending to
- I/O [.NET], log files
ms.assetid: 74423362-1721-49cb-aa0a-e04005f72a06
ms.openlocfilehash: be4cacee8d0a529730c66c5850f42330520ba2d3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734613"
---
# <a name="how-to-open-and-append-to-a-log-file"></a>Procedimiento Abrir y anexar a un archivo de registro

<xref:System.IO.StreamWriter> y <xref:System.IO.StreamReader> escriben y leen caracteres de secuencias. En el siguiente ejemplo de código se abre el archivo *log.txt* para realizar entradas o se crea el archivo en caso de que no exista y se adjunta información de registro al final del archivo. El ejemplo, a continuación, escribe el contenido del archivo en la salida estándar para su presentación.

Como alternativa a este ejemplo, podría almacenar la información como una sola cadena o como una matriz de cadenas, y usar el método <xref:System.IO.File.WriteAllText%2A?displayProperty=nameWithType> o <xref:System.IO.File.WriteAllLines%2A?displayProperty=nameWithType> para lograr la misma funcionalidad.  
  
> [!NOTE]
> Los usuarios de Visual Basic tienen la opción de utilizar los métodos y las propiedades proporcionados por las clases <xref:Microsoft.VisualBasic.Logging.Log> o <xref:Microsoft.VisualBasic.FileIO.FileSystem> para crear archivos de registro o escribir en ellos.  
  
## <a name="example"></a>Ejemplo  

 [!code-csharp[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source2.cs#2)]
 [!code-vb[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source2.vb#2)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.IO.StreamWriter>  
- <xref:System.IO.StreamReader>  
- <xref:System.IO.File.AppendText%2A?displayProperty=nameWithType>  
- <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
- [Cómo: Enumerar directorios y archivos](how-to-enumerate-directories-and-files.md)  
- [Cómo: Leer y escribir en un archivo de datos recién creado](how-to-read-and-write-to-a-newly-created-data-file.md)  
- [Cómo: Leer texto de un archivo](how-to-read-text-from-a-file.md)  
- [Cómo: Escribir texto en un archivo](how-to-write-text-to-a-file.md)  
- [Cómo: Leer caracteres de una cadena](how-to-read-characters-from-a-string.md)  
- [Cómo: Escribir caracteres en una cadena](how-to-write-characters-to-a-string.md)  
- [E/S de archivos y secuencias](index.md)
