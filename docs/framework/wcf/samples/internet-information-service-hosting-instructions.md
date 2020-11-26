---
title: Instrucciones de hospedaje Internet Information Services
ms.date: 03/30/2017
ms.assetid: 959a21c8-9d9d-4757-b255-4e57793ae9d6
ms.openlocfilehash: 151c5ba8dd79e8554e7d79fb5b8182740b0be18e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96237695"
---
# <a name="internet-information-service-hosting-instructions"></a>Instrucciones de hospedaje Internet Information Services

Para ejecutar los ejemplos que son hospedados por Internet Information Services (IIS), debe asegurarse de que IIS está instalado correctamente y se está ejecutando.  
  
### <a name="to-install-iis-version-75-on-windows-server-2008-r2"></a>Para instalar la versión 7.5 de IIS en Windows Server 2008 R2  
  
1. En **Administrador del servidor**, seleccione **roles.** En **Resumen de roles**, haga clic en **Agregar roles**.  
  
2. Haga clic en **siguiente** para mostrar el cuadro de diálogo **Seleccionar roles de servidor** .  
  
3. Seleccione **servidor de aplicaciones** en la lista **roles** y, a continuación, haga clic en **siguiente** dos veces para mostrar el cuadro de diálogo **seleccionar servicios de rol** para el rol servidor de aplicaciones.  
  
4. Active la casilla **servidor Web (IIS)** . Si se le pide que instale características y servicios de rol adicionales, haga clic en **Agregar características necesarias**. Haga clic en **siguiente** dos veces para mostrar el cuadro de diálogo **seleccionar servicios de rol** para el rol servidor Web (IIS).  
  
5. Expanda **herramientas de administración** y, a continuación, compatibilidad con la **Administración de IIS 6**. Seleccione **herramientas de scripting de IIS 6**. Si se le pide que instale características y servicios de rol adicionales, haga clic en **Agregar servicios de rol requeridos**. Haga clic en **Next**.  
  
6. Si el Resumen de selecciones es correcto, haga clic en **instalar**.  
  
7. Cuando finalice la instalación, haga clic en **cerrar**.  
  
### <a name="to-install-iis-version-75-on-windows-7"></a>Para instalar IIS versión 7.5 en Windows 7  
  
1. Haga clic en **Inicio** y, a continuación, en **Panel de control**.  
  
2. Abra el grupo **programas** .  
  
3. En **programas y características**, haga clic en **activar o desactivar las características de Windows**.  
  
4. Se muestra el cuadro de diálogo **control de cuentas de usuario** . Haga clic en **Continuar**.  
  
5. Se muestra el cuadro de diálogo **características de Windows** . Expanda el elemento con la etiqueta **Internet Information Services**.  
  
6. Expanda el elemento con la etiqueta **World Wide Web Servicios**.  
  
7. Expanda el elemento con la etiqueta **características de desarrollo de aplicaciones**.  
  
8. Asegúrese de que los siguientes elementos están seleccionados:  
  
    1. **Extensibilidad de .NET**  
  
    2. **ASP.NET**  
  
    3. **Extensiones ISAPI**  
  
    4. **Filtros ISAPI**  
  
9. En el elemento con la etiqueta **World Wide Web Servicios**, expanda **características http comunes**.  
  
10. Asegúrese de que está seleccionado **contenido estático** .  
  
11. En el elemento con la etiqueta **World Wide Web Servicios**, expanda **seguridad**.  
  
12. Asegúrese de que la opción **autenticación de Windows** está seleccionada.  
  
13. En el directorio **Internet Information Services** , expanda el elemento con la etiqueta **herramientas de administración web** y, a continuación, seleccione **consola de administración de IIS**.  
  
14. Expanda el elemento con la etiqueta **compatibilidad de administración de IIS 6** y, a continuación, seleccione **herramientas de scripting de IIS 6**.  
  
15. En el directorio **Internet Information Services** , expanda el elemento con la etiqueta **Microsoft .NET Framework 3.5.1** y, a continuación, seleccione **Windows Communication Foundation activación http**.  
  
16. Haga clic en **OK**.  
  
### <a name="to-install-iis-version-70-on-windows-server-2008"></a>Para instalar la versión de IIS 7.0 en Windows Server 2008  
  
1. En **Administrador del servidor**, seleccione **roles**. En **Resumen de roles**, haga clic en **Agregar roles**.  
  
2. Haga clic en **siguiente** para mostrar el cuadro de diálogo **Seleccionar roles de servidor** .  
  
3. Seleccione **servidor de aplicaciones** en la lista **roles** y, a continuación, haga clic en **siguiente** dos veces para mostrar el cuadro de diálogo **seleccionar servicios de rol** para el rol servidor de aplicaciones.  
  
4. Active la casilla **servidor Web (IIS)** . Si se le pide que instale características y servicios de rol adicionales, haga clic en **Agregar características necesarias**. Haga clic en **siguiente** dos veces para mostrar el cuadro de diálogo **seleccionar servicios de rol** para el rol servidor Web (IIS).  
  
5. Expanda **herramientas de administración** y, a continuación, compatibilidad con la **Administración de IIS 6**. Seleccione **herramientas de scripting de IIS 6**. Si se le pide que instale características y servicios de rol adicionales, haga clic en **Agregar servicios de rol requeridos**. Haga clic en **Next**.  
  
6. Si el Resumen de selecciones es correcto, haga clic en **instalar**.  
  
7. Cuando finalice la instalación, haga clic en **cerrar**.  
  
### <a name="to-install-iis-version-70-on-windows-vista"></a>Para instalar IIS versión 7.0 en Windows Vista  
  
1. Haga clic en Inicio y, a continuación, en Panel de control.  
  
2. Seleccione el grupo **programas** .  
  
3. En **programas y características**, haga clic en **activar o desactivar las características de Windows**.  
  
4. Se muestra el cuadro de diálogo **control de cuentas de usuario** . Haga clic en **Continuar**.  
  
5. Se muestra el cuadro de diálogo **características de Windows** . Expanda el elemento con la etiqueta **Internet Information Services**.  
  
6. Expanda el elemento con la etiqueta **World Wide Web Servicios**.  
  
7. Expanda el elemento con la etiqueta **características de desarrollo de aplicaciones**.  
  
8. Asegúrese de que los siguientes elementos están seleccionados:  
  
    1. **Extensibilidad de .NET**  
  
    2. **ASP.NET**  
  
    3. **Extensiones ISAPI**  
  
    4. **Filtros ISAPI**  
  
9. Expanda el elemento con la etiqueta **herramientas de administración web** y, a continuación, seleccione **consola de administración de IIS**.  
  
10. En el elemento con la etiqueta **World Wide Web Servicios**, expanda **características http comunes**.  
  
11. Asegúrese de que está seleccionado **contenido estático** .  
  
12. En el elemento con la etiqueta **World Wide Web Servicios**, expanda **seguridad**.  
  
13. Asegúrese de que la opción **autenticación de Windows** está seleccionada.  
  
14. Expanda el elemento con la etiqueta **compatibilidad de administración de IIS 6** y, a continuación, seleccione **herramientas de scripting de IIS 6**.  
  
15. Expanda el elemento con la etiqueta **Microsoft .NET Framework 3,0** y, a continuación, seleccione **Windows Communication Foundation activación http**.  
  
16. Haga clic en **OK**.  
  
### <a name="to-install-iis-version-60-on-windows-server-2003"></a>Instalar la versión 6.0 de IIS en Windows Server 2003  
  
1. En **administrar su servidor**, haga clic en **Agregar o quitar un rol** y, a continuación, haga clic en **siguiente**.  
  
2. Seleccione **servidor de aplicaciones (IIS, ASP.net)** en la lista **función de servidor** y, a continuación, haga clic en **siguiente**.  
  
3. Active la casilla **habilitar ASP.net** y, a continuación, haga clic en **siguiente**.  
  
4. Si el resumen de selecciones es correcto, haga clic en Siguiente.  
  
### <a name="to-install-iis-version-51-on-windows-xp-with-service-pack-2-and-service-pack-3-installed"></a>Para instalar la versión 5.1 de IIS en Windows XP con Service Pack 2 y Service Pack 3 instalados  
  
1. En el Panel de control, haga clic en **Agregar o quitar programas**.  
  
2. En el cuadro de diálogo **Agregar o quitar programas**, haga clic en **Agregar o quitar componentes de Windows**.  
  
3. En el **Asistente para componentes de Windows**, active la casilla **Internet Information Services (IIS)** y, a continuación, haga clic en **siguiente**.  
  
4. Si aparece el cuadro de diálogo **archivos necesarios** , inserte el disco de instalación del sistema operativo, vaya a la carpeta i386 y, a continuación, haga clic en **Aceptar**.  
  
5. Cuando finalice la instalación, haga clic en **Finalizar**.  
  
6. Cierre el cuadro de diálogo **Agregar o quitar programas** y, a continuación, cierre el **Panel de control**.  
  
### <a name="to-verify-the-installation-of-iis-and-aspnet"></a>Para comprobar la instalación de IIS y ASP.NET  
  
1. Guarde el archivo HTML encontrado al final de este tema en el directorio raíz \InetPub\wwwroot y denomínelo Default.aspx.  
  
2. Abra una ventana del explorador.  
  
3. Escriba `http://localhost/Default.aspx` en el cuadro Dirección y, a continuación, presione Entrar.  
  
4. Debe aparecer una página web con el texto "Hello World".  
  
> [!NOTE]
> Cada vez que instale una nueva versión de la .NET Framework, debe volver a registrar aspnet_isapi como una extensión de servicio web para IIS. Para ello, ejecute el comando `aspnet_regiis –I –enable`.  
  
## <a name="sample-code"></a>Código de ejemplo  
  
```xml  
<html>  
   <body>  
       <form >  
           <h3> Hello World  
           </h3>  
       </form>  
   </body>  
</html>  
```
