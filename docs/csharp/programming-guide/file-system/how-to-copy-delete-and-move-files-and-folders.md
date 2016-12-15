---
title: "C&#243;mo: Copiar, eliminar y mover archivos y carpetas (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "E/S [C#]"
ms.assetid: 62e52cd7-9597-4e4a-acf9-1315f5cdbf05
caps.latest.revision: 13
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# C&#243;mo: Copiar, eliminar y mover archivos y carpetas (Gu&#237;a de programaci&#243;n de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

En los ejemplos siguientes se muestra cómo copiar, mover y eliminar archivos y carpetas de forma sincrónica utilizando las clases <xref:System.IO.File?displayProperty=fullName>, <xref:System.IO.Directory?displayProperty=fullName>, <xref:System.IO.FileInfo?displayProperty=fullName> y <xref:System.IO.DirectoryInfo?displayProperty=fullName> del espacio de nombres <xref:System.IO?displayProperty=fullName>.  En estos ejemplos no se proporciona ninguna barra de progreso ni cualquier otra interfaz de usuario.  Si desea proporcionar un cuadro de diálogo de progreso estándar, vea [Cómo: Proporcionar un cuadro de diálogo de progreso para operaciones de archivos](../../../csharp/programming-guide/file-system/how-to-provide-a-progress-dialog-box-for-file-operations.md).  
  
 Utilice <xref:System.IO.FileSystemWatcher?displayProperty=fullName> para proporcionar eventos que permitan calcular el progreso al realizar operaciones en varios archivos.  Otro enfoque consiste en utilizar la invocación de plataforma para llamar a los métodos relacionados con archivos pertinentes en el shell de Windows.  Para obtener información sobre cómo realizar estas operaciones de archivo de forma asincrónica, vea [E\/S de archivos asincrónica](../Topic/Asynchronous%20File%20I-O.md).  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo copiar archivos y directorios.  
  
 [!code-cs[csFilesandFolders#7](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_1.cs)]  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo mover archivos y directorios.  
  
 [!code-cs[csFilesandFolders#8](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_2.cs)]  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo eliminar archivos y directorios.  
  
 [!code-cs[csFilesandFolders#9](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_3.cs)]  
  
## Vea también  
 <xref:System.IO?displayProperty=fullName>   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Registro y sistema de archivos](../../../csharp/programming-guide/file-system/file-system-and-the-registry.md)   
 [Cómo: Proporcionar un cuadro de diálogo de progreso para operaciones de archivos](../../../csharp/programming-guide/file-system/how-to-provide-a-progress-dialog-box-for-file-operations.md)   
 [E\/S de archivos y secuencias](../Topic/File%20and%20Stream%20I-O.md)   
 [Tareas de E\/S comunes](../Topic/Common%20I-O%20Tasks.md)