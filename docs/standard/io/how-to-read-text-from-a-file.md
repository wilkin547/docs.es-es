---
title: Procedimiento Leer texto de un archivo
description: En este artículo, verá ejemplos sobre cómo leer texto de forma sincrónica y asincrónica desde un archivo de texto mediante la clase StreamReader de .NET para aplicaciones de escritorio.
ms.date: 01/03/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- streams, reading text from files
- reading text files
- reading data, text files
- data streams, reading text from files
- I/O [.NET], reading text from files
ms.assetid: ed180baa-dfc6-4c69-a725-46e87edafb27
ms.openlocfilehash: 48b862ff77bf4ace48a5481fe9bedcf354b5654b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725344"
---
# <a name="how-to-read-text-from-a-file"></a>Procedimiento Leer texto de un archivo

En los ejemplos siguientes se muestra cómo leer texto desde un archivo de texto de forma sincrónica y asincrónica mediante .NET para aplicaciones de escritorio. En ambos ejemplos, cuando se crea la instancia de la clase <xref:System.IO.StreamReader>, se proporciona la ruta de acceso relativa o absoluta del archivo.
  
> [!NOTE]
> Estos ejemplos de código no se aplican a aplicaciones universales de Windows (UWP) porque Windows Runtime ofrece otros tipos de flujos para leer archivos o escribir en ellos. Para obtener un ejemplo en el que se muestra cómo leer el texto de un archivo en una aplicación para UWP, consulte [Inicio rápido: lectura y escritura de un archivo](/previous-versions/windows/apps/hh758325(v=win.10)). Para obtener ejemplos en los que se muestra cómo convertir entre los flujos de .NET Framework y los de Windows Runtime, consulte [Cómo: Convertir flujos de .NET Framework en flujos de Windows Runtime y viceversa](how-to-convert-between-dotnet-streams-and-winrt-streams.md).  
  
## <a name="example-synchronous-read-in-a-console-app"></a>Ejemplo: Lectura sincrónica en una aplicación de consola  

En el siguiente ejemplo se muestra una operación de lectura sincrónica dentro de una aplicación de consola. En este ejemplo se abre el archivo de texto con un lector de flujos, copia el contenido en una cadena y genera la cadena en la consola.  
  
> [!IMPORTANT]
> En el ejemplo, se da por supuesto que un archivo llamado *TestFile.txt* ya existe en la misma carpeta que la aplicación.  

:::code language="csharp" source="snippets/how-to-read-text-from-a-file/csharp/sync-console/Program.cs":::
:::code language="vb" source="snippets/how-to-read-text-from-a-file/vb/sync-console/Program.vb":::
  
## <a name="example-asynchronous-read-in-a-wpf-app"></a>Ejemplo: Lectura asincrónica en una aplicación WPF

 En el siguiente ejemplo se muestra una operación de lectura asincrónica en una aplicación de Windows Presentation Foundation (WPF).  
  
> [!IMPORTANT]
> En el ejemplo, se da por supuesto que un archivo llamado *TestFile.txt* ya existe en la misma carpeta que la aplicación.  

:::code language="csharp" source="snippets/how-to-read-text-from-a-file/csharp/async-wpf/MainWindow.xaml.cs":::
:::code language="vb" source="snippets/how-to-read-text-from-a-file/vb/async-wpf/MainWindow.xaml.vb":::
  
## <a name="see-also"></a>Vea también

- <xref:System.IO.StreamReader>  
- <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
- [E/S de archivos asincrónica](asynchronous-file-i-o.md)  
- [Cómo: Crear una lista de directorios](/previous-versions/dotnet/netframework-4.0/5cf8zcfh(v=vs.100))  
- [Inicio rápido: lectura y escritura de archivos](/previous-versions/windows/apps/hh758325(v=win.10))  
- [Cómo: Convertir flujos de .NET Framework en flujos de Windows Runtime y viceversa](how-to-convert-between-dotnet-streams-and-winrt-streams.md)  
- [Cómo: Leer y escribir en un archivo de datos recién creado](how-to-read-and-write-to-a-newly-created-data-file.md)  
- [Cómo: Abrir y anexar a un archivo de registro](how-to-open-and-append-to-a-log-file.md)  
- [Cómo: Escribir texto en un archivo](how-to-write-text-to-a-file.md)  
- [Cómo: Leer caracteres de una cadena](how-to-read-characters-from-a-string.md)  
- [Cómo: Escribir caracteres en una cadena](how-to-write-characters-to-a-string.md)  
- [E/S de archivos y secuencias](index.md)
