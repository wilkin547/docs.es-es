---
title: Ejemplo de integración de SystemWebRouting
ms.date: 03/30/2017
ms.assetid: f1c94802-95c4-49e4-b1e2-ee9dd126ff93
ms.openlocfilehash: 244a7b7b73217086864b16945bc1521a3383aeac
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59147815"
---
# <a name="systemwebrouting-integration-sample"></a>Ejemplo de integración de SystemWebRouting
Este ejemplo muestra la integración de nivel de hospedaje con las clases en el espacio de nombres <xref:System.Web.Routing>. Las clases en el espacio de nombres <xref:System.Web.Routing> permiten a una aplicación utilizar direcciones URL que no se corresponden directamente con un recurso físico. Uso de enrutamiento Web permite al desarrollador crear direcciones virtuales para HTTO que, a continuación, se asignan a los servicios WCF reales. Esto es útil cuando un servicio WCF se debe hospedar sin requerir un archivo físico ni un recurso, o cuando se debe tener acceso a los servicios con direcciones URL que no contienen archivos como .html o .aspx. En este ejemplo se muestra cómo utilizar la clase <xref:System.Web.Routing.RouteTable> para crear URI virtuales que se asignan a servicios en ejecución definidos en global.asax. 

> [!NOTE]
>  Las clases en el espacio de nombres <xref:System.Web.Routing> solo funcionan para los servicios hospedados sobre HTTP.  
  
En este ejemplo usa WCF para crear dos fuentes RSS: un `movies` fuente y un `channels` fuentes de distribución. Las direcciones URL para activar los servicios no contienen una extensión y se registran en el `Application_Start` método de la `Global` clase derivada de la <xref:System.Web.HttpApplication> clase.  
  
> [!NOTE]
>  Este ejemplo solo funciona en Internet Information Services (IIS) 7.0 y versiones posteriores, como IIS 6.0 usa un método diferente para la compatibilidad con direcciones URL sin extensión.  

#### <a name="to-download-this-sample"></a>Para descargar este ejemplo
  
En este ejemplo ya puede instalarse en el equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
   
`<InstallDrive>:\WF_WCF_Samples`  
   
 Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
   
`<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebRoutingIntegration`  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Con Visual Studio, abra el archivo WebRoutingIntegration.sln.  
  
2.  Para ejecutar la solución e iniciar el servidor de desarrollo web, presione F5.  
  
     Aparece una lista de directorios para el ejemplo. Observe que no hay ningún archivo con la extensión de archivo .svc.  
  
3.  En la barra de direcciones, agregue `movies` a la dirección URL, así que indique `http://localhost:[port]/movies` y presione ENTRAR.  
  
     Las fuentes de películas aparecen en el explorador.  
  
4.  En la barra de direcciones, agregue `channels` a la dirección URL, por lo que eso es lecturas `http://localhost:[port]/channels` y presione ENTRAR.  
  
     La fuente de canales aparece en el explorador.  
  
5.  Presione ALT+F4 para cerrar el explorador web.  
  
     Si no se ha cerrado el servidor de desarrollo, haga clic en el icono del área de notificación y seleccione **detener**.  
  
#### <a name="to-use-this-sample-when-hosted-in-iis"></a>Para utilizar este ejemplo cuando se hospeda en IIS  
  
1.  Con Visual Studio, abra el archivo WebRoutingIntegration.sln.  
  
2.  Compile el proyecto presionando CTRL+MAYÚS+B.  
  
3.  Cree una aplicación web en el Administrador de Internet Information Services (IIS).  
  
    1.  Haga clic en el Administrador de IIS, el **sitio Web predeterminado** y seleccione **agregar una aplicación**.  
  
    2.  Para el **alias**, escriba `WebRoutingIntegration`.  
  
    3.  Para el **ruta de acceso física**, seleccione la carpeta servicio dentro del proyecto.  
  
    4.  Haga clic en **Aceptar**.  
  
4.  Iniciar la aplicación, haciendo clic en la aplicación Web y seleccione **administrar aplicación** y, a continuación, **examinar**.  
  
5.  En la barra de direcciones, agregue `movies` a la dirección URL, por lo que eso es lecturas `http://localhost:[port]/movies` y presione ENTRAR.  
  
     Las fuentes de películas aparecen en el explorador.  
  
6.  En la barra de direcciones, agregue `channels` a la dirección URL, por lo que eso es lecturas `http://localhost:[port]/channels` y presione ENTRAR.  
  
     La fuente de canales aparece en el explorador.  
  
7.  Presione ALT+F4 para cerrar el explorador web.  
  
 En este ejemplo se muestra que el nivel de hospedaje es capaz de crear las clases en el espacio de nombres <xref:System.Web.Routing> para enrutar las solicitudes de servicios hospedados a través de HTTP.  
  
> [!NOTE]
>  Debe actualizar la versión del grupo de aplicaciones predeterminado a [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] si se establece a la versión 2.  
  
## <a name="see-also"></a>Vea también

- [Ejemplos de hospedaje y persistencia de AppFabric](https://go.microsoft.com/fwlink/?LinkId=193961)
