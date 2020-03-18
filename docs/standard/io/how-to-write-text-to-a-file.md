---
title: Procedimiento Escribir texto en un archivo
ms.date: 01/04/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- writing text to files
- I/O [.NET Framework], writing text to files
- streams, writing text to files
- data streams, writing text to files
ms.assetid: 060cbe06-2adf-4337-9e7b-961a5c840208
ms.openlocfilehash: ba1c1815f0e49c02d1f0ee3c48ba01b7c2f5e727
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "78160253"
---
# <a name="how-to-write-text-to-a-file"></a>Procedimiento Escribir texto en un archivo
En este tema se muestran diferentes maneras de escribir texto en un archivo para una aplicación .NET.

Las clases y los métodos siguientes normalmente se usan para escribir texto en un archivo:  
  
- <xref:System.IO.StreamWriter> contiene métodos para escribir en un archivo de forma sincrónica (<xref:System.IO.StreamWriter.Write%2A> y <xref:System.IO.TextWriter.WriteLine%2A>) o asincrónica (<xref:System.IO.StreamWriter.WriteAsync%2A> y <xref:System.IO.StreamWriter.WriteLineAsync%2A>).  
  
- <xref:System.IO.File> proporciona métodos estáticos para escribir texto en un archivo (por ejemplo, <xref:System.IO.File.WriteAllLines%2A> y <xref:System.IO.File.WriteAllText%2A>), o bien para anexar texto a un archivo (<xref:System.IO.File.AppendAllLines%2A>, <xref:System.IO.File.AppendAllText%2A> y <xref:System.IO.File.AppendText%2A>).  
  
- <xref:System.IO.Path> es para cadenas que contienen información de la ruta de acceso al archivo o directorio. Contiene el método <xref:System.IO.Path.Combine%2A> y, en .NET Core 2.1 y versiones posteriores, los métodos <xref:System.IO.Path.Join%2A> y <xref:System.IO.Path.TryJoin%2A>, que permiten la concatenación de cadenas para crear una ruta de acceso de archivo o directorio.

> [!NOTE]
> En los ejemplos siguientes solo se muestra la cantidad mínima de código necesario. Normalmente, una aplicación real ofrece una comprobación de errores y un control de excepciones más exhaustivos.  
  
## <a name="example-synchronously-write-text-with-streamwriter"></a>Ejemplo: Escritura de texto con StreamWriter de forma sincrónica

En el ejemplo siguiente se muestra cómo usar la clase <xref:System.IO.StreamWriter> para escribir texto en un archivo nuevo de forma sincrónica, una línea a la vez. Como en la instrucción <xref:System.IO.StreamWriter> se declara el objeto `using` y se crea una instancia de este, se invoca el método <xref:System.IO.StreamWriter.Dispose%2A>, que automáticamente vacía y cierra el flujo.  

[!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/write.cs)]
[!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/write.vb)]  

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

## <a name="example-synchronously-append-text-with-streamwriter"></a>Ejemplo: Anexión de texto con StreamWriter de forma sincrónica

En el ejemplo siguiente se muestra cómo usar la clase <xref:System.IO.StreamWriter> para anexar de forma sincrónica texto al archivo de texto creado en el primer ejemplo.

[!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/append.cs)]
[!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/append.vb)]  

## <a name="example-asynchronously-write-text-with-streamwriter"></a>Ejemplo: Escritura de texto con StreamWriter de forma asincrónica

En el ejemplo siguiente se muestra cómo escribir texto en un archivo nuevo de forma asincrónica mediante la clase <xref:System.IO.StreamWriter> . Para invocar el método <xref:System.IO.StreamWriter.WriteAsync%2A>, la llamada al método debe estar dentro de un método `async`. En el ejemplo de C# se requiere C# 7.1 o una versión posterior, lo que agrega compatibilidad para el modificador `async` en el punto de entrada del programa.

[!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/async.cs)]
[!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/async.vb)]  

## <a name="example-write-and-append-text-with-the-file-class"></a>Ejemplo: Escritura y anexión de texto a la clase File

En el ejemplo siguiente se muestra cómo escribir texto en un archivo nuevo y anexar nuevas líneas de texto en el mismo archivo con la clase <xref:System.IO.File> . Los métodos <xref:System.IO.File.WriteAllText%2A> y <xref:System.IO.File.AppendAllLines%2A> abren y cierran el archivo automáticamente. Si ya existe la ruta de acceso que se proporciona al método <xref:System.IO.File.WriteAllText%2A>, se sobrescribe el archivo.  

[!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/file.cs)]
[!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/file.vb)]  

## <a name="see-also"></a>Vea también

- <xref:System.IO.StreamWriter>
- <xref:System.IO.Path>
- <xref:System.IO.File.CreateText%2A?displayProperty=nameWithType>
- [Cómo: Enumerar directorios y archivos](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)
- [Cómo: Leer y escribir en un archivo de datos recién creado](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)
- [Cómo: Abrir y anexar a un archivo de registro](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)
- [Cómo: Leer texto de un archivo](../../../docs/standard/io/how-to-read-text-from-a-file.md)
- [E/S de archivos y secuencias](../../../docs/standard/io/index.md)
