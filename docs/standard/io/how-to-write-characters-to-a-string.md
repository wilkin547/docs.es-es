---
title: Procedimiento para escribir caracteres en una cadena
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data streams, writing characters to string
- writing characters to strings
- streams, writing characters to strings
- I/O [.NET Framework], writing characters to strings
ms.assetid: 1222cbeb-0760-44bf-9888-914a2a37174b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 125c8ba03c4d1006535dd1e10cbd162b32fede4f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54740988"
---
# <a name="how-to-write-characters-to-a-string"></a>Procedimiento para escribir caracteres en una cadena
Los siguientes ejemplos de código escriben caracteres de forma sincrónica y asincrónica desde una matriz de caracteres en una cadena.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se escriben cinco caracteres de forma sincrónica desde una matriz en una cadena.  
  
 [!code-csharp[Conceptual.StringBuilder#9](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/example2.cs#9)]
 [!code-vb[Conceptual.StringBuilder#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/example2.vb#9)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se leen todos los caracteres e forma asincrónica desde un control <xref:System.Windows.Controls.TextBox> y se almacenan en una matriz. Luego escribe de forma asincrónica cada carácter de letra o espacio en blanco en una línea independiente seguida de un salto de línea en un control <xref:System.Windows.Controls.TextBlock>.  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source2.cs#2)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source2.vb#2)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.IO.StringWriter>
- <xref:System.IO.StringWriter.Write%2A?displayProperty=nameWithType>
- <xref:System.Text.StringBuilder>
- [E/S de archivos y secuencias](../../../docs/standard/io/index.md)
- [Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md)
- [Cómo: Enumerar directorios y archivos](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)
- [Cómo: Leer y escribir en un archivo de datos recién creado](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)
- [Cómo: Abrir y anexar a un archivo de registro](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)
- [Cómo: Leer texto de un archivo](../../../docs/standard/io/how-to-read-text-from-a-file.md)
- [Cómo: Escribir texto en un archivo](../../../docs/standard/io/how-to-write-text-to-a-file.md)
- [Cómo: Leer caracteres de una cadena](../../../docs/standard/io/how-to-read-characters-from-a-string.md)
