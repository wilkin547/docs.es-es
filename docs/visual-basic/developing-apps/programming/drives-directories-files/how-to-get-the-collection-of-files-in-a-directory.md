---
title: "C&#243;mo: Obtener la colecci&#243;n de archivos de un directorio en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "archivos, obtener acceso"
  - "carpetas, trabajar con"
ms.assetid: 6c8ba7e8-dd37-4853-92bf-762b67c98160
caps.latest.revision: 23
caps.handback.revision: 23
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Obtener la colecci&#243;n de archivos de un directorio en Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Las sobrecargas del método <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A?displayProperty=fullName> devuelven una colección de solo lectura de cadenas que representan los nombres de los archivos contenidos en un directorio:  
  
-   Use la sobrecarga <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%28System.String%29> para realizar una búsqueda de archivos sencilla en un directorio concreto, sin buscar en los subdirectorios.  
  
-   Use la sobrecarga [GetFiles\(String, SearchOption, String\[\]\)](assetId:///M:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles(System.String,Microsoft.VisualBasic.FileIO.SearchOption,System.String[])?qualifyHint=False&autoUpgrade=False) para especificar más opciones de búsqueda.  Puede usar el parámetro `wildCards` para especificar un patrón de búsqueda.  Para incluir los subdirectorios en la búsqueda, establezca el parámetro `searchType` en <xref:Microsoft.VisualBasic.FileIO.SearchOption?displayProperty=fullName>.  
  
 Si no se encuentran archivos que coincidan con el patrón especificado, se devuelve una colección vacía.  
  
### Para enumerar los archivos de un directorio  
  
-   Use una de las sobrecargas del método <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A?displayProperty=fullName> y proporcione el nombre y la ruta de acceso del directorio para buscar en el parámetro `directory`.  En el siguiente ejemplo se devuelven todos los archivos contenidos en el directorio y se agregan a  `ListBox1`.  
  
     [!code-vb[VbVbcnMyFileSystem#32](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-get-the-collection-of-files-in-a-directory_1.vb)]  
  
## Programación eficaz  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   La ruta de acceso no es válida por una de las siguientes razones: es una cadena de longitud cero, solo contiene un espacio en blanco, contiene caracteres no válidos o es una ruta de acceso de dispositivo \(empieza por \\\\.  \\\) \(<xref:System.ArgumentException>\).  
  
-   La ruta de acceso no es válida porque es `Nothing` \(<xref:System.ArgumentNullException>\).  
  
-   `directory` no existe \(<xref:System.IO.DirectoryNotFoundException>\).  
  
-   `directory` apunta a un archivo existente \(<xref:System.IO.IOException>\).  
  
-   La ruta supera la longitud máxima definida por el sistema \(<xref:System.IO.PathTooLongException>\).  
  
-   Un nombre de archivo o de directorio de la ruta de acceso contiene un signo de dos puntos \(:\) o tiene un formato no válido \(<xref:System.NotSupportedException>\).  
  
-   El usuario no tiene los permisos necesarios para ver la ruta de acceso \(<xref:System.Security.SecurityException>\).  
  
-   El usuario no tiene los permisos necesarios \(<xref:System.UnauthorizedAccessException>\).  
  
## Vea también  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A>   
 [Cómo: Buscar archivos con un modelo concreto](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-files-with-a-specific-pattern.md)   
 [Cómo: Buscar subdirectorios con un modelo concreto](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md)