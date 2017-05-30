---
title: "Cómo: Leer un valor a partir de una clave del Registro en Visual Basic | Microsoft Docs"
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
- registry keys, determining if a value exists in
- My.Computer.Registry object, examples
- registry, determining if values exist
- registry keys, reading from
- registry, reading
ms.assetid: 775d0a57-68c9-464e-8949-9a39bd29cc64
caps.latest.revision: 31
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
ms.openlocfilehash: b5054e277895d185ab8ec6f6a2950d5dedbef390
ms.contentlocale: es-es
ms.lasthandoff: 05/22/2017

---
# <a name="how-to-read-a-value-from-a-registry-key-in-visual-basic"></a>Cómo: Leer un valor a partir de una clave del Registro en Visual Basic
El método `GetValue` del objeto `My.Computer.Registry` se puede usar para leer valores en el Registro de Windows.  
  
 Si la clave, "Software\MyApp" en el ejemplo siguiente, no existe, se produce una excepción. Si `ValueName`, "Nombre" en el ejemplo siguiente, no existe, se devuelve `Nothing`.  
  
 El método `GetValue` también se puede usar para determinar si existe un valor determinado en una clave del Registro específica.  
  
 Cuando el código lee el registro de una aplicación web, la autenticación y la suplantación determinan el usuario actual que se implementa en la aplicación web.  
  
### <a name="to-read-a-value-from-a-registry-key"></a>Para leer un valor en una clave del Registro  
  
-   Use el método `GetValue` (especificando la ruta de acceso y el nombre) para leer un valor de la clave del Registro. En el ejemplo siguiente se lee el valor `Name` de `HKEY_CURRENT_USER\Software\MyApp` y lo muestra en un cuadro de mensaje.  
  
     [!code-vb[VbResourceTasks#4](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-read-a-value-from-a-registry-key_1.vb)]  
  
 Este ejemplo de código también está disponible como fragmento de código de IntelliSense. En el selector de fragmentos de código, se encuentra en **Sistema operativo Windows > Registro**. Para obtener más información, vea [Fragmentos de código](https://docs.microsoft.com/visualstudio/ide/code-snippets).  
  
### <a name="to-determine-whether-a-value-exists-in-a-registry-key"></a>Para determinar si un valor existe en una clave del Registro  
  
-   Use el método `GetValue` para recuperar el valor. El siguiente código comprueba si el valor existe y devuelve un mensaje si no es así.  
  
     [!code-vb[VbResourceTasks#12](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-read-a-value-from-a-registry-key_2.vb)]  
  
## <a name="robust-programming"></a>Programación sólida  
 El registro contiene claves de nivel superior o raíz que se usan para almacenar datos. Por ejemplo, la clave raíz HKEY_LOCAL_MACHINE se usa para almacenar una configuración de nivel de equipo que usan todos los usuarios, mientras que HKEY_CURRENT_USER se usa para almacenar datos específicos de un usuario individual.  
  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   Que el nombre de la clave sea `Nothing` (<xref:System.ArgumentNullException>).  
  
-   Que el usuario tenga permisos para leer de las claves del Registro (<xref:System.Security.SecurityException>).  
  
-   Que el nombre de la clave supere el límite de 255 caracteres (<xref:System.ArgumentException>).  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Para ejecutar este proceso, el ensamblado necesita un nivel de privilegio concedido por la clase <xref:System.Security.Permissions.RegistryPermission>. Si ejecuta el proceso en un contexto de confianza parcial, este podría desencadenar una excepción por falta de privilegios. De igual manera, el usuario debe tener las ACL correctas para crear o escribir en la configuración. Por ejemplo, una aplicación local que tenga permiso de seguridad de acceso del código puede que no tenga permiso para el sistema operativo. Para obtener más información, vea [Code Access Security Basics](https://msdn.microsoft.com/library/33tceax8) (Aspectos básicos de seguridad de acceso del código).  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>   
 <xref:Microsoft.Win32.RegistryHive>   
 [Leer y escribir en el Registro](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)
