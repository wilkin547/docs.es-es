---
title: "Cómo: Eliminar una clave del Registro en Visual Basic | Microsoft Docs"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.DeleteSetting
dev_langs:
- VB
helpviewer_keywords:
- GetSetting function
- registry, deleting values
- GetAllSettings function
- registry keys, deleting
- registry, deleting keys
- examples [Visual Basic], registry
ms.assetid: ab9aca0e-42b0-4ff7-8ff9-845a4bfdf9f2
caps.latest.revision: 28
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
ms.openlocfilehash: a50ee5a0853e6209c3bf5d5224d536f4cc6bbe11
ms.contentlocale: es-es
ms.lasthandoff: 05/22/2017

---
# <a name="how-to-delete-a-registry-key-in-visual-basic"></a>Cómo: Eliminar una clave del Registro en Visual Basic
Los métodos <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%29> y <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%2CSystem.Boolean%29> se pueden usar para eliminar las claves del Registro.  
  
## <a name="procedure"></a>Procedimiento  
  
#### <a name="to-delete-a-registry-key"></a>Para eliminar una clave del Registro  
  
-   Use el método `DeleteSubKey` para eliminar una clave del Registro. En este ejemplo se elimina la clave Software/TestApp en la sección CurrentUser. Puede cambiar esto en el código para la cadena adecuada o confiar en la información proporcionada por el usuario.  
  
     [!code-vb[VbResourceTasks#19](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-delete-a-registry-key_1.vb)]  
  
## <a name="robust-programming"></a>Programación sólida  
 El método `DeleteSubKey` devuelve una cadena vacía si el par clave/valor no existe.  
  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   El nombre de la clave es `Nothing` (<xref:System.ArgumentNullException>).  
  
-   El usuario no tiene permiso para eliminar claves del Registro (<xref:System.Security.SecurityException>).  
  
-   El nombre de la clave supera el límite de 255 caracteres (<xref:System.ArgumentException>).  
  
-   La clave del Registro es de solo lectura (<xref:System.UnauthorizedAccessException>).  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Las llamadas del Registro producen errores si no se conceden permisos suficientes en tiempo de ejecución (<xref:System.Security.Permissions.RegistryPermission>) o si el usuario no tiene el acceso correcto (como se determina en las ACL) para crear o escribir en la configuración. Por ejemplo, una aplicación local que tenga permiso de seguridad de acceso del código puede que no tenga permiso para el sistema operativo.  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A>   
 <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A>   
 <xref:Microsoft.Win32.RegistryKey>   
 [Seguridad y Registro](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md)   
 [Leer y escribir en el Registro](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)
