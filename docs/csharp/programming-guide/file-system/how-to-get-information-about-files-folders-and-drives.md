---
title: "C&#243;mo: Obtener informaci&#243;n sobre archivos, carpetas y unidades (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "archivos [C#], obtener información sobre"
ms.assetid: 22fc2da6-5494-405b-995e-c0b99142a93e
caps.latest.revision: 30
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 30
---
# C&#243;mo: Obtener informaci&#243;n sobre archivos, carpetas y unidades (Gu&#237;a de programaci&#243;n de C#)
En .NET Framework, puede obtener acceso a la información del sistema de archivos usando las clases siguientes:  
  
-   <xref:System.IO.FileInfo?displayProperty=fullName>  
  
-   <xref:System.IO.DirectoryInfo?displayProperty=fullName>  
  
-   <xref:System.IO.DriveInfo?displayProperty=fullName>  
  
-   <xref:System.IO.Directory?displayProperty=fullName>  
  
-   <xref:System.IO.File?displayProperty=fullName>  
  
 Las clases <xref:System.IO.DirectoryInfo> y <xref:System.IO.FileInfo> representan un archivo o directorio y contienen propiedades que exponen muchos de los atributos de archivo admitidos por el sistema de archivos NTFS.  También contienen métodos para abrir, cerrar, mover y eliminar archivos y carpetas.  Para crear instancias de estas clases, pase al constructor una cadena que represente el nombre del archivo, carpeta o unidad:  
  
```c#  
System.IO.DriveInfo di = new System.IO.DriveInfo(@"C:\");  
```  
  
 Para obtener los nombres de los archivos, las carpetas o las unidades también puede utilizar las llamadas a <xref:System.IO.DirectoryInfo.GetDirectories%2A?displayProperty=fullName>, <xref:System.IO.DirectoryInfo.GetFiles%2A?displayProperty=fullName> y <xref:System.IO.DriveInfo.RootDirectory%2A?displayProperty=fullName>.  
  
 Las clases <xref:System.IO.File?displayProperty=fullName> y <xref:System.IO.Directory?displayProperty=fullName> proporcionan métodos estáticos para recuperar información sobre directorios y archivos.  
  
## Ejemplo  
 En el ejemplo siguiente se muestran varias maneras de obtener acceso a información sobre archivos y carpetas.  
  
 [!code-cs[csFilesandFolders#6](../../../csharp/programming-guide/file-system/codesnippet/csharp/csFilesFolders/FileIteration.cs#6)]  
  
## Programación eficaz  
 Al procesar cadenas de ruta de acceso especificadas por el usuario, también debería controlar las excepciones para las condiciones siguientes:  
  
-   El nombre del archivo es incorrecto.  Por ejemplo, contiene caracteres no válidos o está compuesto sólo por espacios en blanco.  
  
-   El nombre del archivo es null.  
  
-   La longitud del nombre de archivo es superior a la longitud máxima definida por el sistema.  
  
-   El nombre de archivo contiene un signo de dos puntos \(:\).  
  
 Si la aplicación no tiene permisos suficientes para leer el archivo especificado, el método `Exists` devuelve `false` exista o no una ruta de acceso, pero no producirá una excepción.  
  
## Vea también  
 <xref:System.IO?displayProperty=fullName>   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Registro y sistema de archivos](../../../csharp/programming-guide/file-system/file-system-and-the-registry.md)