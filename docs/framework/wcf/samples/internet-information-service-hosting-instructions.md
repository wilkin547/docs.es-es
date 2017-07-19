---
title: "Instrucciones de hospedaje Internet Information Services | Microsoft Docs"
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
ms.assetid: 959a21c8-9d9d-4757-b255-4e57793ae9d6
caps.latest.revision: 30
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 30
---
# Instrucciones de hospedaje Internet Information Services
Para ejecutar los ejemplos que son hospedados por Internet Information Services \(IIS\), debe asegurarse de que IIS está instalado correctamente y se está ejecutando.  
  
### Para instalar la versión 7.5 de IIS en Windows Server 2008 R2  
  
1.  En **Administrador del servidor**, seleccione **Roles**. En **Resumen de roles**, haga clic en **Agregar roles**.  
  
2.  Haga clic en **Siguiente** para mostrar el cuadro de diálogo **Seleccionar roles de servidor**.  
  
3.  Seleccione **Servidor de aplicación** en la lista **Roles** y, a continuación, haga clic en **Siguiente** dos veces para mostrar el cuadro de diálogo **Seleccionar servicios de roles** para el rol Servidor de aplicación.  
  
4.  Seleccione la casilla **Servidor web \(IIS\)**.  Si se le pide que instale características y servicios de rol adicionales, haga clic en **Agregar características requeridas**.  Haga clic en **Siguiente** dos veces para mostrar el cuadro de diálogo **Seleccionar servicios de rol** para el rol de servidor web \(IIS\).  
  
5.  Expanda **Herramientas de administración** y **Compatibilidad con la administración de IIS 6**.  Seleccione **Herramientas de scripting de IIS 6**.  Si se le pide que instale características y servicios de rol adicionales, haga clic en **Agregar servicios de rol requeridos**.  Haga clic en **Siguiente**.  
  
6.  Si el resumen de selecciones es correcto, haga clic en **Instalar**.  
  
7.  Cuando la instalación esté completa, haga clic en **Cerrar**.  
  
### Para instalar IIS versión 7.5 en Windows 7  
  
1.  Haga clic en **Inicio** y, a continuación, en **Panel de control**.  
  
2.  Abra el grupo **Programas**.  
  
3.  En **Programas y características**, haga clic en **Activar o desactivar las características de Windows**.  
  
4.  Se muestra el cuadro de diálogo **Control de cuentas de usuario**.  Haga clic en **Continuar**.  
  
5.  Se muestra el cuadro de diálogo **Características de Windows**.  Expanda el elemento con la etiqueta **Internet Information Services**.  
  
6.  Expanda el elemento con la etiqueta **Servicios World Wide Web**.  
  
7.  Expanda el elemento con la etiqueta **Características de desarrollo de aplicaciones**.  
  
8.  Asegúrese de que los siguientes elementos están seleccionados:  
  
    1.  **Extensibilidad de .NET**  
  
    2.  **ASP.NET**  
  
    3.  **Extensiones ISAPI**  
  
    4.  **filtros ISAPI**  
  
9. En el elemento con la etiqueta **Servicios de World Wide Web**, expanda **Características HTTP comunes**.  
  
10. Asegúrese de que **Contenido Estático** está seleccionado.  
  
11. En el elemento con la etiqueta **Servicios World Wide Web**, expanda **Seguridad**.  
  
12. Asegúrese de que la opción **Autenticación de Windows** está seleccionada.  
  
13. En el directorio **Internet Information Services**, expanda el elemento con la etiqueta **Herramientas de administración web** y, a continuación, seleccione **Consola de administración de IIS**.  
  
14. Expanda el elemento con la etiqueta **Compatibilidad con la administración de IIS 6** y seleccione **Herramientas de scripting de IIS 6**.  
  
15. En el directorio **Internet Information Services**, expanda el elemento con la etiqueta **Microsoft .NET Framework 3.5.1** y, a continuación, seleccione **Activación HTTP de Windows Communication Foundation**.  
  
16. Haga clic en **Aceptar**.  
  
### Para instalar la versión de IIS 7.0 en Windows Server 2008  
  
1.  En **Administrador del servidor**, seleccione **Roles**.  En **Resumen de roles**, haga clic en **Agregar roles**.  
  
2.  Haga clic en **Siguiente** para mostrar el cuadro de diálogo **Seleccionar roles de servidor**.  
  
3.  Seleccione **Servidor de aplicación** en la lista **Roles** y, a continuación, haga clic en **Siguiente** dos veces para mostrar el cuadro de diálogo **Seleccionar servicios de roles** para el rol Servidor de aplicación.  
  
4.  Active la casilla **Servidor web \(IIS\)**.  Si se le pide que instale características y servicios de rol adicionales, haga clic en **Agregar características requeridas**.  Haga clic en **Siguiente** dos veces para mostrar el cuadro de diálogo **Seleccionar servicios de rol** para el rol de servidor web \(IIS\).  
  
5.  Expanda **Herramientas de administración** y **Compatibilidad con la administración de IIS 6**.  Seleccione **Herramientas de scripting de IIS 6**.  Si se le pide que instale características y servicios de rol adicionales, haga clic en **Agregar servicios de rol requeridos**.  Haga clic en **Siguiente**.  
  
6.  Si el resumen de selecciones es correcto, haga clic en **Instalar**.  
  
7.  Cuando la instalación esté completa, haga clic en **Cerrar**.  
  
### Para instalar IIS versión 7.0 en Windows Vista  
  
1.  Haga clic en Inicio y, a continuación, en Panel de control.  
  
2.  Seleccione el grupo **Programas**.  
  
3.  En **Programas y características**, haga clic en **Activar o desactivar las características de Windows**.  
  
4.  Se muestra el cuadro de diálogo **Control de cuentas de usuario**.  Haga clic en **Continuar**.  
  
5.  Se muestra el cuadro de diálogo **Características de Windows**.  Expanda el elemento con la etiqueta **Internet Information Services**.  
  
6.  Expanda el elemento con la etiqueta **Servicios World Wide Web**.  
  
7.  Expanda el elemento con la etiqueta **Características de desarrollo de aplicaciones**.  
  
8.  Asegúrese de que los siguientes elementos están seleccionados:  
  
    1.  **Extensibilidad de .NET**  
  
    2.  **ASP.NET**  
  
    3.  **Extensiones ISAPI**  
  
    4.  **filtros ISAPI**  
  
9. Expanda el elemento con la etiqueta **Herramientas de Administración Web** y, después, seleccione **Consola de Administración IIS**.  
  
10. En el elemento con la etiqueta **Servicios de World Wide Web**, expanda **Características HTTP comunes**.  
  
11. Asegúrese de que **Contenido Estático** está seleccionado.  
  
12. En el elemento con la etiqueta **Servicios World Wide Web**, expanda **Seguridad**.  
  
13. Asegúrese de que la opción **Autenticación de Windows** está seleccionada.  
  
14. Expanda el elemento con la etiqueta **Compatibilidad con la administración de IIS 6** y seleccione **Herramientas de scripting de IIS 6**.  
  
15. Expanda el elemento con la etiqueta **Microsoft .NET Framework 3.0** y seleccione **Activación HTTP de Windows Communication Foundation**.  
  
16. Haga clic en **Aceptar**.  
  
### Instalar la versión 6.0 de IIS en Windows Server 2003  
  
1.  En **Administrar el servidor**, haga clic en **Agregar o quitar un rol** y, a continuación, haga clic en**Siguiente**.  
  
2.  Seleccione **Servidor de aplicación \(IIS, ASP.NET\)** en la lista **Rol del servidor** y, a continuación, haga clic en **Siguiente**.  
  
3.  Seleccione la casilla **Habilitar ASP.NET** y haga clic en **Siguiente**.  
  
4.  Si el resumen de selecciones es correcto, haga clic en Siguiente.  
  
### Para instalar la versión 5.1 de IIS en Windows XP con Service Pack 2 y Service Pack 3 instalados  
  
1.  En el Panel de control, haga clic en **Agregar o quitar programas**.  
  
2.  En el cuadro de diálogo **Agregar o quitar programas**, haga clic en **Agregar o quitar componentes de Windows**.  
  
3.  En el **Asistente para componentes de Windows**, active la casilla **Internet Information Services \(IIS\)** y a continuación haga clic en **Siguiente**.  
  
4.  Si se muestra el cuadro de diálogo **Archivos necesarios**, inserte su disco de instalación del sistema operativo, vaya a la carpeta i386 y, a continuación, haga clic en **Aceptar**.  
  
5.  Cuando la instalación esté completa, haga clic en **Finalizar**.  
  
6.  Cierre el cuadro de diálogo **Agregar o quitar programas** y, a continuación, cierre **Panel de control**.  
  
### Para comprobar la instalación de IIS y ASP.NET  
  
1.  Guarde el archivo HTML encontrado al final de este tema en el directorio raíz \\InetPub\\wwwroot y denomínelo Default.aspx.  
  
2.  Abra una ventana del explorador.  
  
3.  Escriba `http://localhost/Default.aspx` en el cuadro de dirección y presione ENTRAR.  
  
4.  Debe aparecer una página web con el texto "Hello World".  
  
> [!NOTE]
>  Cada vez que instale una nueva versión de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], debe volver a registrar aspnet\_isapi como una extensión de servicio Web para IIS.  Para ello, ejecute el comando `aspnet_regiis –I –enable`.  
  
## Código de ejemplo  
  
```  
<html>  
   <body>  
       <form >  
           <h3> Hello World  
           </h3>  
       </form>  
   </body>  
</html>  
```