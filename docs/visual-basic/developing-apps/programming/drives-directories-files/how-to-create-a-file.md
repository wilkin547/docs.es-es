---
title: "C&#243;mo: Crear un archivo en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "archivos, crear"
  - "archivos de texto, crear"
ms.assetid: 0253bb6d-5519-4a50-b882-b93ef5cca0d9
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Crear un archivo en Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Este ejemplo crea un archivo de texto vacío en la ruta de acceso especificada utilizando el método <xref:System.IO.File.Create%2A> de la clase <xref:System.IO.File>.  
  
## Ejemplo  
 [!code-vb[VbFileIOMisc#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-file_1.vb)]  
  
## Compilar el código  
 Utilice la variable `file` para escribir en el archivo.  
  
## Programación eficaz  
 Si el archivo ya existe, es reemplazado.  
  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   El nombre de la ruta de acceso está mal formado.  Por ejemplo, contiene caracteres no válidos o está compuesto sólo por espacios en blanco \(<xref:System.ArgumentException>\).  
  
-   La ruta de acceso es de sólo lectura \(<xref:System.IO.IOException>\).  
  
-   El nombre de la ruta de acceso es `Nothing` \(<xref:System.ArgumentNullException>\).  
  
-   El nombre de la ruta de acceso es demasiado largo \(<xref:System.IO.PathTooLongException>\).  
  
-   La ruta de acceso no es válida \(<xref:System.IO.DirectoryNotFoundException>\).  
  
-   La ruta de acceso contiene sólo un signo de dos puntos ":" \(<xref:System.NotSupportedException>\).  
  
## Seguridad de .NET Framework  
 En entornos de confianza parcial, podría producirse una excepción <xref:System.Security.SecurityException>.  
  
 La llamada al método <xref:System.IO.File.Create%2A> requiere permisos <xref:System.Security.Permissions.FileIOPermission>.  
  
 Si el usuario no tiene permisos para crear el archivo, se produce una excepción <xref:System.UnauthorizedAccessException>.  
  
## Vea también  
 <xref:System.IO>   
 <xref:System.IO.File.Create%2A>   
 [Using Libraries from Partially Trusted Code](../Topic/Using%20Libraries%20from%20Partially%20Trusted%20Code.md)   
 [Code Access Security Basics](../Topic/Code%20Access%20Security%20Basics.md)