---
title: "Soluci&#243;n de problemas: Leer y escribir en archivos de texto (Visual Basic) | Microsoft Docs"
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
  - "E/S [Visual Basic], solucionar problemas de archivo de texto"
  - "leer archivos de texto, solucionar problemas"
  - "solucionar problemas de E/S de archivos"
  - "solucionar problemas de Visual Basic, archivos de texto"
  - "escribir texto en archivos, solucionar problemas"
  - "escribir en archivos, solucionar problemas"
ms.assetid: a8e9b44d-facb-4718-8c0f-466537171182
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Soluci&#243;n de problemas: Leer y escribir en archivos de texto (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Este tema trata problemas comunes encontrados al trabajar con archivos de texto y sugiere un enfoque para ellos.  
  
## Problemas comunes  
 Los problemas más comunes que se producen al trabajar con archivos de texto incluyen excepciones de seguridad, codificaciones de archivo o rutas de acceso no válidas.  
  
### Excepciones de seguridad  
 Si se produce un error de seguridad, se produce <xref:System.Security.SecurityException>.  A menudo es resultado de la falta de los permisos necesarios del usuario; esto se puede solucionar agregando permisos o trabajando con archivos en almacenamiento aislado.  Para obtener más información, vea [Solución de problemas de excepciones: System.Security.SecurityException](../Topic/Troubleshooting%20Exceptions:%20System.Security.SecurityException.md).  
  
### Codificaciones de archivos  
 Las codificaciones de archivos, también conocidas como codificaciones de caracteres, especifican cómo se representan los caracteres cuando se procesa texto.  Los caracteres inesperados en un archivo de texto pueden ser el resultado de una codificación incorrecta.  En la mayoría de los archivos, es preferible una codificación en lugar de otra en términos de los caracteres de lenguaje que pueden controlar; generalmente, Unicode es la opción más adecuada.  Para obtener más información, vea [Codificaciones de archivos](../../../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md) y <xref:System.Text.Encoding>.  
  
### Rutas de acceso incorrectas  
 Al analizar rutas de acceso de los archivo, en particular las rutas de acceso relativas, es fácil proporcionar datos equivocados.  Se pueden corregir muchos problemas asegurándose de que se proporciona la ruta de acceso correcta.  Para obtener más información, vea [Cómo: Analizar rutas de acceso a archivos](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md).  
  
## Vea también  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 [Leer archivos](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)   
 [Escribir en archivos](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)   
 [Analizar archivos de texto con el objeto TextFieldParser](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)