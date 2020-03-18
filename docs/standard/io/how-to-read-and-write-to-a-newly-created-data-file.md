---
title: Procedimiento Leer y escribir en un archivo de datos recién creado
ms.date: 01/21/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- streams, reading and writing data
- BinaryReader class, examples
- I/O [.NET Framework], reading data
- I/O [.NET Framework], writing data
- BinaryWriter class, examples
ms.assetid: e209d949-31e8-44ea-8e38-87f9093f3093
ms.openlocfilehash: 3772aeeb25d1251a13fde2a0e51a913e5e39eabc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "78155755"
---
# <a name="how-to-read-and-write-to-a-newly-created-data-file"></a>Procedimiento Leer y escribir en un archivo de datos recién creado
Las clases <xref:System.IO.BinaryWriter?displayProperty=nameWithType> y <xref:System.IO.BinaryReader?displayProperty=nameWithType> se usan para escribir y leer datos distintos de cadenas de caracteres. En el ejemplo siguiente se muestra cómo se crea un flujo de archivos vacío y cómo se escriben y se leen datos de este.

El ejemplo crea un archivo de datos llamado *Test.data* en el directorio actual, crea los objetos <xref:System.IO.BinaryWriter> y <xref:System.IO.BinaryReader> asociados y usa el objeto <xref:System.IO.BinaryWriter> para escribir los enteros de 0 a 10 en *Test.data*, que deja el puntero de archivo al final del archivo. A continuación, el objeto <xref:System.IO.BinaryReader> vuelve a establecer el puntero de archivo en el origen y lee el contenido especificado.  
  
> [!NOTE]
> Si *Test.data* ya existe en el directorio actual, se genera una excepción <xref:System.IO.IOException>. Use la opción de modo de archivo <xref:System.IO.FileMode.Create?displayProperty=nameWithType> en lugar de <xref:System.IO.FileMode.CreateNew?displayProperty=nameWithType> para crear siempre un archivo nuevo sin generar una excepción.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CS/source6.cs#7)]
 [!code-vb[System.IO.BinaryReaderWriter#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/VB/source6.vb#7)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.IO.BinaryReader>  
- <xref:System.IO.BinaryWriter>  
- <xref:System.IO.FileStream>  
- <xref:System.IO.FileStream.Seek%2A?displayProperty=nameWithType>  
- <xref:System.IO.SeekOrigin>  
- [Cómo: Enumerar directorios y archivos](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
- [Cómo: Abrir y anexar a un archivo de registro](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
- [Cómo: Leer texto de un archivo](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
- [Cómo: Escribir texto en un archivo](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [Cómo: Leer caracteres de una cadena](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
- [Cómo: Escribir caracteres en una cadena](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
- [E/S de archivos y secuencias](../../../docs/standard/io/index.md)
