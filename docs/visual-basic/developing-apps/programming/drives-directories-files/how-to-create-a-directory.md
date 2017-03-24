---
title: "C&#243;mo: Crear un directorio en Visual Basic | Microsoft Docs"
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
  - "directorios [Visual Basic], crear"
  - "carpetas [Visual Basic], crear"
ms.assetid: 0351a2ca-24d8-43b5-bb39-9b99e6401cff
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# C&#243;mo: Crear un directorio en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Utilice el método `CreateDirectory` del objeto `My.Computer.FileSystem` para crear directorios.  
  
 Si el directorio ya existe, no se produce ninguna excepción.  
  
### Para crear un directorio  
  
-   Utilice el método `CreateDirectory` especificando la ruta de acceso completa de la ubicación donde se debe crear el directorio.  Este ejemplo crea el directorio `NewDirectory` en `C:\Documents and Settings\All Users\Documents`.  
  
     [!code-vb[VbVbcnMyFileSystem#2](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-directory_1.vb)]  
  
## Programación eficaz  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   El nombre de directorio es incorrecto.  Por ejemplo, contiene caracteres no válidos o está compuesto sólo por espacios en blanco \(<xref:System.ArgumentException>\).  
  
-   El directorio principal del directorio que se va a crear es de sólo lectura \(excepción <xref:System.IO.IOException>\).  
  
-   El nombre del directorio es `Nothing` \(<xref:System.ArgumentNullException>\).  
  
-   El nombre del directorio es demasiado largo \(excepción <xref:System.IO.PathTooLongException>\).  
  
-   El nombre del directorio es sólo un signo de dos puntos ":" \(excepción <xref:System.NotSupportedException>\).  
  
-   El usuario no tiene permiso para crear el directorio \(<xref:System.UnauthorizedAccessException>\).  
  
-   El usuario no tiene permisos suficientes en una situación de confianza parcial \(<xref:System.Security.SecurityException>\).  
  
## Vea también  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CreateDirectory%2A>   
 [Crear, eliminar y mover archivos y directorios](../../../../visual-basic/developing-apps/programming/drives-directories-files/creating-deleting-and-moving-files-and-directories.md)