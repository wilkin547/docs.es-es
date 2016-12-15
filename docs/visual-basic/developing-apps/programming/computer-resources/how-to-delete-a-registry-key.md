---
title: "C&#243;mo: Eliminar una clave del Registro en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.DeleteSetting"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ejemplos [Visual Basic], Registro"
  - "GetAllSettings (función)"
  - "GetSetting (función)"
  - "claves del Registro, eliminar"
  - "Registro, eliminar claves"
  - "Registro, eliminar valores"
ms.assetid: ab9aca0e-42b0-4ff7-8ff9-845a4bfdf9f2
caps.latest.revision: 28
caps.handback.revision: 28
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Eliminar una clave del Registro en Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Los métodos <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%29> y <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%2CSystem.Boolean%29> se pueden utilizar para eliminar las claves del Registro.  
  
## Procedimiento  
  
#### Para eliminar una clave del Registro  
  
-   Utilice el método `DeleteSubKey` para eliminar una clave del Registro.  Este ejemplo elimina la clave Software\/TestApp en la sección CurrentUser.  Puede cambiar esto en el código para la cadena adecuada o confiar en la información proporcionada por el usuario.  
  
     [!code-vb[VbResourceTasks#19](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-delete-a-registry-key_1.vb)]  
  
## Programación eficaz  
 El método `DeleteSubKey` devuelve una cadena vacía si el par clave\/valor no existe.  
  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   El nombre de la clave es `Nothing` \(<xref:System.ArgumentNullException>\).  
  
-   El usuario no tiene permiso para eliminar claves del Registro \(<xref:System.Security.SecurityException>\).  
  
-   El nombre de la clave supera el límite de 255 caracteres \(<xref:System.ArgumentException>\).  
  
-   La clave del Registro es de sólo lectura \(<xref:System.UnauthorizedAccessException>\).  
  
## Seguridad de .NET Framework  
 Las llamadas del Registro producen errores si no se conceden permisos suficientes en tiempo de ejecución \(<xref:System.Security.Permissions.RegistryPermission>\) o si el usuario no tiene el acceso correcto \(como se determina en las ACL\) para crear o escribir en la configuración.  Por ejemplo, una aplicación local que tenga permiso de seguridad de acceso del código puede no tener permiso para el sistema operativo.  
  
## Vea también  
 <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A>   
 <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A>   
 <xref:Microsoft.Win32.RegistryKey>   
 [Seguridad y Registro](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md)   
 [Leer y escribir en el Registro](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)