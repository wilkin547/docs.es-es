---
title: "C&#243;mo: Proporcionar un cuadro de di&#225;logo de progreso para operaciones de archivos (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "cuadro de diálogo de progreso [C#]"
ms.assetid: 01b71fe7-8178-4dc8-aeb1-12053be7b51c
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# C&#243;mo: Proporcionar un cuadro de di&#225;logo de progreso para operaciones de archivos (Gu&#237;a de programaci&#243;n de C#)
Puede proporcionar un cuadro de diálogo estándar que muestra el progreso de las operaciones de archivo en Windows si utiliza el método <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%28System.String%2CSystem.String%2CMicrosoft.VisualBasic.FileIO.UIOption%29> en el espacio de nombres <xref:Microsoft.VisualBasic?displayProperty=fullName>.  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
### Para agregar una referencia en Visual Studio  
  
1.  En la barra de menús, elija **Proyecto**, **Agregar referencia**.  
  
     Aparece el cuadro de diálogo **Administrador de referencias**.  
  
2.  En el área **Ensamblados**, elija **Marco** si no está ya elegida.  
  
3.  En la lista de nombres, active la casilla de **Microsoft.VisualBasic** y después elija el botón de **Aceptar** para cerrar el cuadro de diálogo.  
  
## Ejemplo  
 El siguiente código copia el directorio especificado por `sourcePath` en el directorio especificado por `destinationPath`.  Este código también proporciona un cuadro de diálogo estándar que muestra la cantidad de tiempo aproximado restante para que finalice la operación.  
  
 [!code-cs[csFilesandFolders#11](../../../csharp/programming-guide/file-system/codesnippet/csharp/csFilesFolders/FileIteration.cs#11)]  
  
## Vea también  
 [Registro y sistema de archivos](../../../csharp/programming-guide/file-system/file-system-and-the-registry.md)