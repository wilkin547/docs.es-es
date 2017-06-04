---
title: "C&#243;mo: Abrir y anexar a un archivo de registro | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "archivos de registro, abrir"
  - "secuencias, abrir un archivo de registro y agregar información"
  - "archivos de registro, anexar a"
  - "E/S [.NET Framework], archivos de registro"
ms.assetid: 74423362-1721-49cb-aa0a-e04005f72a06
caps.latest.revision: 15
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Abrir y anexar a un archivo de registro
<xref:System.IO.StreamWriter> y <xref:System.IO.StreamReader> escriben y leen caracteres de secuencias.  En el siguiente ejemplo de código, se abre el archivo `log.txt` para escribir en él, o se crea el archivo si todavía no existe y se agrega información al final del archivo.  Seguidamente, se escribe el contenido del archivo en la salida estándar para su presentación.  Como alternativa a este ejemplo,la información se podría almacenar como una única cadena o matriz de cadenas, y el método <xref:System.IO.File.WriteAllText%2A> o <xref:System.IO.File.WriteAllLines%2A> se podría emplear para conseguir la misma funcionalidad.  
  
> [!NOTE]
>  Los usuarios de Visual Basic pueden elegir utilizar los métodos y propiedades proporcionados por las clases <xref:Microsoft.VisualBasic.Logging.Log> o <xref:Microsoft.VisualBasic.FileIO.FileSystem> para crear archivos de registro o escribir en ellos.  
  
## Ejemplo  
 [!code-csharp[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source2.cs#2)]
 [!code-vb[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source2.vb#2)]  
  
## Vea también  
 <xref:System.IO.StreamWriter>   
 <xref:System.IO.StreamReader>   
 <xref:System.IO.File.AppendText%2A?displayProperty=fullName>   
 <xref:System.IO.File.OpenText%2A?displayProperty=fullName>   
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=fullName>   
 [Cómo: Enumerar directorios y archivos](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)   
 [Cómo: Leer y escribir en un archivo de datos recién creado](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)   
 [Cómo: Leer texto de un archivo](../../../docs/standard/io/how-to-read-text-from-a-file.md)   
 [Cómo: Escribir texto en un archivo](../../../docs/standard/io/how-to-write-text-to-a-file.md)   
 [Cómo: Leer caracteres de una cadena](../../../docs/standard/io/how-to-read-characters-from-a-string.md)   
 [Cómo: Escribir caracteres en una cadena](../../../docs/standard/io/how-to-write-characters-to-a-string.md)   
 [E\/S de archivos y secuencias](../../../docs/standard/io/index.md)