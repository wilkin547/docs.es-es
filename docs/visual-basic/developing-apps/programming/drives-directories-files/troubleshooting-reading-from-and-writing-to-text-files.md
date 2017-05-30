---
title: "Solución de problemas: Leer y escribir en archivos de texto (Visual Basic) | Microsoft Docs"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- troubleshooting file I/O
- writing text to files, troubleshooting
- troubleshooting Visual Basic, text files
- I/O [Visual Basic], troubleshooting text files
- writing to files, troubleshooting
- reading text files, troubleshooting
ms.assetid: a8e9b44d-facb-4718-8c0f-466537171182
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 739f14a7cb5c559720bfac1a78b5fc50001052cb
ms.contentlocale: es-es
ms.lasthandoff: 05/22/2017

---
# <a name="troubleshooting-reading-from-and-writing-to-text-files-visual-basic"></a>Solución de problemas: Leer y escribir en archivos de texto (Visual Basic)
En este tema se tratan problemas habituales que surgen cuando se trabaja con archivos de texto y se sugiere un enfoque para cada uno.  
  
## <a name="common-problems"></a>Problemas habituales  
 Entre los problemas más frecuentes que se producen al trabajar con archivos de texto se incluyen excepciones de seguridad, codificaciones de archivos o rutas de acceso no válidas.  
  
### <a name="security-exceptions"></a>Excepciones de seguridad  
 Se genera <xref:System.Security.SecurityException> cuando se produce un error de seguridad. Suele ser consecuencia de que el usuario carezca de los permisos necesarios, lo que se puede resolver al agregar permisos o trabajar con archivos en almacenamiento aislado.  
  
### <a name="file-encodings"></a>Codificaciones de archivos  
 Las codificaciones de archivos, también denominadas codificaciones de caracteres, especifican cómo se representan los caracteres durante el procesamiento de texto. La presencia de caracteres inesperados en un archivo de texto puede deberse a una codificación incorrecta. Con la mayoría de los archivos, puede que una codificación sea preferible a otra en función de los caracteres del lenguaje que pueda controlar, aunque normalmente se prefiere Unicode. Para más información, vea [Codificación de archivos](../../../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md) y <xref:System.Text.Encoding>.  
  
### <a name="incorrect-paths"></a>Rutas de acceso incorrectas  
 Al analizar rutas de acceso de archivo, sobre todo rutas de acceso relativas, es fácil especificar datos equivocados. Muchos problemas pueden corregirse asegurándose de que especifica la ruta de acceso correcta. Para obtener más información, vea [How to: Parse File Paths in Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md) (Cómo: Analizar rutas de acceso a archivos en Visual Basic).  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 [Reading from Files in Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)  (Leer archivos en Visual Basic)  
 [Writing to Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)  (Escribir en archivos en Visual Basic)  
 [Análisis de archivos de texto con el objeto TextFieldParser](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)
