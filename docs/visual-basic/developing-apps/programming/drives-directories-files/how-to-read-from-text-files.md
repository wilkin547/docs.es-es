---
description: 'Más información acerca de: Procedimiento: para leer archivos de texto en Visual Basic'
title: Procedimiento para leer archivos de texto
ms.date: 07/20/2015
helpviewer_keywords:
- extended characters [Visual Basic], reading
- reading text files [Visual Basic]
- reading data, text files
- examples [Visual Basic], reading text files
- text files [Visual Basic], reading
ms.assetid: 735fe9d7-0f7a-4185-ba02-f35e580ec4b8
ms.openlocfilehash: 76f8bbbb7a0064818d324fc6dd9f1f37f7271401
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797437"
---
# <a name="how-to-read-from-text-files-in-visual-basic"></a>Cómo: Leer archivos de texto en Visual Basic

El método <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.ReadAllText%2A> del objeto `My.Computer.FileSystem` permite leer de un archivo de texto. Se puede especificar la codificación del archivo si el contenido del mismo utiliza una codificación como ASCII o UTF-8.

Si está leyendo de un archivo que incluye caracteres extendidos, deberá especificar la codificación del archivo.

> [!NOTE]
> Para leer una única línea de texto de un archivo a la vez, utilice el método <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.OpenTextFileReader%2A> del objeto `My.Computer.FileSystem`. El método `OpenTextFileReader` devuelve un objeto <xref:System.IO.StreamReader>. Puede usar el método <xref:System.IO.StreamReader.ReadLine%2A> del objeto `StreamReader` para leer de un archivo una línea a la vez. Puede buscar el final del archivo con el método <xref:System.IO.StreamReader.EndOfStream%2A> del objeto `StreamReader`.

## <a name="to-read-from-a-text-file"></a>Para leer de un archivo de texto

Utilice el método `ReadAllText` del objeto `My.Computer.FileSystem` para leer el contenido de un archivo de texto en una cadena, proporcionando la ruta de acceso. El ejemplo siguiente lee el contenido del archivo test.txt, lo coloca en una cadena y, a continuación, lo muestra en un cuadro de mensaje.

[!code-vb[VbFileIORead#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#2)]

### <a name="to-read-from-a-text-file-that-is-encoded"></a>Para leer de un archivo de texto que está codificado

Utilice el método `ReadAllText` del objeto `My.Computer.FileSystem` para leer el contenido de un archivo de texto en una cadena, proporcionando la ruta de acceso y el tipo de codificación del archivo. El ejemplo siguiente lee el contenido del archivo UTF32 test.txt, lo coloca en una cadena y, a continuación, lo muestra en un cuadro de mensaje.

[!code-vb[VbFileIORead#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#3)]

## <a name="robust-programming"></a>Programación sólida

Las condiciones siguientes pueden provocar una excepción:

- La ruta de acceso no es válida por una de las razones siguientes: es una cadena de longitud cero, sólo contiene un espacio en blanco, contiene caracteres no válidos o es una ruta de acceso de dispositivo (<xref:System.ArgumentException>).

- La ruta de acceso no es válida porque es `Nothing` (<xref:System.ArgumentNullException>).

- El archivo no existe (<xref:System.IO.FileNotFoundException>).

- El archivo está en uso por otro proceso o hay un error de E/S (<xref:System.IO.IOException>).

- La ruta supera la longitud máxima definida por el sistema (<xref:System.IO.PathTooLongException>).

- Un nombre de archivo o de directorio de la ruta de acceso contiene un signo de dos puntos (:) o tiene un formato no válido (<xref:System.NotSupportedException>).

- No hay suficiente memoria para escribir la cadena en el búfer (<xref:System.OutOfMemoryException>).

- El usuario no tiene los permisos necesarios para ver la ruta de acceso (<xref:System.Security.SecurityException>).

No tome ninguna decisión sobre el contenido del archivo basándose en su nombre. Por ejemplo, es posible que el archivo Form1.vb no sea un archivo de código fuente de Visual Basic.

Compruebe todas las entradas antes de utilizar los datos en la aplicación. Puede que el contenido del archivo no sea el esperado y que los métodos que leen el archivo produzcan un error.

## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A>
- [Lectura de archivos](reading-from-files.md)
- [Procedimiento para leer archivos de texto delimitado por comas](how-to-read-from-comma-delimited-text-files.md)
- [Procedimiento para leer archivos de texto de ancho fijo](how-to-read-from-fixed-width-text-files.md)
- [Procedimiento para leer archivos de texto con varios formatos](how-to-read-from-text-files-with-multiple-formats.md)
- [Solución del problema: leer y escribir en archivos de texto](troubleshooting-reading-from-and-writing-to-text-files.md)
- [Tutorial: Manipulación de archivos y directorios en Visual Basic](walkthrough-manipulating-files-and-directories.md)
- [Codificaciones de archivos](file-encodings.md)
