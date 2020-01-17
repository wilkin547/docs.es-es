---
title: 'Cómo: Reemplazar la reserva de direcciones URL de WCF por una reserva restringida'
ms.date: 03/30/2017
ms.assetid: 2754d223-79fc-4e2b-a6ce-989889f2abfa
ms.openlocfilehash: fc50a0e31a0c323b695ada6565743fa19c1d4c2a
ms.sourcegitcommit: 09b4090b78f52fd09b0e430cd4b26576f1fdf96e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2020
ms.locfileid: "76212193"
---
# <a name="how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation"></a>Cómo: Reemplazar la reserva de direcciones URL de WCF por una reserva restringida

Una reserva de direcciones URL le permite restringir quién puede recibir mensajes desde una URL o un conjunto de ellas. Una reserva consta de una plantilla de dirección URL, una lista de control de acceso (ACL) y un conjunto de marcas. La plantilla de dirección URL define a qué direcciones URL afecta la reserva. Para obtener más información sobre cómo se procesan las plantillas de dirección URL, vea [enrutar solicitudes entrantes](/windows/win32/http/routing-incoming-requests). La ACL determina qué usuario o grupo de usuarios pueden recibir mensajes desde las direcciones URL especificadas. Las marcas indican si la reserva proporciona permiso a un usuario o a un grupo de ellos para realizar escuchas directamente en la dirección URL o delega el permiso de escucha en otro proceso.  
  
 Como parte de la configuración predeterminada del sistema operativo, Windows Communication Foundation (WCF) crea una reserva accesible globalmente para el puerto 80 a fin de permitir que todos los usuarios ejecuten aplicaciones que usan un enlace HTTP doble para la comunicación dúplex. Dado que la ACL en esta reserva es para todos los usuarios, los administradores no pueden conceder o denegar explícitamente el permiso para realizar escuchas en una dirección URL o en un conjunto de ellas. En este tema se explica cómo eliminar esta reserva y cómo volver a crearla con una ACL restringida.  
  
En Windows Vista o Windows Server 2008, puede ver todas las reservas de direcciones URL HTTP desde un símbolo del sistema con privilegios elevados si escribe `netsh http show urlacl`. En el ejemplo siguiente se muestra el aspecto de una reserva de direcciones URL de WCF:

```
Reserved URL : http://+:80/Temporary_Listen_Addresses/  
        User: \Everyone  
            Listen: Yes  
            Delegate: No  
            SDDL: D:(A;;GX;;;WD)  
```

 La reserva consta de una plantilla de dirección URL que se usa cuando una aplicación WCF usa un enlace HTTP dual para la comunicación dúplex. Las direcciones URL de este formulario se utilizan para que un servicio WCF envíe mensajes de vuelta al cliente WCF al comunicarse a través de un enlace HTTP dual. Todos los usuarios tienen permiso para realizar escuchas en la dirección URL, pero no para delegar la escucha en otro proceso. Por último, la ACL se describe en el lenguaje de definición de descriptor de seguridad (SSDL). Para obtener más información sobre SSDL, vea [SSDL](/windows/win32/secauthz/security-descriptor-definition-language)  
  
## <a name="to-delete-the-wcf-url-reservation"></a>Para eliminar la reserva de direcciones URL de WCF  
  
1. Haga clic en **Inicio**, seleccione **todos los programas**, **accesorios**, haga clic con el botón secundario en **símbolo del sistema** y haga clic en **Ejecutar como administrador** en el menú contextual que aparece. Haga clic en **continuar** en la ventana control de cuentas de usuario (UAC), que podría pedir permisos para continuar.  
  
2. Escriba **netsh http Delete urlacl URL =http://+:80/Temporary_Listen_Addresses/** en la ventana del símbolo del sistema.  
  
3. Si la reserva se elimina correctamente, se muestra el mensaje siguiente: **Reserva de direcciones URL eliminada correctamente**  
  
## <a name="creating-a-new-security-group-and-new-restricted-url-reservation"></a>Crear un nuevo grupo de seguridad y una nueva reserva de direcciones URL restringida  
 Para reemplazar la reserva de direcciones URL de WCF por una reserva restringida, primero debe crear un nuevo grupo de seguridad. Hay dos maneras de hacerlo: desde un símbolo del sistema o desde la consola de administración del equipo. Opte por una de ellas.  
  
### <a name="to-create-a-new-security-group-from-a-command-prompt"></a>Para crear un nuevo grupo de seguridad desde un símbolo del sistema  
  
1. Haga clic en **Inicio**, seleccione **todos los programas**, **accesorios**, haga clic con el botón secundario en **símbolo del sistema** y haga clic en **Ejecutar como administrador** en el menú contextual que aparece. Haga clic en **continuar** en la ventana control de cuentas de usuario (UAC), que podría pedir permisos para continuar.  
  
2. Escriba **net localgroup "\<nombre de grupo de seguridad >"/comment: "\<Descripción del grupo de seguridad >"/Add "** en el símbolo del sistema. Reemplace **\<nombre del grupo de seguridad >** por el nombre del grupo de seguridad que desea crear y **\<Descripción del grupo de seguridad >** con una descripción adecuada para el grupo de seguridad.  
  
3. Si el grupo de seguridad se crea correctamente, se muestra el mensaje siguiente: **El comando se completó correctamente.**  
  
### <a name="to-create-a-new-security-group-from-the-computer-management-console"></a>Para crear un nuevo grupo de seguridad desde la consola de administración del equipo  
  
1. Haga clic en **Inicio**, en **Panel de control**, en **herramientas administrativas**y en **Administración de equipos** para abrir la consola administración de equipos. Haga clic en **continuar** en la ventana control de cuentas de usuario (UAC), que podría pedir permisos para continuar.  
  
2. Haga clic en **herramientas del sistema**, en **usuarios y grupos locales**, haga clic con el botón secundario en carpeta **grupos** y haga clic en **nuevo grupo** en el menú contextual que aparece. Escriba el nombre de **Grupo**deseado, la **Descripción** y otros detalles de este nuevo grupo de seguridad y haga clic en el botón **crear** para crear el grupo de seguridad.  
  
### <a name="to-create-the-restricted-url-reservation"></a>Para crear la reserva de direcciones URL restringida  
  
1. Haga clic en **Inicio**, seleccione **todos los programas**, **accesorios**, haga clic con el botón secundario en **símbolo del sistema** y haga clic en **Ejecutar como administrador** en el menú contextual que aparece. Haga clic en **continuar** en la ventana control de cuentas de usuario (UAC), que podría pedir permisos para continuar.  
  
2. Escriba **netsh http Add urlacl URL =http://+:80/Temporary_Listen_Addresses/ user = "\< nombre de equipo >\\ < nombre de grupo de seguridad\>** en el símbolo del sistema. Reemplace **\<nombre** del equipo > por el nombre del equipo en el que se debe crear el grupo y **\<nombre del grupo de seguridad >** por el nombre del grupo de seguridad que creó anteriormente.  
  
3. Si la reserva se crea correctamente, se muestra el mensaje siguiente: **Reserva de direcciones URL agregada correctamente**.
