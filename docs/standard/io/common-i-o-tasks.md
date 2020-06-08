---
title: Tareas de E/S comunes
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- I/O, common tasks
ms.assetid: bf00c380-706a-4e38-b829-454a480629fc
ms.openlocfilehash: 9474d6c0340583e285a6dc47933c602f799f121d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287433"
---
# <a name="common-io-tasks"></a>Tareas de E/S comunes
El espacio de nombres <xref:System.IO> proporciona varias clases que permiten realizar diferentes acciones, como leer y escribir, en archivos, directorios y secuencias. Para más información, vea [E/S de archivos y secuencias](index.md).  
  
## <a name="common-file-tasks"></a>Tareas de archivo comunes  
  
|Para...|Vea el ejemplo de este tema...|  
|-------------------|--------------------------------------|  
|Crear un archivo de texto|Método<xref:System.IO.File.CreateText%2A?displayProperty=nameWithType><br /><br /> Método<xref:System.IO.FileInfo.CreateText%2A?displayProperty=nameWithType><br /><br /> Método<xref:System.IO.File.Create%2A?displayProperty=nameWithType><br /><br /> Método<xref:System.IO.FileInfo.Create%2A?displayProperty=nameWithType>|  
|Escribir en un archivo de texto|[Cómo: Escribir texto en un archivo](how-to-write-text-to-a-file.md)<br /><br /> [Cómo: Escribir un archivo de texto (C++/CLI)](/cpp/dotnet/how-to-write-a-text-file-cpp-cli)|  
|Leer de un archivo de texto|[Cómo: Leer texto de un archivo](how-to-read-text-from-a-file.md)|  
|Anexar texto a un archivo|[Cómo: Abrir y anexar a un archivo de registro](how-to-open-and-append-to-a-log-file.md)<br /><br /> Método<xref:System.IO.File.AppendText%2A?displayProperty=nameWithType><br /><br /> Método<xref:System.IO.FileInfo.AppendText%2A?displayProperty=nameWithType>|  
|Cambiar el nombre de un archivo o moverlo|Método<xref:System.IO.File.Move%2A?displayProperty=nameWithType><br /><br /> Método<xref:System.IO.FileInfo.MoveTo%2A?displayProperty=nameWithType>|  
|Eliminar un archivo|Método<xref:System.IO.File.Delete%2A?displayProperty=nameWithType><br /><br /> Método<xref:System.IO.FileInfo.Delete%2A?displayProperty=nameWithType>|  
|Copiar un archivo|Método<xref:System.IO.File.Copy%2A?displayProperty=nameWithType><br /><br /> Método<xref:System.IO.FileInfo.CopyTo%2A?displayProperty=nameWithType>|  
|Obtener el tamaño de un archivo|Propiedad <xref:System.IO.FileInfo.Length%2A?displayProperty=nameWithType>|  
|Obtener los atributos de un archivo|Método<xref:System.IO.File.GetAttributes%2A?displayProperty=nameWithType>|  
|Establecer los atributos de un archivo|Método<xref:System.IO.File.SetAttributes%2A?displayProperty=nameWithType>|  
|Determinar si existe un archivo|Método<xref:System.IO.File.Exists%2A?displayProperty=nameWithType>|  
|Leer de un archivo binario|[Cómo: Leer y escribir en un archivo de datos recién creado](how-to-read-and-write-to-a-newly-created-data-file.md)|  
|Escribir en un archivo binario|[Cómo: Leer y escribir en un archivo de datos recién creado](how-to-read-and-write-to-a-newly-created-data-file.md)|  
|Recuperar la extensión de un nombre de archivo|Método<xref:System.IO.Path.GetExtension%2A?displayProperty=nameWithType>|  
|Recuperar la ruta de acceso completa de un archivo|Método<xref:System.IO.Path.GetFullPath%2A?displayProperty=nameWithType>|  
|Recuperar el nombre y la extensión de un archivo de una ruta de acceso|Método<xref:System.IO.Path.GetFileName%2A?displayProperty=nameWithType>|  
|Cambiar la extensión de un archivo|Método<xref:System.IO.Path.ChangeExtension%2A?displayProperty=nameWithType>|  
  
## <a name="common-directory-tasks"></a>Tareas de directorio comunes  
  
|Para...|Vea el ejemplo de este tema...|  
|-------------------|--------------------------------------|  
|Obtener acceso a un archivo de una carpeta especial como Mis documentos|[Cómo: Escribir texto en un archivo](how-to-write-text-to-a-file.md)|  
|Creación de un directorio|Método<xref:System.IO.Directory.CreateDirectory%2A?displayProperty=nameWithType><br /><br /> Propiedad <xref:System.IO.FileInfo.Directory%2A?displayProperty=nameWithType>|  
|Crear un subdirectorio|Método<xref:System.IO.DirectoryInfo.CreateSubdirectory%2A?displayProperty=nameWithType>|  
|Cambiar el nombre de un directorio o moverlo|Método<xref:System.IO.Directory.Move%2A?displayProperty=nameWithType><br /><br /> Método<xref:System.IO.DirectoryInfo.MoveTo%2A?displayProperty=nameWithType>|  
|Copiar un directorio|[Copiar directorios](how-to-copy-directories.md)|  
|Eliminar un directorio|Método<xref:System.IO.Directory.Delete%2A?displayProperty=nameWithType><br /><br /> Método<xref:System.IO.DirectoryInfo.Delete%2A?displayProperty=nameWithType>|  
|Ver los archivos y los subdirectorios de un directorio|[Enumerar directorios y archivos](how-to-enumerate-directories-and-files.md)|  
|Buscar el tamaño de un directorio|Clase <xref:System.IO.Directory?displayProperty=nameWithType>|  
|Determinar si existe un directorio|Método<xref:System.IO.Directory.Exists%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a>Vea también

- [E/S de archivos y secuencias](index.md)
- [Crear secuencias](composing-streams.md)
- [Asynchronous File I/O](asynchronous-file-i-o.md)
