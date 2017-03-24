---
title: "C&#243;mo: Recuperar el contenido del directorio Mis documentos en Visual Basic | Microsoft Docs"
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
  - "directorio Mis Documentos"
ms.assetid: 26560d01-7dda-4457-8e95-21db23d71aea
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# C&#243;mo: Recuperar el contenido del directorio Mis documentos en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

El objeto <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories> se puede utilizar para leer en muchos de los directorios **Todos los usuarios**, como **Mis documentos** o **Escritorio**.  
  
### Para leer de la carpeta Mis documentos  
  
-   Utilice el método `ReadAllText` para leer el texto de cada archivo situado en un directorio concreto.  El código siguiente especifica un directorio y un archivo y, a continuación, utiliza `ReadAllText` para leerlos y colocarlos en la cadena denominada `patients`.  
  
     [!code-vb[VbVbcnMyFileSystem#15](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-retrieve-the-contents-of-the-my-documents-directory_1.vb)]  
  
## Vea también  
 <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A>