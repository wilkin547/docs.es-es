---
description: 'Más información acerca de: Procedimiento: para crear un archivo en Visual Basic'
title: Procedimiento para crear un archivo
ms.date: 07/20/2015
helpviewer_keywords:
- text files [Visual Basic], creating
- files [Visual Basic], creating
ms.assetid: 0253bb6d-5519-4a50-b882-b93ef5cca0d9
ms.openlocfilehash: b46786035c14021ceb27cce5b34eff5c8397fc9a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797593"
---
# <a name="how-to-create-a-file-in-visual-basic"></a>Cómo: Crear un archivo en Visual Basic

En este ejemplo se crea un archivo de texto vacío en la ruta de acceso especificada usando el método <xref:System.IO.File.Create%2A> de la clase <xref:System.IO.File>.  
  
## <a name="example"></a>Ejemplo  

 [!code-vb[VbFileIOMisc#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/class2.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  

 Use la variable `file` para escribir en el archivo.  
  
## <a name="robust-programming"></a>Programación sólida  

 Si el archivo ya existe, se reemplaza.  
  
 Las condiciones siguientes pueden provocar una excepción:  
  
- El nombre de la ruta de acceso es incorrecto. Por ejemplo, contiene caracteres no válidos o solo tiene espacios en blanco (<xref:System.ArgumentException>).  
  
- La ruta de acceso es de solo lectura (<xref:System.IO.IOException>).  
  
- El nombre de la ruta de acceso es `Nothing` (<xref:System.ArgumentNullException>).  
  
- El nombre de la ruta de acceso es demasiado largo (<xref:System.IO.PathTooLongException>).  
  
- La ruta de acceso no es válida (<xref:System.IO.DirectoryNotFoundException>).  
  
- La ruta de acceso es solo dos puntos ":" (<xref:System.NotSupportedException>).  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  

 En entornos de confianza parcial, podría producirse una excepción <xref:System.Security.SecurityException>.  
  
 La llamada al método <xref:System.IO.File.Create%2A> requiere <xref:System.Security.Permissions.FileIOPermission>.  
  
 Si el usuario no tiene permisos para crear el archivo, se produce una excepción <xref:System.UnauthorizedAccessException>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.IO>
- <xref:System.IO.File.Create%2A>
- [Utilizar bibliotecas de código que no es de plena confianza](../../../../framework/misc/using-libraries-from-partially-trusted-code.md)
- [Conceptos básicos sobre la seguridad de acceso del código](../../../../framework/misc/code-access-security-basics.md)
