---
title: 'Cómo: Leer de un archivo de texto (Guía de programación de C#)'
ms.date: 07/20/2015
f1_keywords:
- StreamReader.ReadToEnd
helpviewer_keywords:
- text files, writing to
- reading text files
- reading data, text files
- text files, reading
ms.assetid: 92246c5b-e819-4eea-9370-1a9460e12de3
ms.openlocfilehash: a42f98a81ff9e9bdbbf6c61554667aa223c7c269
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-read-from-a-text-file-c-programming-guide"></a>Cómo: Leer de un archivo de texto (Guía de programación de C#)
En este ejemplo se lee el contenido de un archivo de texto con los métodos estáticos <xref:System.IO.File.ReadAllText%2A> y <xref:System.IO.File.ReadAllLines%2A> de la clase <xref:System.IO.File?displayProperty=nameWithType>.  
  
 Para obtener un ejemplo en el que se usa <xref:System.IO.StreamReader>, vea [Cómo: Leer un archivo de texto línea a línea](../../../csharp/programming-guide/file-system/how-to-read-a-text-file-one-line-at-a-time.md).  
  
> [!NOTE]
>  Los archivos que se usan en este ejemplo se crean en el tema [Cómo: Escribir en un archivo texto](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md).  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csFilesandFolders#4](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-read-from-a-text-file_1.cs)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Copie el código y péguelo en una aplicación de consola de C#.  
  
 Si no está usando los archivos de texto de [Cómo: Escribir en un archivo texto](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md), reemplace el argumento a `ReadAllText` y a `ReadAllLines` con la ruta de acceso adecuada y el nombre de archivo en el equipo.  
  
## <a name="robust-programming"></a>Programación sólida  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   El archivo no existe o no existe en la ubicación especificada. Compruebe la ruta de acceso y la ortografía del nombre de archivo.  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 No confíe en el nombre de un archivo para determinar el contenido del archivo. Por ejemplo, el archivo `myFile.cs` puede que no sea un archivo de código fuente de C#.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IO?displayProperty=nameWithType>  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Registro y sistema de archivos (Guía de programación de C#)](../../../csharp/programming-guide/file-system/index.md)
