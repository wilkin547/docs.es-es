---
title: 'Cómo: Leer caracteres de una cadena'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- reading characters from strings
- data streams, reading characters from string
- I/O [.NET Framework], reading characters from strings
- reading data, strings
- streams, reading characters from string
ms.assetid: 27ea5e52-6db8-42d8-980a-50bcfc7fd270
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 13a57f8ea7db91e5357ecfb20c4e907f2706f78d
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2018
ms.locfileid: "45592924"
---
# <a name="how-to-read-characters-from-a-string"></a>Cómo: Leer caracteres de una cadena
En los ejemplos de código siguientes se muestra cómo leer caracteres desde una cadena de forma sincrónica y asincrónica.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo lee trece caracteres de forma sincrónica de una cadena, los almacena en un matriz y muestra dichos caracteres. A continuación, lee los caracteres restantes de la cadena, los almacena en la matriz a partir del sexto elemento y muestra el contenido de la matriz.  
  
 [!code-cpp[Conceptual.StringReader#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.stringreader/cpp/source.cpp#1)]
 [!code-csharp[Conceptual.StringReader#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source.cs#1)]
 [!code-vb[Conceptual.StringReader#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source.vb#1)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se leen todos los caracteres e forma asincrónica desde un control <xref:System.Windows.Controls.TextBox> y se almacenan en una matriz. Luego escribe de forma asincrónica cada carácter de letra o espacio en blanco en una línea independiente seguida de un salto de línea en un control <xref:System.Windows.Controls.TextBlock>.  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source2.cs#2)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source2.vb#2)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.IO.StringReader>  
- <xref:System.IO.StringReader.Read%2A?displayProperty=nameWithType>  
- [Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md) (E/S de archivos asincrónica)  
- [Cómo: Crear una lista de directorios](https://msdn.microsoft.com/library/4d2772b1-b991-4532-a8a6-6ef733277e69)  
- [Cómo: Leer y escribir en un archivo de datos recién creado](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
- [Cómo: Abrir y anexar a un archivo de registro](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
- [Cómo: Leer texto de un archivo](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
- [Cómo: Escribir texto en un archivo](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [Cómo: Escribir caracteres en una cadena](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
- [E/S de archivos y secuencias](../../../docs/standard/io/index.md)
