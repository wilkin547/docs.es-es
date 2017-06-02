---
title: "Tareas de E/S comunes | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "E/S, tareas comunes"
ms.assetid: bf00c380-706a-4e38-b829-454a480629fc
caps.latest.revision: 15
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
---
# Tareas de E/S comunes
El espacio de nombres <xref:System.IO> proporciona varias clases que permiten realizar diferentes acciones, como leer y escribir, en archivos, directorios y secuencias.  Para obtener más información, vea [E\/S de archivos y secuencias](../../../docs/standard/io/index.md).  
  
## Tareas de archivo comunes  
  
|Para...|Vea el ejemplo de este tema...|  
|-------------|------------------------------------|  
|Crear un archivo de texto|Método <xref:System.IO.File.CreateText%2A?displayProperty=fullName><br /><br /> Método <xref:System.IO.FileInfo.CreateText%2A?displayProperty=fullName><br /><br /> Método <xref:System.IO.File.Create%2A?displayProperty=fullName><br /><br /> Método <xref:System.IO.FileInfo.Create%2A?displayProperty=fullName>|  
|Escribir en un archivo de texto|[Cómo: Escribir texto en un archivo](../../../docs/standard/io/how-to-write-text-to-a-file.md)<br /><br /> [Cómo: Escribir un archivo de texto](../Topic/How%20to:%20Write%20a%20Text%20File%20\(C++-CLI\).md)|  
|Leer de un archivo de texto|[Cómo: Leer texto de un archivo](../../../docs/standard/io/how-to-read-text-from-a-file.md)|  
|Anexar texto a un archivo|[Cómo: Abrir y anexar a un archivo de registro](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)<br /><br /> Método <xref:System.IO.File.AppendText%2A?displayProperty=fullName><br /><br /> Método <xref:System.IO.FileInfo.AppendText%2A?displayProperty=fullName>|  
|Cambiar el nombre de un archivo o moverlo|Método <xref:System.IO.File.Move%2A?displayProperty=fullName><br /><br /> Método <xref:System.IO.FileInfo.MoveTo%2A?displayProperty=fullName>|  
|Eliminar un archivo|Método <xref:System.IO.File.Delete%2A?displayProperty=fullName><br /><br /> Método <xref:System.IO.FileInfo.Delete%2A?displayProperty=fullName>|  
|Copiar un archivo|Método <xref:System.IO.File.Copy%2A?displayProperty=fullName><br /><br /> Método <xref:System.IO.FileInfo.CopyTo%2A?displayProperty=fullName>|  
|Obtener el tamaño de un archivo|Propiedad <xref:System.IO.FileInfo.Length%2A?displayProperty=fullName>|  
|Obtener los atributos de un archivo|Método <xref:System.IO.File.GetAttributes%2A?displayProperty=fullName>|  
|Establecer los atributos de un archivo|Método <xref:System.IO.File.SetAttributes%2A?displayProperty=fullName>|  
|Determinar si existe un archivo|Método <xref:System.IO.File.Exists%2A?displayProperty=fullName>|  
|Leer de un archivo binario|[Cómo: Leer y escribir en un archivo de datos recién creado](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)|  
|Escribir en un archivo binario|[Cómo: Leer y escribir en un archivo de datos recién creado](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)|  
|Recuperar la extensión de un nombre de archivo|Método <xref:System.IO.Path.GetExtension%2A?displayProperty=fullName>|  
|Recuperar la ruta de acceso completa de un archivo|Método <xref:System.IO.Path.GetFullPath%2A?displayProperty=fullName>|  
|Recuperar el nombre y la extensión de un archivo de una ruta de acceso|Método <xref:System.IO.Path.GetFileName%2A?displayProperty=fullName>|  
|Cambiar la extensión de un archivo|Método <xref:System.IO.Path.ChangeExtension%2A?displayProperty=fullName>|  
  
## Tareas de directorio comunes  
  
|Para...|Vea el ejemplo de este tema...|  
|-------------|------------------------------------|  
|Obtener acceso a un archivo de una carpeta especial como Mis documentos|[Cómo: Escribir texto en un archivo](../../../docs/standard/io/how-to-write-text-to-a-file.md)|  
|Crear un directorio|Método <xref:System.IO.Directory.CreateDirectory%2A?displayProperty=fullName><br /><br /> Propiedad <xref:System.IO.FileInfo.Directory%2A?displayProperty=fullName>|  
|Crear un subdirectorio|Método <xref:System.IO.DirectoryInfo.CreateSubdirectory%2A?displayProperty=fullName>|  
|Cambiar el nombre de un directorio o moverlo|Método <xref:System.IO.Directory.Move%2A?displayProperty=fullName><br /><br /> Método <xref:System.IO.DirectoryInfo.MoveTo%2A?displayProperty=fullName>|  
|Copiar un directorio|[Cómo: Copiar directorios](../../../docs/standard/io/how-to-copy-directories.md)|  
|Eliminar un directorio|Método <xref:System.IO.Directory.Delete%2A?displayProperty=fullName><br /><br /> Método <xref:System.IO.DirectoryInfo.Delete%2A?displayProperty=fullName>|  
|Ver los archivos y los subdirectorios de un directorio|[Cómo: Enumerar directorios y archivos](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)|  
|Buscar el tamaño de un directorio|Clase <xref:System.IO.Directory?displayProperty=fullName>|  
|Determinar si existe un directorio|Método <xref:System.IO.Directory.Exists%2A?displayProperty=fullName>|  
  
## Vea también  
 [E\/S de archivos y secuencias](../../../docs/standard/io/index.md)   
 [Crear secuencias](../../../docs/standard/io/composing-streams.md)   
 [E\/S de archivos asincrónica](../../../docs/standard/io/e-s-de-archivos-asincrónica.md)