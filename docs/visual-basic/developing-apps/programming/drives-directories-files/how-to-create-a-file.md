---
title: "Cómo: Crear un archivo en Visual Basic"
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
- text files, creating
- files, creating
ms.assetid: 0253bb6d-5519-4a50-b882-b93ef5cca0d9
caps.latest.revision: 15
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d06d274b31afad0a437405d1679e0be7548f2e14
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-a-file-in-visual-basic"></a>Cómo: Crear un archivo en Visual Basic
En este ejemplo se crea un archivo de texto vacío en la ruta de acceso especificada usando el método <xref:System.IO.File.Create%2A> de la clase <xref:System.IO.File>.  
  
## <a name="example"></a>Ejemplo  
 [!code-vb[VbFileIOMisc#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-file_1.vb)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Use la variable `file` para escribir en el archivo.  
  
## <a name="robust-programming"></a>Programación sólida  
 Si el archivo ya existe, se reemplaza.  
  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   El nombre de la ruta de acceso es incorrecto. Por ejemplo, contiene caracteres no válidos o solo tiene espacios en blanco (<xref:System.ArgumentException>).  
  
-   La ruta de acceso es de solo lectura (<xref:System.IO.IOException>).  
  
-   El nombre de la ruta de acceso es `Nothing` (<xref:System.ArgumentNullException>).  
  
-   El nombre de la ruta de acceso es demasiado largo (<xref:System.IO.PathTooLongException>).  
  
-   La ruta de acceso no es válida (<xref:System.IO.DirectoryNotFoundException>).  
  
-   La ruta de acceso es solo dos puntos ":" (<xref:System.NotSupportedException>).  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 En entornos de confianza parcial, podría producirse una excepción <xref:System.Security.SecurityException>.  
  
 La llamada al método <xref:System.IO.File.Create%2A> requiere <xref:System.Security.Permissions.FileIOPermission>.  
  
 Si el usuario no tiene permisos para crear el archivo, se produce una excepción <xref:System.UnauthorizedAccessException>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IO>   
 <xref:System.IO.File.Create%2A>   
 [Using Libraries from Partially Trusted Code](../../../../framework/misc/using-libraries-from-partially-trusted-code.md)  (Usar bibliotecas de código que no es de plena confianza)  
 [Code Access Security Basics](https://msdn.microsoft.com/library/33tceax8) (Conceptos básicos sobre la seguridad de acceso del código)

