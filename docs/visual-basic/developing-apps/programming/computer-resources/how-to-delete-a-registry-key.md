---
title: 'Cómo: Eliminar una clave del Registro'
ms.date: 07/20/2015
f1_keywords:
- vb.DeleteSetting
helpviewer_keywords:
- GetSetting function [Visual Basic]
- registry [Visual Basic], deleting values
- GetAllSettings function
- registry keys [Visual Basic], deleting
- registry [Visual Basic], deleting keys
- examples [Visual Basic], registry
ms.assetid: ab9aca0e-42b0-4ff7-8ff9-845a4bfdf9f2
ms.openlocfilehash: ea537d302f64933176f1a44fec2e27b804ff5809
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363324"
---
# <a name="how-to-delete-a-registry-key-in-visual-basic"></a>Cómo: Eliminar una clave del Registro en Visual Basic

Los métodos <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%29> y <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%2CSystem.Boolean%29> se pueden usar para eliminar las claves del Registro.  
  
## <a name="procedure"></a>Procedimiento  
  
#### <a name="to-delete-a-registry-key"></a>Para eliminar una clave del Registro  
  
- Use el método `DeleteSubKey` para eliminar una clave del Registro. En este ejemplo se elimina la clave Software/TestApp en la sección CurrentUser. Puede cambiar esto en el código para la cadena adecuada o confiar en la información proporcionada por el usuario.  
  
     [!code-vb[VbResourceTasks#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#19)]  
  
## <a name="robust-programming"></a>Programación sólida  

 El método `DeleteSubKey` devuelve una cadena vacía si el par clave/valor no existe.  
  
 Las condiciones siguientes pueden provocar una excepción:  
  
- Que el nombre de la clave sea `Nothing` (<xref:System.ArgumentNullException>).  
  
- Que el usuario no tenga permisos para eliminar claves del Registro (<xref:System.Security.SecurityException>).  
  
- Que el nombre de la clave supere el límite de 255 caracteres (<xref:System.ArgumentException>).  
  
- Que la clave del Registro sea de solo lectura (<xref:System.UnauthorizedAccessException>).  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  

 Las llamadas del Registro producen errores si no se conceden permisos suficientes en tiempo de ejecución (<xref:System.Security.Permissions.RegistryPermission>) o si el usuario no tiene el acceso correcto (como se determina en las ACL) para crear o escribir en la configuración. Por ejemplo, una aplicación local que tenga permiso de seguridad de acceso del código puede que no tenga permiso para el sistema operativo.  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A>
- <xref:Microsoft.Win32.RegistryKey>
- [Seguridad y Registro](security-and-the-registry.md)
- [Leer y escribir en el Registro](reading-from-and-writing-to-the-registry.md)
