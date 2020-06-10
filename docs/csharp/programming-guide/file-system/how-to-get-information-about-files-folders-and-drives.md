---
title: 'Procedimiento Obtener información sobre archivos, carpetas y unidades: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- files [C#], getting information about
ms.assetid: 22fc2da6-5494-405b-995e-c0b99142a93e
ms.openlocfilehash: 32aced17634a1406e2fce0af9c2a92f7a5eb9b40
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241622"
---
# <a name="how-to-get-information-about-files-folders-and-drives--c-programming-guide"></a>Procedimiento Obtener información sobre archivos, carpetas y unidades (Guía de programación de C#)
En .NET, puede acceder a información del sistema de archivos mediante las clases siguientes:  
  
- <xref:System.IO.FileInfo?displayProperty=nameWithType>  
  
- <xref:System.IO.DirectoryInfo?displayProperty=nameWithType>  
  
- <xref:System.IO.DriveInfo?displayProperty=nameWithType>  
  
- <xref:System.IO.Directory?displayProperty=nameWithType>  
  
- <xref:System.IO.File?displayProperty=nameWithType>  
  
 Las clases <xref:System.IO.FileInfo> y <xref:System.IO.DirectoryInfo> representan un archivo o directorio y contienen propiedades que exponen muchos de los atributos de archivo admitidos por el sistema de archivos NTFS. También contienen métodos para abrir, cerrar, mover y eliminar archivos y carpetas. Para crear instancias de estas clases, pase una cadena que represente el nombre del archivo, carpeta o unidad en el constructor:  
  
```csharp  
System.IO.DriveInfo di = new System.IO.DriveInfo(@"C:\");  
```  
  
 También puede obtener los nombres de archivos, carpetas o unidades mediante llamadas a <xref:System.IO.DirectoryInfo.GetDirectories%2A?displayProperty=nameWithType>, <xref:System.IO.DirectoryInfo.GetFiles%2A?displayProperty=nameWithType> y <xref:System.IO.DriveInfo.RootDirectory%2A?displayProperty=nameWithType>.  
  
 Las clases <xref:System.IO.Directory?displayProperty=nameWithType> y <xref:System.IO.File?displayProperty=nameWithType> proporcionan métodos estáticos para recuperar información sobre directorios y archivos.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestran diversas maneras de obtener acceso a información sobre archivos y carpetas.  
  
 [!code-csharp[csFilesandFolders#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#6)]  
  
## <a name="robust-programming"></a>Programación sólida  
 Al procesar cadenas de ruta de acceso especificadas por el usuario, también debe controlar las excepciones para las condiciones siguientes:  
  
- El nombre del archivo es incorrecto. Por ejemplo, contiene caracteres no válidos o solo espacios en blanco.  
  
- El nombre del archivo es nulo.  
  
- La longitud del nombre de archivo es superior a la longitud máxima definida por el sistema.  
  
- El nombre de archivo contiene un signo de dos puntos (:).  
  
 Si la aplicación no tiene permisos suficientes para leer el archivo especificado, el método `Exists` devuelve `false` con independencia de si existe una ruta de acceso; el método no produce una excepción.  
  
## <a name="see-also"></a>Vea también

- <xref:System.IO?displayProperty=nameWithType>
- [Guía de programación de C#](../index.md)
- [Registro y sistema de archivos (Guía de programación de C#)](./index.md)
