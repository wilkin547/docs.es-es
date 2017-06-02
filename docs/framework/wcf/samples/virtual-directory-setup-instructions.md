---
title: "Instrucciones de configuraci&#243;n del directorio virtual | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: 3c62cab5-81a4-48b6-ac8c-9ce33a85a157
caps.latest.revision: 36
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 36
---
# Instrucciones de configuraci&#243;n del directorio virtual
Los ejemplos [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] comparten un directorio virtual común denominado servicemodelsamples que está asignado a la carpeta %SystemDrive%\\inetpub\\wwwroot\\servicemodelsamples.  
  
> [!NOTE]
>  %SystemDrive% acostumbra a ser C: o D:, según la ubicación de la unidad en que está instalado Internet Information Services \(IIS\).  
  
 Puede ejecutar los archivos Setupvroot.bat y Cleanupvroot.bat desde [Procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) para crear el directorio virtual.Si prefiere crear manualmente el directorio virtual, utilice los procedimientos siguientes.  
  
## Procedimientos  
  
#### Para crear un directorio virtual en IIS 7.0 o 7.5  
  
1.  En el menú **Inicio**, haga clic en **Ejecutar** y escriba **inetmgr** para abrir el complemento MMC de Internet Information Services \(IIS\).  
  
2.  En el panel izquierdo, expanda el nodo con el nombre del equipo y, a continuación, expanda el nodo **Sitios**.  
  
3.  Haga clic con el botón secundario en **Sitio web predeterminado** y, a continuación, seleccione **Agregar aplicación** para abrir la ventana **Agregar aplicación**.  
  
4.  En la ventana, escriba `servicemodelsamples` como alias para el directorio virtual que está creando.  
  
5.  Cree el siguiente directorio: %SystemDrive%\\inetpub\\wwwroot\\servicemodelsamples  
  
6.  Especifique la ruta de acceso física a %SystemDrive%\\inetpub\\wwwroot\\servicemodelsamples.La mayoría de los ejemplos de WCF copian los archivos ejecutables de servicio a esta ubicación cuando se compilan.  
  
7.  Haga clic en **Aceptar**.Ahora se crea la aplicación web para los ejemplos de WCF.  
  
    > [!NOTE]
    >  Esta tarea solo se debe realizar una vez, porque todos los ejemplos de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utilizan la misma aplicación web servicemodelsamples.  
  
    > [!NOTE]
    >  En esta documentación, el término `virtual directory` es sinónimo de `Web application`.  
  
     Además de crear el directorio virtual, también debe establecer sus propiedades para permitir que los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se ejecuten.Para obtener información más detallada, vea a continuación.  
  
#### Para crear un directorio virtual en IIS 5.1 o 6.0  
  
1.  Abra una ventana del símbolo del sistema y escriba `start inetmgr` para abrir el complemento MMC de Internet Information Services \(IIS\).  
  
2.  En el panel izquierdo, expanda el nodo con el nombre del equipo y, a continuación, expanda el nodo **Sitios web**.  
  
3.  Haga clic con el botón secundario en **Sitio Web predeterminado** y seleccione **Nuevo, Directorio virtual** para abrir el asistente para crear un directorio virtual.  
  
4.  En el asistente, escriba `servicemodelsamples` como alias para el directorio virtual que está creando.  
  
5.  Especifique la ruta de acceso a %SystemDrive%\\inetpub\\wwwroot\\servicemodelsamples.La mayoría de los ejemplos [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] copian los archivos ejecutables de servicio a esta ubicación cuando se compilan.  
  
6.  Haga clic en **Siguiente**.  
  
7.  De forma predeterminada, las casillas siguientes están activadas:  
  
    -   **Leer**  
  
    -   **Ejecutar scripts \(como ASP\)**  
  
8.  Haga clic en **Siguiente** y, a continuación, haga clic en **Finalizar** para completar el asistente.  
  
    > [!NOTE]
    >  Esta tarea solo se debe realizar una vez, porque todos los ejemplos [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utilizan el mismo directorio virtual servicemodelsamples.  
  
#### Para establecer propiedades de directorio virtual adicionales en IIS 7.0 o 7.5  
  
1.  Haga clic en el nodo servicemodelsamples.Se muestran dos vistas en la parte inferior de la ventana.Seleccione **Vista Características** si aún no lo está.  
  
2.  Haga doble clic en la entrada de **Examen de directorios**.  
  
3.  En el panel Acciones, seleccione la opción **Habilitar**.Esto permite tener acceso al directorio del directorio mediante Internet Explorer, lo que resulta útil cuando se depura un servicio.  
  
 Finalmente, debe establecer las propiedades de seguridad de la carpeta servicemodelsamples para permitir que otros puedan obtener acceso a ella.Para obtener información más detallada, vea a continuación.  
  
#### Para establecer propiedades de directorio virtual adicionales en IIS 5.1 o 6.0  
  
1.  Haga clic con el botón secundario en el nodo servicemodelsamples y, a continuación, haga clic en **Propiedades**.  
  
2.  De forma predeterminada, las casillas siguientes están activadas:  
  
    -   **Leer**  
  
    -   **Registrar visitas**  
  
    -   **Indizar este recurso**  
  
3.  Active la casilla **Examen de directorios**.Esto permite tener acceso al directorio del directorio mediante Internet Explorer, lo que resulta útil cuando se depura un servicio.  
  
#### Para establecer propiedades de seguridad de la carpeta en IIS 7.0 o 7.5  
  
1.  Navegue hasta %SystemDrive%\\inetpub\\wwwroot\\servicemodelsamples.  
  
2.  Haga clic con el botón secundario en la carpeta servicemodelsamples y haga clic en **Compartir** o **Compartir con**.  
  
3.  Haga clic en la flecha abajo a la izquierda del botón **Agregar**.  
  
4.  Seleccione la entrada **Buscar**.Aparecerá la ventana **Seleccionar usuarios o grupos**.  
  
5.  Haga clic en **Avanzado**.  
  
6.  Haga clic en **Ubicaciones**.La ventana **Ubicaciones** está ahora abierta.  
  
7.  Seleccione la entrada para el equipo que se está utilizando.Es importante seleccionar el equipo local y no una entrada para cualquier dominio o red de la lista.Después de haber seleccionado el equipo, haga clic en **Aceptar**.  
  
8.  Haga clic en **Buscar ahora**.De este modo se rellenan los resultados de la búsqueda con objetos asociados al equipo local.  
  
9. Busque la entrada **IIS\_IUSRS** en la columna **Nombre \(nombre distintivo relativo\)**.Seleccione esa entrada y haga clic en **Aceptar** para cerrar la ventana de resultados de la búsqueda.  
  
10. Haga clic en **Aceptar** para cerrar la ventana **Seleccionar usuarios o grupos**.  
  
11. Haga clic en **Compartir** para conservar los cambios.  
  
12. Después de que se hayan realizado los cambios para habilitar el uso compartido, haga clic en **Hecho** para cerrar la ventana **Uso compartido de archivos**.  
  
#### Para establecer propiedades de seguridad de la carpeta en IIS 5.1 o 6.0  
  
1.  Navegue hasta %SystemDrive%\\inetpub\\wwwroot\\servicemodelsamples.  
  
2.  Haga clic con el botón secundario en la carpeta **servicemodelsamples** y, a continuación, haga clic en **Compartir y seguridad**.  
  
3.  Haga clic en la pestaña **Seguridad**.  
  
4.  Si está utilizando IIS 6.0, en el cuadro **Nombres de grupos o usuarios**, compruebe si **Cuenta de invitado para Internet** está en la lista.  
  
     Si no está en la lista:  
  
    1.  Haga clic en **Inicio** y, a continuación, en **Panel de control**.  
  
    2.  Si no ve el icono **Cuentas de usuario**, haga clic en **Cambiar a vista por categorías**.  
  
    3.  Haga clic en el icono **Cuentas de usuario**.  
  
    4.  Bajo "o elija un icono del Panel de control", haga clic en **Cuentas de usuario**.  
  
    5.  En el cuadro de diálogo **Cuentas de usuario**, haga clic en la pestaña **Avanzadas**.  
  
    6.  Haga clic en **Avanzado**.  
  
    7.  En el cuadro de diálogo **Usuarios y grupos locales**, haga clic para expandir la carpeta **Usuarios**.  
  
    8.  En el panel derecho, haga doble clic en **Cuenta de invitado para Internet**.  
  
    9. En el cuadro de diálogo **Propiedades**, copie el nombre utilizado como cuenta de invitado para Internet.De forma predeterminada, el nombre comienza con "USR\_" seguido por el nombre del equipo.  
  
    10. Cierre el cuadro de diálogo **Propiedades**.  
  
    11. Cierre el cuadro de diálogo **Usuarios y grupos locales**.  
  
    12. Cierre el cuadro de diálogo **Cuentas de usuario**.  
  
    13. Cierre el otro cuadro de diálogo **Cuentas de usuario**.  
  
    14. En el cuadro de diálogo **Propiedades de servicemodelsamples**, en la pestaña **Seguridad**, haga clic en **Agregar**.  
  
    15. Escriba el nombre del equipo seguido por una barra diagonal inversa, pegue el nombre de la cuenta de usuario para Internet \(por ejemplo, myMachineName\\%InternetGuestAccountName%\).  
  
    16. Haga clic en **Comprobar nombres** para comprobar la adición.Si es válido, el nombre está en mayúsculas y subrayado.  
  
5.  Para IIS 6.0, compruebe también que el servicio de red aparece en el cuadro **Nombres de grupos o usuarios**.  
  
     Si el servicio de red no está en la lista:  
  
    1.  Haga clic en **Agregar**.  
  
    2.  En el cuadro de diálogo **Seleccionar usuarios o grupos**, escriba el nombre del equipo seguido por una barra diagonal inversa.  
  
    3.  Escriba service después de la barra diagonal inversa \(sin espacio\).  
  
    4.  Haga clic en **Comprobar nombres**.  
  
    5.  Si se encuentran varios nombres, seleccione **Servicio de red** y haga clic en **Aceptar**.  
  
    6.  Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Seleccionar usuarios o grupos**.  
  
6.  Si está utilizando Windows XP SP2 con IIS 5.1, compruebe que la Cuenta de invitado para internet y ASPNET aparecen en el cuadro **Nombres de grupos o usuarios**.  
  
     Observe que el usuario de ASPNET puede ser un miembro del grupo de seguridad integrado **Usuarios**.En ese caso, si se hace una lista del grupo **Usuarios** en el cuadro de diálogo, no necesita agregarlo como elemento independiente a la lista de usuarios permitidos.  
  
     Para comprobar si ASPNET forma parte del grupo de seguridad **Usuarios**:  
  
    1.  En el menú **Inicio**, haga clic en el **Panel de control**.  
  
    2.  Haga clic en el icono **Cuentas de usuario**.  
  
    3.  En la columna **Grupo**, compruebe que el valor para **ASPNET** es "Usuarios".  
  
## Vea también  
 [Instrucciones de hospedaje Internet Information Services](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md)