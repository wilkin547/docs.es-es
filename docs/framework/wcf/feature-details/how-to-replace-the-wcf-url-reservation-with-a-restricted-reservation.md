---
title: "Cómo: Reemplazar la reserva de direcciones URL de WCF por una reserva restringida"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2754d223-79fc-4e2b-a6ce-989889f2abfa
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8c25403f298444732f6787979add595bd877bb2c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation"></a>Cómo: Reemplazar la reserva de direcciones URL de WCF por una reserva restringida
Una reserva de direcciones URL le permite restringir quién puede recibir mensajes desde una URL o un conjunto de ellas. Una reserva consta de una plantilla de dirección URL, una lista de control de acceso (ACL) y un conjunto de marcas. La plantilla de dirección URL define a qué direcciones URL afecta la reserva. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]cómo se procesan las plantillas de dirección URL, vea [las solicitudes entrantes de enrutamiento](http://go.microsoft.com/fwlink/?LinkId=136764). La ACL determina qué usuario o grupo de usuarios pueden recibir mensajes desde las direcciones URL especificadas. Las marcas indican si la reserva proporciona permiso a un usuario o a un grupo de ellos para realizar escuchas directamente en la dirección URL o delega el permiso de escucha en otro proceso.  
  
 Como parte de la configuración predeterminada del sistema operativo, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] crea una reserva accesible globalmente para el puerto 80 que permite a todos los usuarios ejecutar aplicaciones que usan un enlace HTTP doble para la comunicación dúplex. Dado que la ACL en esta reserva es para todos los usuarios, los administradores no pueden conceder o denegar explícitamente el permiso para realizar escuchas en una dirección URL o en un conjunto de ellas. En este tema se explica cómo eliminar esta reserva y cómo volver a crearla con una ACL restringida.  
  
 En [!INCLUDE[wv](../../../../includes/wv-md.md)] o [!INCLUDE[lserver](../../../../includes/lserver-md.md)] puede ver todas las reservas de direcciones URL de HTTP desde un símbolo del sistema con permisos elevados escribiendo `netsh http show urlacl`.  En el ejemplo siguiente se muestra el aspecto que debe tener una reserva de direcciones URL de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
```  
Reserved URL : http://+:80/Temporary_Listen_Addresses/  
        User: \Everyone  
            Listen: Yes  
            Delegate: No  
            SDDL: D:(A;;GX;;;WD)  
```  
  
 La reserva consta de una plantilla de dirección URL usada cuando una aplicación [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] emplea un enlace HTTP doble para la comunicación dúplex. Las direcciones URL con este formato permiten que un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] devuelva mensajes al cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] al comunicarse sobre un enlace HTTP doble. Todos los usuarios tienen permiso para realizar escuchas en la dirección URL, pero no para delegar la escucha en otro proceso. Por último, la ACL se describe en el lenguaje de definición de descriptor de seguridad (SSDL). [!INCLUDE[crabout](../../../../includes/crabout-md.md)]SSDL, vea [SSDL](http://go.microsoft.com/fwlink/?LinkId=136789)  
  
### <a name="to-delete-the-wcf-url-reservation"></a>Para eliminar la reserva de direcciones URL de WCF  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, haga clic en **Accesorios**, haga clic en **símbolo** y haga clic en **ejecutar como Administrador de** en el menú contextual que aparece. Haga clic en **continuar** en la ventana de Control de cuentas de usuario (UAC) que podría solicitar permiso para continuar.  
  
2.  Escriba en **netsh http eliminar dirección url de urlacl = http: / / +:80/Temporary_Listen_Addresses/** en la ventana de símbolo del sistema.  
  
3.  Si la reserva se elimina correctamente, se muestra el mensaje siguiente: **Reserva de direcciones URL que se eliminó correctamente**  
  
## <a name="creating-a-new-security-group-and-new-restricted-url-reservation"></a>Crear un nuevo grupo de seguridad y una nueva reserva de direcciones URL restringida  
 Para reemplazar la reserva de direcciones URL de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] por una reserva restringida, primero debe crear un nuevo grupo de seguridad. Hay dos maneras de hacerlo: desde un símbolo del sistema o desde la consola de administración del equipo. Opte por una de ellas.  
  
#### <a name="to-create-a-new-security-group-from-a-command-prompt"></a>Para crear un nuevo grupo de seguridad desde un símbolo del sistema  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, haga clic en **Accesorios**, haga clic en **símbolo** y haga clic en **ejecutar como Administrador de** en el menú contextual que aparece. Haga clic en **continuar** en la ventana de Control de cuentas de usuario (UAC) que podría solicitar permiso para continuar.  
  
2.  Escriba en **net localgroup "\<el nombre del grupo de seguridad >" / comment: "\<descripción del grupo de seguridad >" /Add** en el símbolo del sistema. Reemplazar  **\<el nombre del grupo de seguridad >** con el nombre del grupo de seguridad que desea crear y  **\<descripción del grupo de seguridad >** con una descripción apropiada para el grupo de seguridad.  
  
3.  Si el grupo de seguridad se crea correctamente, se muestra el mensaje siguiente: **El comando que se completó correctamente.**  
  
#### <a name="to-create-a-new-security-group-from-the-computer-management-console"></a>Para crear un nuevo grupo de seguridad desde la consola de administración del equipo  
  
1.  Haga clic en **iniciar**, haga clic en **el Panel de Control**, haga clic en **herramientas administrativas**y haga clic en **administración de equipos** para abrir el equipo Consola de administración. Haga clic en **continuar** en la ventana de Control de cuentas de usuario (UAC) que podría solicitar permiso para continuar.  
  
2.  Haga clic en **herramientas del sistema**, haga clic en **usuarios y grupos locales**, haga clic en **grupos** carpeta y haga clic en **nuevo grupo** en el menú contextual que aparece. Tipo en lo que se desea **nombre del grupo de**, **descripción** y otros detalles de este nuevo grupo de seguridad y haga clic en el **crear** botón para crear el grupo de seguridad.  
  
#### <a name="to-create-the-restricted-url-reservation"></a>Para crear la reserva de direcciones URL restringida  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, haga clic en **Accesorios**, haga clic en **símbolo** y haga clic en **ejecutar como Administrador de** en el menú contextual que aparece. Haga clic en **continuar** en la ventana de Control de cuentas de usuario (UAC) que podría solicitar permiso para continuar.  
  
2.  Escriba en **netsh http agregar dirección url urlacl = http: / / +: 80/Temporary_Listen_Addresses/usuario = "\<nombre de equipo >\\< nombre del grupo de seguridad\>**  en el símbolo del sistema. Reemplazar  **\<nombre de equipo >** con el nombre del equipo en el que debe crearse el grupo y  **\<el nombre del grupo de seguridad >** con el nombre del grupo de seguridad que creó anteriormente.  
  
3.  Si la reserva se crea correctamente, se muestra el mensaje siguiente: **Reserva de direcciones URL se agregó correctamente**.
