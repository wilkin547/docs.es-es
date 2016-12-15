---
title: "Clases utilizadas en el sistema de archivos y la E/S de archivos en .NET Framework (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "clases de E/S de archivos"
ms.assetid: 4a5ca924-eea8-4a95-a5f0-6ac10de276a3
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Clases utilizadas en el sistema de archivos y la E/S de archivos en .NET Framework (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Las tablas siguientes incluyen las clases usadas más comúnmente para las operaciones de E\/S de archivos en .NET Framework, clasificadas en clases de E\/S de archivos, clases usadas para crear secuencias y clases utilizadas para leer y escribir en secuencias.  
  
 Para entrar en la documentación de [!INCLUDE[dnprdnlong](../../../../csharp/programming-guide/events/includes/dnprdnlong_md.md)] y consultar una lista más completa, vea [Información general de la biblioteca de clases](../Topic/.NET%20Framework%20Class%20Library%20Overview.md).  
  
## Clases básicas de E\/S para archivos, unidades y directorios  
 La tabla siguiente muestra y describe las clases principales utilizadas para las operaciones de E\/S de archivos.  
  
|Clase|Descripción|  
|-----------|-----------------|  
|<xref:System.IO.Directory?displayProperty=fullName>|Proporciona métodos estáticos para crear, mover y enumerar archivos en directorios y subdirectorios.|  
|<xref:System.IO.DirectoryInfo?displayProperty=fullName>|Proporciona métodos de instancia para crear, mover y enumerar archivos en directorios y subdirectorios.|  
|<xref:System.IO.DriveInfo?displayProperty=fullName>|Proporciona métodos de instancia para crear, mover y enumerar entre unidades.|  
|<xref:System.IO.File?displayProperty=fullName>|Proporciona métodos estáticos para crear, copiar, eliminar, mover y abrir archivos, y ayuda en la creación de una secuencia `FileStream`.|  
|<xref:System.IO.FileAccess?displayProperty=fullName>|Define constantes de acceso de lectura, de escritura y de lectura\/escritura para un archivo.|  
|<xref:System.IO.FileAttributes?displayProperty=fullName>|Proporciona atributos para archivos y directorios, como `Archive`, `Hidden` y `ReadOnly`.|  
|<xref:System.IO.FileInfo?displayProperty=fullName>|Proporciona métodos estáticos para crear, copiar, eliminar, mover y abrir archivos, y ayuda en la creación de una secuencia `FileStream`.|  
|<xref:System.IO.FileMode?displayProperty=fullName>|Controla cómo se abre un archivo.  Este parámetro se especifica en muchos de los constructores para `FileStream` e `IsolatedStorageFileStream`, y para los métodos `Open` de <xref:System.IO.File> y <xref:System.IO.FileInfo>.|  
|<xref:System.IO.FileShare?displayProperty=fullName>|Define las constantes para controlar el tipo de acceso que pueden tener otras secuencias de archivo al mismo archivo.|  
|<xref:System.IO.Path?displayProperty=fullName>|Proporciona métodos y propiedades para procesar cadenas de directorio.|  
|<xref:System.Security.Permissions.FileIOPermission?displayProperty=fullName>|Controla el acceso a archivos y carpetas definiendo los permisos <xref:System.Security.Permissions.FileIOPermissionAttribute.Read%2A>, <xref:System.Security.Permissions.FileIOPermissionAttribute.Write%2A>, <xref:System.Security.Permissions.FileIOPermissionAttribute.Append%2A> y <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A>.|  
  
## Clases utilizadas para crear secuencias  
 La tabla siguiente muestra y describe las clases principales utilizadas para crear secuencias.  
  
|Clase|Descripción|  
|-----------|-----------------|  
|<xref:System.IO.BufferedStream?displayProperty=fullName>|Agrega una capa de almacenamiento en búfer para las operaciones de lectura y escritura en otra secuencia.|  
|<xref:System.IO.FileStream?displayProperty=fullName>|Admite el acceso aleatorio a los archivos a través de su método <xref:System.IO.FileStream.Seek%2A>.  <xref:System.IO.FileStream> abre los archivos sincrónicamente de forma predeterminada, pero también admite operaciones asincrónicas.|  
|<xref:System.IO.MemoryStream?displayProperty=fullName>|Crea una secuencia cuya memoria auxiliar es la memoria, en lugar de un archivo.|  
|<xref:System.Net.Sockets.NetworkStream?displayProperty=fullName>|Proporciona el flujo de datos subyacente para el acceso a través de la red.|  
|<xref:System.Security.Cryptography.CryptoStream?displayProperty=fullName>|Define una secuencia que vincula los flujos de datos a las transformaciones criptográficas.|  
  
## Clases usadas para leer y escribir en secuencias  
 La tabla siguiente muestra las clases concretas utilizadas para leer y escribir en los archivos con secuencias.  
  
|**Clase**|**Descripción**|  
|---------------|---------------------|  
|<xref:System.IO.BinaryReader?displayProperty=fullName>|Lee cadenas codificadas y los tipos de datos primitivos de una secuencia <xref:System.IO.FileStream>.|  
|<xref:System.IO.BinaryWriter?displayProperty=fullName>|Escribe cadenas codificadas y los tipos de datos primitivos en una secuencia <xref:System.IO.FileStream>.|  
|<xref:System.IO.StreamReader?displayProperty=fullName>|Lee los caracteres de un objeto <xref:System.IO.FileStream> y utiliza la clase <xref:System.IO.StreamReader.CurrentEncoding%2A> para convertir los caracteres en bytes, y viceversa.  <xref:System.IO.StreamReader> tiene un constructor que trata de comprobar si el valor de <xref:System.IO.StreamReader.CurrentEncoding%2A> es correcto para una secuencia dada, basándose en la presencia de un preámbulo específico de <xref:System.IO.StreamReader.CurrentEncoding%2A>, como por ejemplo una marca de orden de bytes.|  
|<xref:System.IO.StreamWriter?displayProperty=fullName>|Escribe caracteres en una secuencia `FileStream`, utilizando <xref:System.IO.StreamWriter.Encoding%2A> para convertir los caracteres a bytes.|  
|<xref:System.IO.StringReader?displayProperty=fullName>|Lee caracteres de una cadena `String`.  El resultado puede ser una secuencia en cualquier codificación o una cadena `String`.|  
|<xref:System.IO.StringWriter?displayProperty=fullName>|Escribe caracteres en una cadena `String`.  El resultado puede ser una secuencia en cualquier codificación o una cadena `String`.|  
  
## Vea también  
 [Crear secuencias](../Topic/Composing%20Streams.md)   
 [E\/S de archivos y secuencias](../Topic/File%20and%20Stream%20I-O.md)   
 [E\/S de archivos asincrónica](../Topic/Asynchronous%20File%20I-O.md)   
 [Fundamentos del sistema de archivos y la E\/S de archivos en .NET Framework \(Visual Basic\)](../../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md)