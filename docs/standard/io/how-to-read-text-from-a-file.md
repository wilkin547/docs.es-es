---
title: 'Cómo: Leer texto de un archivo'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- streams, reading text from files
- reading text files
- reading data, text files
- data streams, reading text from files
- I/O [.NET Framework], reading text from files
ms.assetid: ed180baa-dfc6-4c69-a725-46e87edafb27
caps.latest.revision: 23
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: e1058879d4af8aac12baf24d10a0c22894351e6f
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="how-to-read-text-from-a-file"></a>Cómo: Leer texto de un archivo
En los ejemplos siguientes se muestra cómo leer texto desde un archivo de texto de forma sincrónica y asincrónica mediante .NET para aplicaciones de escritorio. En ambos ejemplos, cuando se crea la instancia de la clase <xref:System.IO.StreamReader>, se proporciona la ruta de acceso relativa o absoluta del archivo. En los ejemplos siguientes se supone que el archivo denominado TestFile.txt está en la misma carpeta que la aplicación.  
  
 Estos ejemplos de código no se pueden aplicar al desarrollo de aplicaciones de la Tienda Windows porque Windows Runtime ofrece diferentes tipos de secuencias al leer archivos o escribir en ellos. Para obtener un ejemplo acerca de cómo leer el texto de un archivo en el contexto de una aplicación de la Tienda Windows, vea [Inicio rápido: lectura y escritura de un archivo](http://msdn.microsoft.com/library/windows/apps/hh758325.aspx). Para obtener ejemplos que muestren cómo convertir entre secuencias de .NET Framework y secuencias de Windows Runtime, consulte [Cómo: Convertir entre secuencias .NET Framework y secuencias de Windows Runtime](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md).  
  
## <a name="example"></a>Ejemplo  
 El primer ejemplo muestra una operación de lectura sincrónica dentro de una aplicación de consola. En este ejemplo, el archivo de texto se abre con un lector de secuencias, el contenido se copia en una cadena y la cadena se envía a la consola.  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source3.cs#3)]
 [!code-vb[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source3.vb#3)]  
  
## <a name="example"></a>Ejemplo  
 El segundo ejemplo muestra una operación de lectura asincrónica dentro de una aplicación de Windows Presentation Foundation (WPF).  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source6.cs#6)]
 [!code-vb[Conceptual.BasicIO.TextFiles#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source6.vb#6)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IO.StreamReader>  
 <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
 [Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md) (E/S de archivos asincrónica)  
 [Cómo: Crear una lista de directorios](https://msdn.microsoft.com/library/4d2772b1-b991-4532-a8a6-6ef733277e69)  
 [Inicio rápido: lectura y escritura de un archivo](http://msdn.microsoft.com/library/windows/apps/hh758325.aspx)  
 [Convertir flujos de .NET Framework en flujos de Windows Runtime y viceversa](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)  
 [Cómo: Leer y escribir en un archivo de datos recién creado](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
 [Cómo: Abrir y anexar a un archivo de registro](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
 [Cómo: Escribir texto en un archivo](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [Cómo: Leer caracteres de una cadena](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
 [Cómo: Escribir caracteres en una cadena](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
 [E/S de archivos y secuencias](../../../docs/standard/io/index.md)
