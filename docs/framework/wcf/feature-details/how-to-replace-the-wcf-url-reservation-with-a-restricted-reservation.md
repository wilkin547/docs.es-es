---
title: "C&#243;mo: Reemplazar la reserva de direcciones URL de WCF por una reserva restringida | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2754d223-79fc-4e2b-a6ce-989889f2abfa
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# C&#243;mo: Reemplazar la reserva de direcciones URL de WCF por una reserva restringida
Una reserva de direcciones URL le permite restringir quién puede recibir mensajes desde una URL o un conjunto de ellas.Una reserva consta de una plantilla de dirección URL, una lista de control de acceso \(ACL\) y un conjunto de marcas.La plantilla de dirección URL define a qué direcciones URL afecta la reserva.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] cómo se procesan las plantillas de dirección URL, vea [Enrutar solicitudes entrantes](http://go.microsoft.com/fwlink/?LinkId=136764).La ACL determina qué usuario o grupo de usuarios pueden recibir mensajes desde las direcciones URL especificadas.Las marcas indican si la reserva proporciona permiso a un usuario o a un grupo de ellos para realizar escuchas directamente en la dirección URL o delega el permiso de escucha en otro proceso.  
  
 Como parte de la configuración predeterminada del sistema operativo, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] crea una reserva accesible globalmente para el puerto 80 que permite a todos los usuarios ejecutar aplicaciones que usan un enlace HTTP doble para la comunicación dúplex.Dado que la ACL en esta reserva es para todos los usuarios, los administradores no pueden conceder o denegar explícitamente el permiso para realizar escuchas en una dirección URL o en un conjunto de ellas.En este tema se explica cómo eliminar esta reserva y cómo volver a crearla con una ACL restringida.  
  
 En [!INCLUDE[wv](../../../../includes/wv-md.md)] o [!INCLUDE[lserver](../../../../includes/lserver-md.md)] puede ver todas las reservas de direcciones URL de HTTP desde un símbolo del sistema con permisos elevados escribiendo `netsh http show urlacl`.En el ejemplo siguiente se muestra el aspecto que debe tener una reserva de direcciones URL de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
```  
Reserved URL : http://+:80/Temporary_Listen_Addresses/  
        User: \Everyone  
            Listen: Yes  
            Delegate: No  
            SDDL: D:(A;;GX;;;WD)  
```  
  
 La reserva consta de una plantilla de dirección URL usada cuando una aplicación [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] emplea un enlace HTTP doble para la comunicación dúplex.Las direcciones URL con este formato permiten que un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] devuelva mensajes al cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] al comunicarse sobre un enlace HTTP doble.Todos los usuarios tienen permiso para realizar escuchas en la dirección URL, pero no para delegar la escucha en otro proceso.Por último, la ACL se describe en el lenguaje de definición de descriptor de seguridad \(SSDL\).[!INCLUDE[crabout](../../../../includes/crabout-md.md)] SSDL, vea [SSDL](http://go.microsoft.com/fwlink/?LinkId=136789)  
  
### Para eliminar la reserva de direcciones URL de WCF  
  
1.  Haga clic en **Inicio**, seleccione sucesivamente **Todos los programas** y **Accesorios**, haga clic con el botón secundario en **Símbolo del sistema** y, a continuación, haga clic en **Ejecutar como administrador** en el menú contextual que aparece.Haga clic en **Continuar** en la ventana Control de cuentas de usuario \(UAC\) que podría solicitar permiso para continuar.  
  
2.  Escriba **netsh http delete urlacl url\=http:\/\/\+:80\/Temporary\_Listen\_Addresses\/** en la ventana del símbolo del sistema.  
  
3.  Si la reserva se elimina correctamente, se muestra el mensaje siguiente:**URL reservation successfully deleted**  
  
## Crear un nuevo grupo de seguridad y una nueva reserva de direcciones URL restringida  
 Para reemplazar la reserva de direcciones URL de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] por una reserva restringida, primero debe crear un nuevo grupo de seguridad.Hay dos maneras de hacerlo: desde un símbolo del sistema o desde la consola de administración del equipo.Opte por una de ellas.  
  
#### Para crear un nuevo grupo de seguridad desde un símbolo del sistema  
  
1.  Haga clic en **Inicio**, seleccione sucesivamente **Todos los programas** y **Accesorios**, haga clic con el botón secundario en **Símbolo del sistema** y, a continuación, haga clic en **Ejecutar como administrador** en el menú contextual que aparece.Haga clic en **Continuar** en la ventana Control de cuentas de usuario \(UAC\) que podría solicitar permiso para continuar.  
  
2.  Escriba **net localgroup "\<security group name\>" \/comment:"\<security group description\>" \/add** en el símbolo del sistema.Reemplace **\<security group name\>** con el nombre del grupo de seguridad que desea crear y **\<security group description\>** con una descripción apropiada para dicho grupo.  
  
3.  Si el grupo de seguridad se crea correctamente, se muestra el mensaje siguiente:**The command completed successfully.**  
  
#### Para crear un nuevo grupo de seguridad desde la consola de administración del equipo  
  
1.  Haga clic en **Inicio**, **Panel de control**, **Herramientas administrativas** y **Administración de equipos** para mostrar la consola de administración del equipo.Haga clic en **Continuar** en la ventana Control de cuentas de usuario \(UAC\) que podría solicitar permiso para continuar.  
  
2.  Haga clic en **Herramientas del sistema** y en **Usuarios y grupos locales**, haga clic con el botón secundario en la carpeta **Grupos** y, por último, haga clic en **Nuevo grupo** en el menú contextual que aparece.Escriba el **Nombre de grupo** y la **Descripción** deseados, así como la información necesaria para este nuevo grupo de seguridad, y, a continuación, haga clic en el botón **Crear** para crear el grupo de seguridad.  
  
#### Para crear la reserva de direcciones URL restringida  
  
1.  Haga clic en **Inicio**, seleccione sucesivamente **Todos los programas** y **Accesorios**, haga clic con el botón secundario en **Símbolo del sistema** y, a continuación, haga clic en **Ejecutar como administrador** en el menú contextual que aparece.Haga clic en **Continuar** en la ventana Control de cuentas de usuario \(UAC\) que podría solicitar permiso para continuar.  
  
2.  Escriba **netsh http add urlacl url\=http:\/\/\+:80\/Temporary\_Listen\_Addresses\/ user\="\<machine name\>\\\<security group name\>** en el símbolo del sistema.Reemplace **\<machine name\>** con el nombre del equipo en el que se debe crear el grupo y **\<security group name\>** con el nombre del grupo de seguridad creado anteriormente.  
  
3.  Si la reserva se crea correctamente, se muestra el mensaje siguiente:**URL reservation successfully added**.