---
title: "C&#243;mo: Leer un valor a partir de una clave del Registro en Visual Basic | Microsoft Docs"
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
  - "My.Computer.Registry (objeto), ejemplos"
  - "claves del Registro, determinar si un valor existe en"
  - "claves del Registro, leer"
  - "Registro, determinar si existen valores"
  - "Registro, leer"
ms.assetid: 775d0a57-68c9-464e-8949-9a39bd29cc64
caps.latest.revision: 31
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 31
---
# C&#243;mo: Leer un valor a partir de una clave del Registro en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

El método `GetValue` del objeto `My.Computer.Registry` se puede utilizar para leer valores en el Registro de Windows.  
  
 Si la clave no existe, “software \\MyApp” en el ejemplo siguiente, se produce una excepción.  si no existe `ValueName`, “nombre” en el ejemplo siguiente, se devuelve `Nothing` .  
  
 El método de `GetValue` también se puede utilizar para determinar si existe un valor determinado en una clave del Registro específica.  
  
 Cuando el código lee el registro de una aplicación web, la suplantación determina el usuario actual la autenticación y que se implementa en la aplicación web.  
  
### Para leer un valor en una clave del Registro  
  
-   Utilice el método `GetValue` \(especificando la ruta de acceso y el nombre\) para leer un valor de la clave del Registro.  El ejemplo siguiente lee el valor `Name` de `HKEY_CURRENT_USER\Software\MyApp` y lo muestra en un cuadro de mensaje.  
  
     [!code-vb[VbResourceTasks#4](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/how-to-read-a-value-from_1.vb)]  
  
 Este ejemplo de código también está disponible como fragmento de código de IntelliSense.  En el selector de fragmentos de código, se encuentra en **Sistema operativo Windows \> Registro**.  Para obtener más información, vea [Fragmentos de código](/visual-studio/ide/code-snippets).  
  
### Para determinar si un valor existe en una clave del Registro  
  
-   Utilice el método `GetValue` para recuperar el valor.  El código comprueba siguientes si el valor existe y devuelve un mensaje si no lo hace.  
  
     [!code-vb[VbResourceTasks#12](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/how-to-read-a-value-from_2.vb)]  
  
## Programación eficaz  
 El Registro contiene claves de nivel superior o raíz que se utilizan para almacenar datos.  Por ejemplo, la tecla principal de HKEY\_LOCAL\_MACHINE se utiliza para almacenar una configuración de nivel del equipo que utilizan todos los usuarios, mientras que HKEY\_CURRENT\_USER se utiliza para almacenar datos específicos de un usuario individual.  
  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   El nombre de la clave es `Nothing` \(<xref:System.ArgumentNullException>\).  
  
-   El usuario no tiene permiso para leer claves del Registro \(<xref:System.Security.SecurityException>\).  
  
-   El nombre de la clave supera el límite de 255 caracteres \(<xref:System.ArgumentException>\).  
  
## Seguridad de .NET Framework  
 Para ejecutar este proceso, el ensamblado requiere un nivel de privilegios concedido por la clase <xref:System.Security.Permissions.RegistryPermission>.  Si ejecuta el proceso en un contexto de confianza parcial, podría desencadenarse una excepción por falta de privilegios.  De igual manera, el usuario debe tener las ACL correctas para crear o escribir en la configuración.  Por ejemplo, una aplicación local que tenga permiso de seguridad de acceso del código puede no tener permiso para el sistema operativo.  Para obtener más información, vea [Code Access Security Basics](../Topic/Code%20Access%20Security%20Basics.md).  
  
## Vea también  
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>   
 <xref:Microsoft.Win32.RegistryHive>   
 [Leer y escribir en el Registro](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)