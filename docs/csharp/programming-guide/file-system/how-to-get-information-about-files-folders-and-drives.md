---
title: "Cómo: Obtener información sobre archivos, carpetas y unidades (Guía de programación de C#) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- files [C#], getting information about
ms.assetid: 22fc2da6-5494-405b-995e-c0b99142a93e
caps.latest.revision: 30
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 16950f835938846804ade1a8ad23d907aa69b9c3
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-get-information-about-files-folders-and-drives--c-programming-guide"></a>Cómo: Obtener información sobre archivos, carpetas y unidades (Guía de programación de C#)
En .NET Framework, puede tener acceso a información del sistema de archivos mediante las clases siguientes:  
  
-   <xref:System.IO.FileInfo?displayProperty=fullName>  
  
-   <xref:System.IO.DirectoryInfo?displayProperty=fullName>  
  
-   <xref:System.IO.DriveInfo?displayProperty=fullName>  
  
-   <xref:System.IO.Directory?displayProperty=fullName>  
  
-   <xref:System.IO.File?displayProperty=fullName>  
  
 Las clases <xref:System.IO.FileInfo> y <xref:System.IO.DirectoryInfo> representan un archivo o directorio y contienen propiedades que exponen muchos de los atributos de archivo admitidos por el sistema de archivos NTFS. También contienen métodos para abrir, cerrar, mover y eliminar archivos y carpetas. Para crear instancias de estas clases, pase una cadena que represente el nombre del archivo, carpeta o unidad en el constructor:  
  
```csharp  
System.IO.DriveInfo di = new System.IO.DriveInfo(@"C:\");  
```  
  
 También puede obtener los nombres de archivos, carpetas o unidades mediante llamadas a <xref:System.IO.DirectoryInfo.GetDirectories%2A?displayProperty=fullName>, <xref:System.IO.DirectoryInfo.GetFiles%2A?displayProperty=fullName> y <xref:System.IO.DriveInfo.RootDirectory%2A?displayProperty=fullName>.  
  
 Las clases <xref:System.IO.Directory?displayProperty=fullName> y <xref:System.IO.File?displayProperty=fullName> proporcionan métodos estáticos para recuperar información sobre los directorios y los archivos.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestran diversas maneras de obtener acceso a información sobre archivos y carpetas.  
  
 [!code-cs[csFilesandFolders#6](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-get-information-about-files-folders-and-drives_1.cs)]  
  
## <a name="robust-programming"></a>Programación sólida  
 Al procesar cadenas de ruta de acceso especificadas por el usuario, también debe controlar las excepciones para las condiciones siguientes:  
  
-   El nombre del archivo es incorrecto. Por ejemplo, contiene caracteres no válidos o solo espacios en blanco.  
  
-   El nombre del archivo es nulo.  
  
-   La longitud del nombre de archivo es superior a la longitud máxima definida por el sistema.  
  
-   El nombre de archivo contiene un signo de dos puntos (:).  
  
 Si la aplicación no tiene permisos suficientes para leer el archivo especificado, el método `Exists` devuelve `false` con independencia de si existe una ruta de acceso; el método no produce una excepción.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IO?displayProperty=fullName>   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Registro y sistema de archivos (Guía de programación de C#)](../../../csharp/programming-guide/file-system/index.md)
