---
title: Instrucciones de hospedaje Internet Information Services
ms.date: 03/30/2017
ms.assetid: 959a21c8-9d9d-4757-b255-4e57793ae9d6
ms.openlocfilehash: 92ee270426dbb7fdd166964c1b10e37f280e28f3
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591882"
---
# <a name="internet-information-service-hosting-instructions"></a>Instrucciones de hospedaje Internet Information Services
Para ejecutar los ejemplos que son hospedados por Internet Information Services (IIS), debe asegurarse de que IIS está instalado correctamente y se está ejecutando.  
  
### <a name="to-install-iis-version-75-on-windows-server-2008-r2"></a>Para instalar la versión 7.5 de IIS en Windows Server 2008 R2  
  
1. Desde **administrador del servidor**, seleccione **Roles.** En **resumen de funciones**, haga clic en **agregar Roles**.  
  
2. Haga clic en **siguiente** para mostrar el **seleccionar Roles de servidor** cuadro de diálogo.  
  
3. Seleccione **Application Server** desde el **Roles** lista y, a continuación, haga clic en **siguiente** dos veces para mostrar el **seleccionar servicios de rol** cuadro de diálogo para el Rol de servidor de aplicaciones.  
  
4. Seleccione el **servidor Web (IIS)** casilla de verificación. Si se le pide que instale características y servicios de rol adicionales, haga clic en **agregar características requeridas**. Haga clic en **siguiente** dos veces para mostrar el **seleccionar servicios de rol** cuadro de diálogo para el rol de servidor Web (IIS).  
  
5. Expanda **las herramientas de administración**y, a continuación, expanda **compatibilidad con la administración de IIS 6**. Seleccione **IIS herramientas de Scripting 6**. Si se le pide que instale características y servicios de rol adicionales, haga clic en **agregar servicios de rol requeridos**. Haga clic en **Siguiente**.  
  
6. Si el resumen de selecciones es correcto, haga clic en **instalar**.  
  
7. Cuando se completa la instalación, haga clic en **cerrar**.  
  
### <a name="to-install-iis-version-75-on-windows-7"></a>Para instalar IIS versión 7.5 en Windows 7  
  
1. Haga clic en **iniciar**y, a continuación, haga clic en **Panel de Control**.  
  
2. Abra el **programas** grupo.  
  
3. En **programas y características**, haga clic en **activar o desactivar las características de Windows**.  
  
4. El **User Account Control** muestra el cuadro de diálogo. Haga clic en **Continuar**.  
  
5. El **características de Windows** muestra el cuadro de diálogo. Expanda el elemento con la etiqueta **Internet Information Services**.  
  
6. Expanda el elemento con la etiqueta **servicios World Wide Web**.  
  
7. Expanda el elemento con la etiqueta **Application Development Features**.  
  
8. Asegúrese de que los siguientes elementos están seleccionados:  
  
    1. **Extensibilidad de .NET**  
  
    2. **ASP.NET**  
  
    3. **Extensiones ISAPI**  
  
    4. **Filtros ISAPI**  
  
9. En el elemento con la etiqueta **servicios World Wide Web**, expanda **características Http comunes**.  
  
10. Asegúrese de que **contenido estático** está seleccionada.  
  
11. En el elemento con la etiqueta **servicios World Wide Web**, expanda **seguridad**.  
  
12. Asegúrese de que **Windows autenticación** está seleccionada.  
  
13. En el **Internet Information Services** directory, expanda el elemento con la etiqueta **herramientas de administración Web**y, a continuación, seleccione **consola de administración IIS**.  
  
14. Expanda el elemento con la etiqueta **compatibilidad con la administración de IIS 6**y, a continuación, seleccione **herramientas de Scripting de IIS 6**.  
  
15. En el **Internet Information Services** directory, expanda el elemento con la etiqueta **Microsoft .NET Framework 3.5.1**y, a continuación, seleccione **activación Http de Windows Communication Foundation**.  
  
16. Haga clic en **Aceptar**.  
  
### <a name="to-install-iis-version-70-on-windows-server-2008"></a>Para instalar la versión de IIS 7.0 en Windows Server 2008  
  
1. Desde **administrador del servidor**, seleccione **Roles**. En **resumen de funciones**, haga clic en **agregar Roles**.  
  
2. Haga clic en **siguiente** para mostrar el **seleccionar Roles de servidor** cuadro de diálogo.  
  
3. Seleccione **Application Server** desde el **Roles** lista y, a continuación, haga clic en **siguiente** dos veces para mostrar el **seleccionar servicios de rol** cuadro de diálogo para el Rol de servidor de aplicaciones.  
  
4. Seleccione **servidor Web (IIS)** casilla de verificación. Si se le pide que instale características y servicios de rol adicionales, haga clic en **agregar características requeridas**. Haga clic en **siguiente** dos veces para mostrar el **seleccionar servicios de rol** cuadro de diálogo para el rol de servidor Web (IIS).  
  
5. Expanda **las herramientas de administración**y, a continuación, expanda **compatibilidad con la administración de IIS 6**. Seleccione **IIS herramientas de Scripting 6**. Si se le pide que instale características y servicios de rol adicionales, haga clic en **agregar servicios de rol requeridos**. Haga clic en **Siguiente**.  
  
6. Si el resumen de selecciones es correcto, haga clic en **instalar**.  
  
7. Cuando se completa la instalación, haga clic en **cerrar**.  
  
### <a name="to-install-iis-version-70-on-windows-vista"></a>Para instalar IIS versión 7.0 en Windows Vista  
  
1. Haga clic en Inicio y, a continuación, en Panel de control.  
  
2. Seleccione el **programas** grupo.  
  
3. En **programas y características**, haga clic en **activar o desactivar las características de Windows**.  
  
4. El **User Account Control** muestra el cuadro de diálogo. Haga clic en **Continuar**.  
  
5. El **características de Windows** muestra el cuadro de diálogo. Expanda el elemento con la etiqueta **Internet Information Services**.  
  
6. Expanda el elemento con la etiqueta **servicios World Wide Web**.  
  
7. Expanda el elemento con la etiqueta **Application Development Features**.  
  
8. Asegúrese de que los siguientes elementos están seleccionados:  
  
    1. **Extensibilidad de .NET**  
  
    2. **ASP.NET**  
  
    3. **Extensiones ISAPI**  
  
    4. **Filtros ISAPI**  
  
9. Expanda el elemento con la etiqueta **herramientas de administración Web**y, a continuación, seleccione **consola de administración IIS**.  
  
10. En el elemento con la etiqueta **servicios World Wide Web**, expanda **características Http comunes**.  
  
11. Asegúrese de que **contenido estático** está seleccionada.  
  
12. En el elemento con la etiqueta **servicios World Wide Web**, expanda **seguridad**.  
  
13. Asegúrese de que **Windows autenticación** está seleccionada.  
  
14. Expanda el elemento con la etiqueta **compatibilidad con la administración de IIS 6**y, a continuación, seleccione **herramientas de Scripting de IIS 6**.  
  
15. Expanda el elemento con la etiqueta **Microsoft .NET Framework 3.0**y, a continuación, seleccione **activación Http de Windows Communication Foundation**.  
  
16. Haga clic en **Aceptar**.  
  
### <a name="to-install-iis-version-60-on-windows-server-2003"></a>Instalar la versión 6.0 de IIS en Windows Server 2003  
  
1. Desde **Administre su servidor**, haga clic en **agregar o quitar una función**y, a continuación, haga clic en **siguiente**.  
  
2. Seleccione **servidor de aplicaciones (IIS, ASP.NET)** desde el **rol de servidor** lista y, a continuación, haga clic en **siguiente**.  
  
3. Seleccione **habilitar ASP.NET** casilla de verificación y, a continuación, haga clic en **siguiente**.  
  
4. Si el resumen de selecciones es correcto, haga clic en Siguiente.  
  
### <a name="to-install-iis-version-51-on-windows-xp-with-service-pack-2-and-service-pack-3-installed"></a>Para instalar la versión 5.1 de IIS en Windows XP con Service Pack 2 y Service Pack 3 instalados  
  
1. En el Panel de Control, haga clic en **agregar o quitar programas**.  
  
2. En el **agregar o quitar programas** cuadro de diálogo, haga clic en **agregar o quitar componentes de Windows**.  
  
3. En el **Asistente para componentes de Windows**, seleccione el **Internet Information Services (IIS)** casilla de verificación y, a continuación, haga clic en **siguiente**.  
  
4. Si el **archivos necesarios** se muestra el cuadro de diálogo, inserte el disco de instalación de sistema operativo, vaya a la carpeta i386 y, a continuación, haga clic en **Aceptar**.  
  
5. Cuando se completa la instalación, haga clic en **finalizar**.  
  
6. Cierre el **agregar o quitar programas** cuadro de diálogo y, a continuación, cierre **Panel de Control**.  
  
### <a name="to-verify-the-installation-of-iis-and-aspnet"></a>Para comprobar la instalación de IIS y ASP.NET  
  
1. Guarde el archivo HTML encontrado al final de este tema en el directorio raíz \InetPub\wwwroot y denomínelo Default.aspx.  
  
2. Abra una ventana del explorador.  
  
3. Tipo `http://localhost/Default.aspx` en el cuadro Dirección y, a continuación, presione ENTRAR.  
  
4. Debe aparecer una página web con el texto "Hello World".  
  
> [!NOTE]
>  Cada vez que instale una nueva versión de .NET Framework, volver a debe registrar aspnet_isapi como una extensión de servicio Web de IIS. Para ello, ejecute el comando `aspnet_regiis –I –enable`.  
  
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
