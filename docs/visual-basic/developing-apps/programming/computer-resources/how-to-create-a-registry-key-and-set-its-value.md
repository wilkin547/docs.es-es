---
title: "C&#243;mo: Crear una clave del Registro y establecer su valor en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "RegistryKey.CreateSubKey"
  - "RegistryKey.SetValue"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ejemplos [Visual Basic], Registro"
  - "claves del Registro, crear"
  - "claves del Registro, establecer valores"
  - "Registro, agregar claves"
  - "Registro, agregar valores"
ms.assetid: d3e40f74-c283-480c-ab18-e5e9052cd814
caps.latest.revision: 30
caps.handback.revision: 30
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Crear una clave del Registro y establecer su valor en Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

El método `CreateSubKey` del objeto `My.Computer.Registry` se puede utilizar para crear una clave del Registro.  
  
## Procedimiento  
  
#### Para crear una clave del Registro  
  
-   Utilice el método `CreateSubKey`, especificando en qué subárbol se va a colocar la clave, así como el nombre de la clave.  El parámetro  `Subkey`  no distingue entre mayúsculas y minúsculas.  Este ejemplo crea la clave del Registro `MyTestKey` en HKEY\_CURRENT\_USER.  
  
     [!code-vb[VbResourceTasks#17](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-create-a-registry-key-and-set-its-value_1.vb)]  
  
#### Crear una clave del Registro y establecer un valor en él  
  
1.  Utilice el método `CreateSubkey`, especificando en qué subárbol se va a colocar la clave, así como el nombre de la clave.  Este ejemplo crea la clave del Registro `MyTestKey` en HKEY\_CURRENT\_USER.  
  
     [!code-vb[VbResourceTasks#17](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-create-a-registry-key-and-set-its-value_1.vb)]  
  
2.  Establezca el valor con el método `SetValue`.  Este ejemplo establece el valor de la cadena. "  "MyTestKeyValue" en "This is a test value".  
  
     [!code-vb[VbResourceTasks#14](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-create-a-registry-key-and-set-its-value_2.vb)]  
  
## Ejemplo  
 Este ejemplo crea la clave del Registro `MyTestKey` en HKEY\_CURRENT\_USER y, a continuación, establece el valor de la cadena `MyTestKeyValue` en `This is a test value`.  
  
 [!code-vb[VbResourceTasks#15](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-create-a-registry-key-and-set-its-value_3.vb)]  
  
## Programación eficaz  
 Examine la estructura del Registro para buscar la ubicación adecuada para la clave.  Por ejemplo, puede que desee abrir la clave HKEY\_CURRENT\_USER\\Software del usuario actual y crear una clave con el nombre de su empresa.  A continuación, agregue los valores del Registro a la clave de su empresa.  
  
 Cuando se esté leyendo el Registro desde una aplicación Web, el usuario actual dependerá de la autenticación y suplantación implementadas en la aplicación Web.  
  
 Resulta más seguro escribir datos en la carpeta de usuario \(<xref:Microsoft.Win32.Registry.CurrentUser>\) que en el equipo local \(<xref:Microsoft.Win32.Registry.LocalMachine>\).  
  
 A la hora de crear valores de Registro, deberá decidir qué hacer si coinciden con otros ya existentes.  Es posible que otro proceso, probablemente malintencionado, haya creado el valor y tenga acceso a él.  Cuando ponga datos en el valor del Registro, los datos estarán disponibles para el otro proceso.  Para evitar esto, utilice el método <xref:Microsoft.Win32.RegistryKey.GetValue%2A>.  Devuelve `Nothing` si la clave no existe ya.  
  
 Aunque la clave del Registro esté protegida por listas de control de acceso \(ACL\), no es seguro almacenar en ella datos secretos \(por ejemplo, contraseñas\) como texto sin formato.  
  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   El nombre de la clave es `Nothing` \(<xref:System.ArgumentNullException>\).  
  
-   El usuario no tiene permiso para crear claves del Registro \(<xref:System.Security.SecurityException>\).  
  
-   El nombre de la clave supera el límite de 255 caracteres \(<xref:System.ArgumentException>\).  
  
-   La clave está cerrada \(<xref:System.IO.IOException>\).  
  
-   La clave del Registro es de sólo lectura \(<xref:System.UnauthorizedAccessException>\).  
  
## Seguridad de .NET Framework  
 Para ejecutar este proceso, el ensamblado requiere un nivel de privilegios concedido por la clase <xref:System.Security.Permissions.RegistryPermission>.  Si ejecuta el proceso en un contexto de confianza parcial, podría desencadenarse una excepción por falta de privilegios.  De igual manera, el usuario debe tener las ACL correctas para crear o escribir en la configuración.  Por ejemplo, una aplicación local que tenga permiso de seguridad de acceso del código puede no tener permiso para el sistema operativo.  Para obtener más información, vea [Code Access Security Basics](../Topic/Code%20Access%20Security%20Basics.md).  
  
## Vea también  
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>   
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy.CurrentUser%2A>   
 <xref:Microsoft.Win32.RegistryKey.CreateSubKey%2A>   
 [Leer y escribir en el Registro](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)   
 [Code Access Security Basics](../Topic/Code%20Access%20Security%20Basics.md)