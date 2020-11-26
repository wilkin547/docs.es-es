---
title: Instrucciones de configuración del directorio virtual
ms.date: 03/30/2017
ms.assetid: 3c62cab5-81a4-48b6-ac8c-9ce33a85a157
ms.openlocfilehash: dba6547888935ccf36ec0924fd3c95e8fbda5688
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96243656"
---
# <a name="virtual-directory-setup-instructions"></a>Instrucciones de configuración del directorio virtual

Los ejemplos de Windows Communication Foundation (WCF) están diseñados para compartir un directorio virtual común denominado servicemodelsamples que se asigna a la carpeta%SystemDrive%\inetpub\wwwroot\servicemodelsamples.  
  
> [!NOTE]
> %SystemDrive% acostumbra a ser C: o D:, según la ubicación de la unidad en que está instalado Internet Information Services (IIS).  
  
 Puede ejecutar los archivos Setupvroot.bat y Cleanupvroot.bat desde el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md) para crear el directorio virtual. Si prefiere crear manualmente el directorio virtual, utilice los procedimientos siguientes.  
  
## <a name="procedures"></a>Procedimientos  
  
#### <a name="to-create-a-virtual-directory-in-iis-70-or-75"></a>Para crear un directorio virtual en IIS 7,0 o 7,5  
  
1. En el menú **Inicio** , haga clic en **Ejecutar** y, a continuación, escriba **inetmgr** para abrir el complemento MMC de Internet Information Services (IIS).  
  
2. En el panel izquierdo, expanda el nodo con el nombre del equipo y, a continuación, expanda el nodo **sitios** .  
  
3. Haga clic con el botón secundario en **sitio web predeterminado** y, a continuación, seleccione **Agregar aplicación** para abrir la **ventana Agregar aplicación**.  
  
4. En la ventana de, escriba `servicemodelsamples` como el alias del directorio virtual que va a crear.  
  
5. Cree el siguiente directorio: %SystemDrive%\inetpub\wwwroot\servicemodelsamples  
  
6. Especifique la ruta de acceso física a %SystemDrive%\inetpub\wwwroot\servicemodelsamples.  La mayoría de los ejemplos de WCF copian los archivos ejecutables de servicio a esta ubicación cuando se compilan.  
  
7. Haga clic en **OK**. Ahora se crea la aplicación web para los ejemplos de WCF.  
  
    > [!NOTE]
    > Esta tarea debe realizarse una sola vez, ya que todos los ejemplos de WCF usan la misma aplicación web servicemodelsamples.  
  
    > [!NOTE]
    > En esta documentación, el término `virtual directory` es sinónimo de `Web application`.  
  
     Además de crear el directorio virtual, también debe establecer sus propiedades para permitir la ejecución de los servicios WCF. Consulte a continuación para más información.  
  
#### <a name="to-create-a-virtual-directory-in-iis-51-or-60"></a>Para crear un directorio virtual en IIS 5.1 o 6.0  
  
1. Abra una ventana del símbolo del sistema y escriba `start inetmgr` para abrir el complemento MMC Internet Information Services (IIS).  
  
2. En el panel izquierdo, expanda el nodo con el nombre del equipo y, a continuación, expanda el nodo **sitios web** .  
  
3. Haga clic con el botón secundario en **sitio web predeterminado** y seleccione **nuevo, directorio virtual** para abrir el Asistente para crear un directorio virtual.  
  
4. En el asistente, escriba `servicemodelsamples` como el alias del directorio virtual que va a crear.  
  
5. Especifique la ruta de acceso a %SystemDrive%\inetpub\wwwroot\servicemodelsamples. La mayoría de los ejemplos de WCF copian los archivos ejecutables de servicio a esta ubicación cuando se compilan.  
  
6. Haga clic en **Next**.  
  
7. De forma predeterminada, las casillas siguientes están activadas:  
  
    - **Lectura**  
  
    - **Ejecutar scripts (como ASP)**  
  
8. Haga clic en **siguiente** y, a continuación, haga clic en **Finalizar** para completar el asistente.  
  
    > [!NOTE]
    > Esta tarea solo se debe realizar una vez porque todos los ejemplos de WCF usan el mismo directorio virtual servicemodelsamples.  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-70-or-75"></a>Para establecer propiedades adicionales del directorio virtual en IIS 7,0 o 7,5  
  
1. Haga clic en el nodo servicemodelsamples. Se muestran dos vistas en la parte inferior de la ventana. Seleccione la **vista características** si aún no está seleccionada.  
  
2. Haga doble clic en la entrada para el **examen de directorios**.  
  
3. En el panel acciones, seleccione la opción **Habilitar** . Esto permite tener acceso al directorio del directorio mediante Internet Explorer, lo que resulta útil cuando se depura un servicio.  
  
 Finalmente, debe establecer las propiedades de seguridad de la carpeta servicemodelsamples para permitir que otros puedan obtener acceso a ella. Consulte a continuación para más información.  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-51-or-60"></a>Para establecer propiedades de directorio virtual adicionales en IIS 5.1 o 6.0  
  
1. Haga clic con el botón secundario en el nodo servicemodelsamples y, a continuación, haga clic en **propiedades**.  
  
2. De forma predeterminada, las casillas siguientes están activadas:  
  
    - **Lectura**  
  
    - **Registrar visitas**  
  
    - **Indexar este recurso**  
  
3. Active la casilla **examen de directorios** . Esto permite tener acceso al directorio del directorio mediante Internet Explorer, lo que resulta útil cuando se depura un servicio.  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-70-or-75"></a>Para establecer las propiedades de seguridad de la carpeta en IIS 7,0 o 7,5  
  
1. Navegue hasta %SystemDrive%\inetpub\wwwroot\servicemodelsamples.  
  
2. Haga clic con el botón secundario en la carpeta servicemodelsamples y haga clic en **compartir** o **compartir con**.  
  
3. Haga clic en la flecha abajo a la izquierda del botón **Agregar** .  
  
4. Seleccione la entrada **Buscar** . Se abre la ventana **Seleccionar usuarios o grupos** .  
  
5. Haga clic en **Avanzadas**.  
  
6. Haga clic en **Ubicaciones**. La ventana **ubicaciones** ahora está abierta.  
  
7. Seleccione la entrada para el equipo que se está utilizando. Es importante seleccionar el equipo local y no una entrada para cualquier dominio o red de la lista. Después de haber seleccionado el equipo, haga clic en **Aceptar**.  
  
8. Haz clic en **Buscar ahora**. De este modo se rellenan los resultados de la búsqueda con objetos asociados al equipo local.  
  
9. Busque la entrada **IIS_IUSRS** en la columna **nombre (nombre distintivo relativo)** . Seleccione la entrada y haga clic en **Aceptar** para cerrar la ventana Resultados de la búsqueda.  
  
10. Haga clic en **Aceptar** para cerrar la ventana **Seleccionar usuarios o grupos** .  
  
11. Haga clic en **compartir** para conservar los cambios.  
  
12. Una vez completados los cambios para habilitar el uso compartido, haga clic en **listo** para cerrar la ventana de **uso compartido de archivos** .  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-51-or-60"></a>Para establecer propiedades de seguridad de la carpeta en IIS 5.1 o 6.0  
  
1. Navegue hasta %SystemDrive%\inetpub\wwwroot\servicemodelsamples.  
  
2. Haga clic con el botón secundario en la carpeta **servicemodelsamples** y, a continuación, haga clic en **compartir y seguridad.**  
  
3. Haga clic en la pestaña **Security** (Seguridad).  
  
4. Si usa IIS 6,0, en el cuadro **nombres de grupos o usuarios** , compruebe si aparece la **cuenta de invitado para Internet** .  
  
     Si no es así:  
  
    1. Haga clic en **Inicio** y después en **Panel de control**.  
  
    2. Si no ve el icono **cuentas de usuario** , haga clic en **cambiar a vista por categorías**.  
  
    3. Haga clic en el icono **cuentas de usuario** .  
  
    4. En "o elija un icono del panel de control", haga clic en **cuentas de usuario**.  
  
    5. En el cuadro de diálogo **cuentas de usuario** , haga clic en la pestaña **Opciones avanzadas** .  
  
    6. Haga clic en **Avanzadas**.  
  
    7. En el cuadro de diálogo **usuarios y grupos locales** , haga clic para expandir la carpeta **usuarios** .  
  
    8. En el panel derecho, haga doble clic en **cuenta de invitado para Internet**.  
  
    9. En el cuadro de diálogo **propiedades** , copie el nombre usado como cuenta de invitado para Internet. De forma predeterminada, el nombre comienza con "USR_" seguido por el nombre del equipo.  
  
    10. Cierre el cuadro de diálogo **Propiedades** .  
  
    11. Cierre el cuadro de diálogo **usuarios y grupos locales** .  
  
    12. Cierre el cuadro de diálogo **cuentas de usuario** .  
  
    13. Cierre el cuadro de diálogo otras **cuentas de usuario** .  
  
    14. En el cuadro de diálogo **propiedades de servicemodelsamples** , en la pestaña **seguridad** , haga clic en **Agregar**.  
  
    15. Escriba el nombre del equipo seguido de una barra diagonal inversa y, a continuación, pegue el nombre de la cuenta de usuario de Internet, por ejemplo, myMachineName \\ % InternetGuestAccountName%  
  
    16. Haga clic en **Comprobar nombres** para comprobar la adición. Si es válido, el nombre está en mayúsculas y subrayado.  
  
5. Para IIS 6,0, compruebe también que el servicio de red aparece en el cuadro **nombres de grupos o usuarios** .  
  
     Si el servicio de red no está en la lista:  
  
    1. Haga clic en **Agregar**.  
  
    2. En el cuadro de diálogo **Seleccionar usuarios o grupos** , escriba el nombre del equipo seguido de una barra diagonal inversa.  
  
    3. Escriba **Service** después de la barra diagonal inversa (sin espacio).  
  
    4. Haga clic en **Comprobar nombres**.  
  
    5. Si se encuentran varios nombres, seleccione **servicio de red** y haga clic en **Aceptar**.  
  
    6. Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Seleccionar usuarios o grupos** .  
  
6. Si usa Windows XP SP2 con IIS 5,1, compruebe que la cuenta de invitado para Internet y ASPNET aparecen en el cuadro **nombres de grupos o usuarios** .  
  
     Tenga en cuenta que el usuario ASPNET puede ser miembro del grupo de seguridad **usuarios** integrados. Si es así, si el grupo **usuarios** aparece en el cuadro de diálogo, no es necesario agregarlo como un elemento independiente a la lista de usuarios permitidos.  
  
     Para comprobar si ASPNET forma parte del grupo de seguridad de **usuarios** :  
  
    1. En el menú **Inicio** , haga clic en **Panel de control**.  
  
    2. Haga clic en el icono **cuentas de usuario** .  
  
    3. En la columna **Grupo** , compruebe que el valor de **ASPNET** es "usuarios".  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de hospedaje Internet Information Services](internet-information-service-hosting-instructions.md)
