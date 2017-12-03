---
title: "Ejemplo de integración de SystemWebRouting"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f1c94802-95c4-49e4-b1e2-ee9dd126ff93
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c38c7af4988e6e47ee307f5cd7a8b6733b043a7c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="systemwebrouting-integration-sample"></a>Ejemplo de integración de SystemWebRouting
Este ejemplo muestra la integración de nivel de hospedaje con las clases en el espacio de nombres <xref:System.Web.Routing>. Las clases en el espacio de nombres <xref:System.Web.Routing> permiten a una aplicación utilizar direcciones URL que no se corresponden directamente con un recurso físico. El uso de enrutamiento web permite al desarrollador de software crear direcciones virtuales para HTTO que se asignan a continuación a los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] reales. Esto es útil cuando un servicio WCF se debe hospedar sin requerir un archivo físico ni un recurso, o cuando se debe tener acceso a los servicios con direcciones URL que no contienen archivos como .html o .aspx. En este ejemplo se muestra cómo utilizar la clase <xref:System.Web.Routing.RouteTable> para crear URI virtuales que se asignan a servicios en ejecución definidos en global.asax. En este ejemplo hay dos fuentes RSS creadas con WCF: una fuente `movies` y una fuente `channels`. Las direcciones URL para activar los servicios no contienen una extensión y se registran en el `Application_Start` método de la `Global` clase derivada de la <xref:System.Web.HttpApplication.Application_Start> clase.  
  
> [!NOTE]
>  Las clases en el espacio de nombres <xref:System.Web.Routing> solo funcionan para los servicios hospedados sobre HTTP.  
  
> [!NOTE]
>  Este ejemplo solo funciona en [!INCLUDE[iisver](../../../../includes/iisver-md.md)], porque [!INCLUDE[iis60](../../../../includes/iis60-md.md)] usa un método diferente para admitir las direcciones URL sin extensión.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebRoutingIntegration`  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Abra el archivo WebRoutingIntegration.sln con [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Para ejecutar la solución e iniciar el servidor de desarrollo web, presione F5.  
  
     Aparece una lista de directorios para el ejemplo. Observe que no hay ningún archivo con la extensión de archivo .svc.  
  
3.  En la barra de direcciones, agregue `movies` a la dirección URL, de modo que se lea http://localhost:[puerto]/movies y presione ENTRAR.  
  
     Las fuentes de películas aparecen en el explorador.  
  
4.  En la barra de direcciones, agregue `channels` a la dirección URL, de modo que se lea http://localhost:[puerto]/channels y presione ENTRAR.  
  
     La fuente de canales aparece en el explorador.  
  
5.  Presione ALT+F4 para cerrar el explorador web.  
  
     Si no se ha salido del servidor de desarrollo, haga clic en el icono del área de notificación y seleccione **detener**.  
  
#### <a name="to-use-this-sample-when-hosted-in-iis"></a>Para utilizar este ejemplo cuando se hospeda en IIS  
  
1.  Abra el archivo WebRoutingIntegration.sln con [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Compile el proyecto presionando CTRL+MAYÚS+B.  
  
3.  Cree una aplicación web en el Administrador de Internet Information Services (IIS).  
  
    1.  En el Administrador de IIS, haga clic con el **sitio Web predeterminado** y seleccione **agregar una aplicación**.  
  
    2.  Para el **alias**, escriba `WebRoutingIntegration`.  
  
    3.  Para el **ruta de acceso física**, seleccione la carpeta servicio dentro del proyecto.  
  
    4.  Press **OK**.  
  
4.  Iniciar la aplicación, haciendo clic en la aplicación Web y seleccione **administrar la aplicación** y, a continuación, **examinar**.  
  
5.  En la barra de direcciones, agregue `movies` a la dirección URL, de modo que se lea http://localhost:[puerto]/movies y presione ENTRAR.  
  
     Las fuentes de películas aparecen en el explorador.  
  
6.  En la barra de direcciones, agregue `channels` a la dirección URL, de modo que se lea http://localhost:[puerto]/channels y presione ENTRAR.  
  
     La fuente de canales aparece en el explorador.  
  
7.  Presione ALT+F4 para cerrar el explorador web.  
  
 En este ejemplo se muestra que el nivel de hospedaje es capaz de crear las clases en el espacio de nombres <xref:System.Web.Routing> para enrutar las solicitudes de servicios hospedados a través de HTTP.  
  
> [!NOTE]
>  Actualice la versión del grupo de aplicaciones predeterminado a [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] si está establecido en la versión 2.  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de persistencia y el hospedaje de AppFabric](http://go.microsoft.com/fwlink/?LinkId=193961)
