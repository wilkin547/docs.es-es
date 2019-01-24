---
title: Instrucciones de configuración del directorio virtual
ms.date: 03/30/2017
ms.assetid: 3c62cab5-81a4-48b6-ac8c-9ce33a85a157
ms.openlocfilehash: 0f32fd6d65db529ba1015dedd98f99efd7f408c4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54588118"
---
# <a name="virtual-directory-setup-instructions"></a>Instrucciones de configuración del directorio virtual
Los ejemplos de Windows Communication Foundation (WCF) están diseñados para compartir un directorio virtual común denominado servicemodelsamples que está asignado a la carpeta %SystemDrive%\inetpub\wwwroot\servicemodelsamples.  
  
> [!NOTE]
>  %SystemDrive% acostumbra a ser C: o D:, según la ubicación de la unidad en que está instalado Internet Information Services (IIS).  
  
 Puede ejecutar los archivos Setupvroot.bat y Cleanupvroot.bat desde el [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) para crear el directorio virtual. Si prefiere crear manualmente el directorio virtual, utilice los procedimientos siguientes.  
  
## <a name="procedures"></a>Procedimientos  
  
#### <a name="to-create-a-virtual-directory-in-iis-70-or-75"></a>Para crear un directorio virtual en IIS 7.0 o 7.5  
  
1.  Desde el **iniciar** menú, haga clic en **ejecutar**, a continuación, escriba **inetmgr** para abrir el complemento MMC de Internet Information Services (IIS).  
  
2.  En el panel izquierdo, expanda el nodo con el nombre del equipo y, a continuación, expanda el **sitios** nodo.  
  
3.  Haga clic en **sitio Web predeterminado**y, a continuación, seleccione **Agregar aplicación** para abrir el **ventana Agregar aplicación**.  
  
4.  En la ventana, escriba `servicemodelsamples` como alias para el directorio virtual que está creando.  
  
5.  Cree el siguiente directorio: %SystemDrive%\inetpub\wwwroot\servicemodelsamples  
  
6.  Especifique la ruta de acceso física a %SystemDrive%\inetpub\wwwroot\servicemodelsamples.  La mayoría de los ejemplos de WCF copian los archivos ejecutables de servicio a esta ubicación cuando se compilan.  
  
7.  Haga clic en **Aceptar**. Ahora se crea la aplicación web para los ejemplos de WCF.  
  
    > [!NOTE]
    >  Esta tarea debe realizarse una sola vez, porque todos los ejemplos WCF usan la misma aplicación Web servicemodelsamples.  
  
    > [!NOTE]
    >  En esta documentación, el término `virtual directory` es sinónimo de `Web application`.  
  
     Además de crear el directorio virtual, también debe establecer sus propiedades para permitir que se ejecuten los servicios WCF. Para obtener información más detallada, vea a continuación.  
  
#### <a name="to-create-a-virtual-directory-in-iis-51-or-60"></a>Para crear un directorio virtual en IIS 5.1 o 6.0  
  
1.  Abra una ventana de símbolo del sistema y escriba `start inetmgr` para abrir el complemento MMC de Internet Information Services (IIS).  
  
2.  En el panel izquierdo, expanda el nodo con el nombre del equipo y, a continuación, expanda el **sitios Web** nodo.  
  
3.  Haga clic en **sitio Web predeterminado** y seleccione **nuevo, el directorio Virtual** para abrir el Asistente para crear un directorio Virtual.  
  
4.  En el asistente, escriba `servicemodelsamples` como alias para el directorio virtual que está creando.  
  
5.  Especifique la ruta de acceso a %SystemDrive%\inetpub\wwwroot\servicemodelsamples. La mayoría de los ejemplos de WCF copian los archivos ejecutables de servicio a esta ubicación cuando se compilan.  
  
6.  Haga clic en **Siguiente**.  
  
7.  De forma predeterminada, las casillas siguientes están activadas:  
  
    -   **Read**  
  
    -   **Ejecutar secuencias de comandos (por ejemplo, ASP)**  
  
8.  Haga clic en **siguiente**y, a continuación, haga clic en **finalizar** para completar el asistente.  
  
    > [!NOTE]
    >  Esta tarea debe realizarse una sola vez porque todos los ejemplos WCF usan el mismo directorio virtual servicemodelsamples.  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-70-or-75"></a>Para establecer las propiedades del directorio virtual adicionales en IIS 7.0 o 7.5  
  
1.  Haga clic en el nodo servicemodelsamples. Se muestran dos vistas en la parte inferior de la ventana. Seleccione **vista características** si aún no está seleccionado.  
  
2.  Haga doble clic en la entrada de **examen de directorios**.  
  
3.  En el panel Acciones, seleccione el **habilitar** opción. Esto permite tener acceso al directorio del directorio mediante Internet Explorer, lo que resulta útil cuando se depura un servicio.  
  
 Finalmente, debe establecer las propiedades de seguridad de la carpeta servicemodelsamples para permitir que otros puedan obtener acceso a ella. Para obtener información más detallada, vea a continuación.  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-51-or-60"></a>Para establecer propiedades de directorio virtual adicionales en IIS 5.1 o 6.0  
  
1.  Haga clic en el nodo servicemodelsamples y, a continuación, haga clic en **propiedades**.  
  
2.  De forma predeterminada, las casillas siguientes están activadas:  
  
    -   **Read**  
  
    -   **Registrar visitas**  
  
    -   **Indizar este recurso**  
  
3.  Seleccione el **examen de directorios** casilla de verificación. Esto permite tener acceso al directorio del directorio mediante Internet Explorer, lo que resulta útil cuando se depura un servicio.  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-70-or-75"></a>Para establecer las propiedades de seguridad de la carpeta en IIS 7.0 o 7.5  
  
1.  Navegue hasta %SystemDrive%\inetpub\wwwroot\servicemodelsamples.  
  
2.  Haga clic en la carpeta servicemodelsamples y haga clic en **Share** o **compartir con**.  
  
3.  Haga clic en la flecha hacia abajo a la izquierda de la **agregar** botón.  
  
4.  Seleccione el **buscar** entrada. El **Seleccionar usuarios o grupos** abre la ventana.  
  
5.  Haga clic en **Avanzado**.  
  
6.  Haga clic en **ubicaciones**. El **ubicaciones** ahora está abierta la ventana.  
  
7.  Seleccione la entrada para el equipo que se está utilizando. Es importante seleccionar el equipo local y no una entrada para cualquier dominio o red de la lista. Después de haber seleccionado el equipo, haga clic en **Aceptar**.  
  
8.  Haga clic en **Buscar ahora**. De este modo se rellenan los resultados de la búsqueda con objetos asociados al equipo local.  
  
9. Buscar el **IIS_IUSRS** entrada en el **nombre (nombre distintivo relativo)** columna. Seleccione esa entrada y haga clic en **Aceptar** cerrar esta ventana de resultados.  
  
10. Haga clic en **Aceptar** para cerrar el **Seleccionar usuarios o grupos** ventana.  
  
11. Haga clic en **Share** para conservar los cambios.  
  
12. Una vez completados los cambios para habilitar el uso compartido, haga clic en **realiza** para cerrar el **uso compartido de archivos** ventana.  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-51-or-60"></a>Para establecer propiedades de seguridad de la carpeta en IIS 5.1 o 6.0  
  
1.  Navegue hasta %SystemDrive%\inetpub\wwwroot\servicemodelsamples.  
  
2.  Haga clic en el **servicemodelsamples** carpeta y, a continuación, haga clic en **compartir y seguridad.**  
  
3.  Haga clic en la pestaña **Seguridad** .  
  
4.  Si está utilizando IIS 6.0, en el **los nombres de usuario o grupo** casilla de verificación si **cuenta de invitado para Internet** aparece.  
  
     Si no está en la lista:  
  
    1.  Haga clic en **Inicio** y después en **Panel de control**.  
  
    2.  Si no ve el **cuentas de usuario** icono, haga clic en **cambiar a vista por categorías**.  
  
    3.  Haga clic en el **cuentas de usuario** icono.  
  
    4.  Bajo "o elija un icono del Panel de Control," haga clic en **cuentas de usuario**.  
  
    5.  En el **cuentas de usuario** cuadro de diálogo, haga clic en el **avanzadas** ficha.  
  
    6.  Haga clic en **Avanzado**.  
  
    7.  En el **usuarios y grupos locales** cuadro de diálogo, haga clic para expandir el **usuarios** carpeta.  
  
    8.  En el panel derecho, haga doble clic en **cuenta de invitado para Internet**.  
  
    9. En el **propiedades** cuadro de diálogo, copie el nombre se usa como la cuenta de invitado de Internet. De forma predeterminada, el nombre comienza con "USR_" seguido por el nombre del equipo.  
  
    10. Cerrar la **propiedades** cuadro de diálogo.  
  
    11. Cerrar la **usuarios y grupos locales** cuadro de diálogo.  
  
    12. Cerrar la **cuentas de usuario** cuadro de diálogo.  
  
    13. Cerrar la otra **cuentas de usuario** cuadro de diálogo.  
  
    14. En el **propiedades de servicemodelsamples** cuadro de diálogo el **seguridad** , haga clic **agregar**.  
  
    15. Escriba el nombre del equipo seguido por una barra diagonal inversa, a continuación, pegue el nombre de la cuenta de usuario de Internet, por ejemplo, myMachineName\\InternetGuestAccountName %  
  
    16. Haga clic en **comprobar nombres** para comprobar la adición. Si es válido, el nombre está en mayúsculas y subrayado.  
  
5.  Para IIS 6.0, compruebe también que el servicio de red aparece en el **los nombres de usuario o grupo** cuadro.  
  
     Si el servicio de red no está en la lista:  
  
    1.  Haga clic en **Agregar**.  
  
    2.  En el **Seleccionar usuarios o grupos** cuadro de diálogo, escriba el nombre del equipo seguido por una barra diagonal inversa.  
  
    3.  Tipo **servicio** después de la barra diagonal inversa (sin espacio).  
  
    4.  Haga clic en **comprobar nombres**.  
  
    5.  Si se encuentran varios nombres, seleccione **NETWORK SERVICE** y haga clic en **Aceptar**.  
  
    6.  Haga clic en **Aceptar** para cerrar el **Seleccionar usuarios o grupos** cuadro de diálogo.  
  
6.  Si utiliza Windows XP SP2 con IIS 5.1, compruebe que cuenta de invitado para Internet y ASPNET aparecen en la **los nombres de usuario o grupo** cuadro.  
  
     Tenga en cuenta que el usuario ASPNET puede ser un miembro de los integrados **usuarios** grupo de seguridad. Si es así, a continuación si el **usuarios** grupo aparece en el cuadro de diálogo, no es necesario agregarlo como un elemento independiente a la lista de usuarios permitidos.  
  
     Para comprobar si ASPNET forma parte de la **usuarios** grupo de seguridad:  
  
    1.  En el **iniciar** menú, haga clic en **Panel de Control**.  
  
    2.  Haga clic en el **cuentas de usuario** icono.  
  
    3.  En el **grupo** columna, compruebe que el valor de **ASPNET** es "Users".  
  
## <a name="see-also"></a>Vea también
- [Instrucciones de hospedaje de Internet Information Services](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md)
