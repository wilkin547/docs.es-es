---
title: "C&#243;mo: Buscar subdirectorios con un modelo concreto en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "carpetas, buscar"
  - "coincidencia con un modelo"
ms.assetid: c9265fd1-7483-4150-8b7f-ff642caa939d
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# C&#243;mo: Buscar subdirectorios con un modelo concreto en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

El método <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetDirectories%2A> devuelve una colección de solo lectura de cadenas que representan los nombres de ruta de acceso a los subdirectorios en un directorio.  Puede utilizar el parámetro `wildCards` para especificar un modelo concreto.  Si desea incluir el contenido de subdirectorios en la búsqueda, establezca el parámetro `searchType` en `SearchOption.SearchAllSubDirectories`.  
  
 Se devuelve una colección vacía si no se encuentra ningún directorio que coincida con el modelo especificado.  
  
### Para buscar subdirectorios con un modelo concreto  
  
-   Utilice el método `GetDirectories` y proporcione el nombre y ruta de acceso del directorio que desee buscar.  En el ejemplo siguiente se devuelven todos los directorios de la estructura de directorios que contienen la palabra "Logs" en su nombre y se agregan a `ListBox1`.  
  
     [!code-vb[VbVbcnFileAccess#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/how-to-find-subdirectori_1.vb)]  
  
## Programación eficaz  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   La ruta de acceso no es válida por una de las razones siguientes: es una cadena de longitud cero, solo contiene un espacio en blanco, contiene caracteres no válidos o es una ruta de acceso de dispositivo \(empieza por \\\\.  \\\) \(<xref:System.ArgumentException>\).  
  
-   La ruta de acceso no es válida porque es `Nothing` \(<xref:System.ArgumentNullException>\).  
  
-   Uno o más de los caracteres comodín especificados es `Nothing`, una cadena vacía o contiene sólo espacios \(<xref:System.ArgumentNullException>\).  
  
-   `directory` no existe \(<xref:System.IO.DirectoryNotFoundException>\).  
  
-   `directory` señala a un archivo existente \(<xref:System.IO.IOException>\).  
  
-   La ruta de acceso supera la longitud máxima definida por el sistema \(<xref:System.IO.PathTooLongException>\).  
  
-   Un nombre de archivo o de carpeta en la ruta de acceso contiene dos puntos \(:\) o está en un formato no válido \(<xref:System.NotSupportedException>\).  
  
-   El usuario no tiene los permisos necesarios para ver la ruta de acceso \(<xref:System.Security.SecurityException>\).  
  
-   El usuario no tiene los permisos necesarios \(<xref:System.UnauthorizedAccessException>\).  
  
## Vea también  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetDirectories%2A>   
 [Cómo: Buscar archivos con un modelo concreto](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-files-with-a-specific-pattern.md)