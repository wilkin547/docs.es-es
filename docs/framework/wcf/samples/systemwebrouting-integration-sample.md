---
title: "Ejemplo de integraci&#243;n de SystemWebRouting | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f1c94802-95c4-49e4-b1e2-ee9dd126ff93
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Ejemplo de integraci&#243;n de SystemWebRouting
Este ejemplo muestra la integración de nivel de hospedaje con las clases en el espacio de nombres <xref:System.Web.Routing>.  Las clases en el espacio de nombres <xref:System.Web.Routing> permiten a una aplicación utilizar direcciones URL que no se corresponden directamente con un recurso físico.  El uso de enrutamiento web permite al desarrollador de software crear direcciones virtuales para HTTO que se asignan a continuación a los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] reales.  Esto es útil cuando un servicio WCF se debe hospedar sin requerir un archivo físico ni un recurso, o cuando se debe tener acceso a los servicios con direcciones URL que no contienen archivos como .html o .aspx.  En este ejemplo se muestra cómo utilizar la clase <xref:System.Web.Routing.RouteTable> para crear URI virtuales que se asignan a servicios en ejecución definidos en global.asax.  En este ejemplo hay dos fuentes RSS creadas con WCF: una fuente `movies` y una fuente `channels`.  Las direcciones URL para activar los servicios no contienen una extensión de archivo y se registran en el método <xref:System.Web.HttpApplication.Application_Start%2A>.  
  
> [!NOTE]
>  Las clases en el espacio de nombres <xref:System.Web.Routing> solo funcionan para los servicios hospedados sobre HTTP.  
  
> [!NOTE]
>  Este ejemplo solo funciona en [!INCLUDE[iisver](../../../../includes/iisver-md.md)], porque [!INCLUDE[iis60](../../../../includes/iis60-md.md)] usa un método diferente para admitir las direcciones URL sin extensión.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.  Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].  Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebRoutingIntegration`  
  
#### Para utilizar este ejemplo  
  
1.  Abra el archivo WebRoutingIntegration.sln con [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Para ejecutar la solución e iniciar el servidor de desarrollo web, presione F5.  
  
     Aparece una lista de directorios para el ejemplo.  Observe que no hay ningún archivo con la extensión de archivo .svc.  
  
3.  En la barra de direcciones, agregue `movies` a la dirección URL, de modo que se lea http:\/\/localhost:\[puerto\]\/movies y presione ENTRAR.  
  
     Las fuentes de películas aparecen en el explorador.  
  
4.  En la barra de direcciones, agregue `channels` a la dirección URL, de modo que se lea http:\/\/localhost:\[puerto\]\/channels y presione ENTRAR.  
  
     La fuente de canales aparece en el explorador.  
  
5.  Presione ALT\+F4 para cerrar el explorador web.  
  
     Si el servidor de desarrollo no se ha cerrado, haga clic con el botón secundario en el icono del área de notificación y seleccione **Detener**.  
  
#### Para utilizar este ejemplo cuando se hospeda en IIS  
  
1.  Abra el archivo WebRoutingIntegration.sln con [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Compile el proyecto presionando CTRL\+MAYÚS\+B.  
  
3.  Cree una aplicación web en el Administrador de Internet Information Services \(IIS\).  
  
    1.  En el Administrador de IIS, haga clic con el botón secundario en **Sitio web predeterminado** y seleccione **Agregar una aplicación**.  
  
    2.  Como **alias**, escriba `WebRoutingIntegration`.  
  
    3.  Como **Ruta de acceso física**, seleccione la carpeta Servicio dentro del proyecto.  
  
    4.  Presione **Aceptar**.  
  
4.  Inicie la aplicación, haciendo clic con el botón secundario en la aplicación web y seleccionando **Administrar aplicación** y, a continuación, **Examinar**.  
  
5.  En la barra de direcciones, agregue `movies` a la dirección URL, de modo que se lea http:\/\/localhost:\[puerto\]\/movies y presione ENTRAR.  
  
     Las fuentes de películas aparecen en el explorador.  
  
6.  En la barra de direcciones, agregue `channels` a la dirección URL, de modo que se lea http:\/\/localhost:\[puerto\]\/channels y presione ENTRAR.  
  
     La fuente de canales aparece en el explorador.  
  
7.  Presione ALT\+F4 para cerrar el explorador web.  
  
 En este ejemplo se muestra que el nivel de hospedaje es capaz de crear las clases en el espacio de nombres <xref:System.Web.Routing> para enrutar las solicitudes de servicios hospedados a través de HTTP.  
  
> [!NOTE]
>  Actualice la versión del grupo de aplicaciones predeterminado a [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] si está establecido en la versión 2.  
  
## Vea también  
 [Ejemplos de Hospedaje y persistencia de AppFabric](http://go.microsoft.com/fwlink/?LinkId=193961)