---
title: Procedimiento Leer texto de un archivo
ms.date: 01/03/2019
ms.technology: dotnet-standard
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
ms.openlocfilehash: 49ea989a2b11c6572dc08970cf96e2df5f4fa024
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706665"
---
# <a name="how-to-read-text-from-a-file"></a>Procedimiento Leer texto de un archivo
En los ejemplos siguientes se muestra cómo leer texto desde un archivo de texto de forma sincrónica y asincrónica mediante .NET para aplicaciones de escritorio. En ambos ejemplos, cuando se crea la instancia de la clase <xref:System.IO.StreamReader>, se proporciona la ruta de acceso relativa o absoluta del archivo. 
  
> [!NOTE]
> Estos ejemplos de código no se pueden aplicar al desarrollo de aplicaciones universales de Windows (UWP) porque Windows Runtime ofrece diferentes tipos de flujos para leer archivos o escribir en ellos. Para obtener un ejemplo en el que se muestra cómo leer el texto de un archivo en una aplicación para UWP, consulte [Inicio rápido: lectura y escritura de un archivo](https://docs.microsoft.com/previous-versions/windows/apps/hh758325(v=win.10)). Para obtener ejemplos en los que se muestra cómo convertir entre los flujos de .NET Framework y los de Windows Runtime, consulte [Cómo: Convertir flujos de .NET Framework en flujos de Windows Runtime y viceversa](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md).  
  
## <a name="example-synchronous-read-in-a-console-app"></a>Ejemplo: Lectura sincrónica en una aplicación de consola  
En el siguiente ejemplo se muestra una operación de lectura sincrónica dentro de una aplicación de consola. En este ejemplo se abre el archivo de texto con un lector de flujos, copia el contenido en una cadena y genera la cadena en la consola.  
  
> [!IMPORTANT]
> En el ejemplo, se da por supuesto que un archivo llamado *TestFile.txt* ya existe en la misma carpeta que la aplicación.  

 [!code-csharp[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source3.cs#3)]
 [!code-vb[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source3.vb#3)]  
  
## <a name="example-asynchronous-read-in-a-wpf-app"></a>Ejemplo: Lectura asincrónica en una aplicación WPF 
 En el siguiente ejemplo se muestra una operación de lectura asincrónica en una aplicación de Windows Presentation Foundation (WPF).  
  
> [!IMPORTANT]
> En el ejemplo, se da por supuesto que un archivo llamado *TestFile.txt* ya existe en la misma carpeta que la aplicación.  

 [!code-csharp[TextFiles](../../../samples/snippets/csharp/VS_Snippets_Wpf/TextFiles/MainWindow.xaml.cs)]
 [!code-vb[TextFiles](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextFiles/MainWindow.xaml.vb)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.IO.StreamReader>  
- <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
- [E/S de archivos asincrónica](../../../docs/standard/io/asynchronous-file-i-o.md)  
- [Cómo: Crear una lista de directorios](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5cf8zcfh(v=vs.100))  
- [Inicio rápido: lectura y escritura de archivos](https://docs.microsoft.com/previous-versions/windows/apps/hh758325%28v=win.10%29)  
- [Cómo: Convertir flujos de .NET Framework en flujos de Windows Runtime y viceversa](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)  
- [Cómo: Leer y escribir en un archivo de datos recién creado](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
- [Cómo: Abrir y anexar a un archivo de registro](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
- [Cómo: Escribir texto en un archivo](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [Cómo: Leer caracteres de una cadena](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
- [Cómo: Escribir caracteres en una cadena](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
- [E/S de archivos y secuencias](../../../docs/standard/io/index.md)
