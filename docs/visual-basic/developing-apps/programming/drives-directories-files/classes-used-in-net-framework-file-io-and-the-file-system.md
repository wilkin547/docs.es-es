---
title: Clases utilizadas en el sistema de archivos y la E/S de archivos en .NET Framework
ms.date: 07/20/2015
helpviewer_keywords:
- file I/O classes
ms.assetid: 4a5ca924-eea8-4a95-a5f0-6ac10de276a3
ms.openlocfilehash: 2c696d5b8c83ae55caf61e4710630ad1e34c088d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401776"
---
# <a name="classes-used-in-net-framework-file-io-and-the-file-system-visual-basic"></a>Clases utilizadas en el sistema de archivos y la E/S de archivos en .NET Framework (Visual Basic)

En las tablas siguientes se incluyen las clases usadas más comúnmente para las operaciones de E/S de archivos en .NET Framework, clasificadas en clases de E/S de archivos, clases usadas para crear secuencias y clases usadas para leer y escribir en secuencias.  
  
Para obtener una lista más completa, vea [Información general de la biblioteca de clases](../../../../standard/class-library-overview.md).  
  
## <a name="basic-io-classes-for-files-drives-and-directories"></a>Clases básicas de E/S para archivos, unidades y directorios  

 En la tabla siguiente se muestran y describen las clases principales usadas para las operaciones de E/S de archivos.  
  
|Clase|Description|  
|-----------|-----------------|  
|<xref:System.IO.Directory?displayProperty=nameWithType>|Proporciona métodos estáticos para crear, mover y enumerar en directorios y subdirectorios.|  
|<xref:System.IO.DirectoryInfo?displayProperty=nameWithType>|Proporciona métodos de instancia para crear, mover y enumerar en directorios y subdirectorios.|  
|<xref:System.IO.DriveInfo?displayProperty=nameWithType>|Proporciona métodos de instancia para crear, mover y enumerar entre unidades.|  
|<xref:System.IO.File?displayProperty=nameWithType>|Proporciona métodos estáticos para crear, copiar, eliminar, mover y abrir archivos, y ayuda en la creación de una `FileStream`.|  
|<xref:System.IO.FileAccess?displayProperty=nameWithType>|Define constantes de acceso de lectura, de escritura y de lectura/escritura para un archivo.|  
|<xref:System.IO.FileAttributes?displayProperty=nameWithType>|Proporciona atributos para archivos y directorios, como `Archive`, `Hidden` y `ReadOnly`.|  
|<xref:System.IO.FileInfo?displayProperty=nameWithType>|Proporciona métodos estáticos para crear, copiar, eliminar, mover y abrir archivos, y ayuda en la creación de una `FileStream`.|  
|<xref:System.IO.FileMode?displayProperty=nameWithType>|Controla cómo se abre un archivo. Este parámetro se especifica en muchos de los constructores para `FileStream` e `IsolatedStorageFileStream`, y para los métodos `Open` de <xref:System.IO.File> y <xref:System.IO.FileInfo>.|  
|<xref:System.IO.FileShare?displayProperty=nameWithType>|Define las constantes para controlar el tipo de acceso que pueden tener otras secuencias de archivo al mismo archivo.|  
|<xref:System.IO.Path?displayProperty=nameWithType>|Proporciona métodos y propiedades para procesar cadenas de directorio.|  
|<xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType>|Controla el acceso a archivos y carpetas mediante la definición de los permisos <xref:System.Security.Permissions.FileIOPermissionAttribute.Read%2A>, <xref:System.Security.Permissions.FileIOPermissionAttribute.Write%2A>, <xref:System.Security.Permissions.FileIOPermissionAttribute.Append%2A> y <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A>.|  
  
## <a name="classes-used-to-create-streams"></a>Clases usadas para crear secuencias  

 En la tabla siguiente se muestran y describen las clases principales usadas para crear secuencias.  
  
|Clase|Description|  
|-----------|-----------------|  
|<xref:System.IO.BufferedStream?displayProperty=nameWithType>|Agrega una capa de almacenamiento en búfer para las operaciones de lectura y escritura en otra secuencia.|  
|<xref:System.IO.FileStream?displayProperty=nameWithType>|Admite el acceso aleatorio a archivos a través de su método <xref:System.IO.FileStream.Seek%2A>. <xref:System.IO.FileStream> abre los archivos sincrónicamente de manera predeterminada, pero también admite operaciones asincrónicas.|  
|<xref:System.IO.MemoryStream?displayProperty=nameWithType>|Crea una secuencia cuya memoria auxiliar es la memoria, en lugar de un archivo.|  
|<xref:System.Net.Sockets.NetworkStream?displayProperty=nameWithType>|Proporciona el flujo de datos subyacente para el acceso a través de la red.|  
|<xref:System.Security.Cryptography.CryptoStream?displayProperty=nameWithType>|Define un flujo que vincula flujos de datos a transformaciones criptográficas.|  
  
## <a name="classes-used-to-read-from-and-write-to-streams"></a>Clases usadas para leer y escribir en secuencias  

 En la tabla siguiente se muestran las clases concretas usadas para leer y escribir en los archivos con secuencias.  
  
|**Clase**|**Descripción**|  
|---------------|---------------------|  
|<xref:System.IO.BinaryReader?displayProperty=nameWithType>|Lee cadenas codificadas y tipos de datos primitivos de una secuencia <xref:System.IO.FileStream>.|  
|<xref:System.IO.BinaryWriter?displayProperty=nameWithType>|Escribe cadenas codificadas y tipos de datos primitivos en una secuencia <xref:System.IO.FileStream>.|  
|<xref:System.IO.StreamReader?displayProperty=nameWithType>|Lee caracteres de <xref:System.IO.FileStream>, con el uso de <xref:System.IO.StreamReader.CurrentEncoding%2A> para convertir caracteres en bytes y caracteres a partir de bytes. <xref:System.IO.StreamReader> tiene un constructor que intenta confirmar la propiedad <xref:System.IO.StreamReader.CurrentEncoding%2A> correcta de un flujo determinado, en función de la presencia de un preámbulo específico de <xref:System.IO.StreamReader.CurrentEncoding%2A>, como una marca BOM.|  
|<xref:System.IO.StreamWriter?displayProperty=nameWithType>|Escribe caracteres en `FileStream`, con el uso de <xref:System.IO.StreamWriter.Encoding%2A> para convertir caracteres en bytes.|  
|<xref:System.IO.StringReader?displayProperty=nameWithType>|Lee caracteres de `String`. El resultado puede ser una secuencia en cualquier codificación o `String`.|  
|<xref:System.IO.StringWriter?displayProperty=nameWithType>|Escribe caracteres en `String`. El resultado puede ser una secuencia en cualquier codificación o `String`.|  
  
## <a name="see-also"></a>Vea también

- [Crear secuencias](../../../../standard/io/composing-streams.md)
- [E/S de archivos y secuencias](../../../../standard/io/index.md)
- [Asynchronous File I/O](../../../../standard/io/asynchronous-file-i-o.md)
- [Fundamentos del sistema de archivos y la E/S de archivos en .NET Framework (Visual Basic)](basics-of-net-framework-file-io-and-the-file-system.md)
