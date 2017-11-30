---
title: Servicios WCF y ASP.NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b980496a-f0b0-4319-8e55-a0f0fa32da70
caps.latest.revision: "24"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c86ab6996b85e679fc5c15d85e86d25eaa8b1844
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="wcf-services-and-aspnet"></a>Servicios WCF y ASP.NET
En este tema se tratan los servicios de hospedaje de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] en paralelo con ASP.NET y el hospedaje de ellos en el modo de compatibilidad de ASP.NET.  
  
## <a name="hosting-wcf-side-by-side-with-aspnet"></a>Hospedaje de WCF en paralelo con ASP.NET  
 Los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hospedados en Internet Information Services (IIS) se pueden encontrar con páginas .ASPX y servicios Web ASMX dentro de un dominio de aplicación común e individual. ASP.NET proporciona servicios de infraestructura común como administración de AppDomain y compilación dinámica en tiempo de ejecución de HTTP de ASP.NET e [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. La configuración predeterminada para [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] es en paralelo con ASP.NET.  
  
 ![Servicios WCF y ASP. NET: estado compartido](../../../../docs/framework/wcf/feature-details/media/hostingwcfwithaspnet.gif "HostingWCFwithASPNET")  
  
 El tiempo de ejecución de HTTP de ASP.NET controla las solicitudes de ASP.NET, pero no participa en el procesamiento de solicitudes destinadas a servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], aunque estos servicios se hospeden en el mismo AppDomain que el contenido de ASP.NET. En su lugar, el modelo de servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] intercepta los mensajes direccionados a los servicios [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y los enruta a través de la pila de transporte/canal de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 Los resultados del modelo en paralelo son de la siguiente manera:  
  
-   Los servicios de ASP.NET e [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] pueden compartir el estado del AppDomain. Dado que los dos marcos pueden coexistir en el mismo AppDomain, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] también pueden compartir el estado del AppDomain con ASP.NET (incluidas las variables estáticas, los eventos, etc.).  
  
-   Los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se comportan de forma coherente, independientemente del entorno de hospedaje y del transporte. El tiempo de ejecución de HTTP de ASP.NET se acopla de manera intencionada al entorno de hospedaje de IIS/ASP.NET y a la comunicación HTTP. De manera inversa, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] está diseñado para comportarse de forma consistente en diferentes entornos de hospedaje ([!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se comporta de forma consistente dentro y fuera de IIS) y transportes (un servicio hospedado en IIS 7.0 y posterior tiene un comportamiento coherente en todos los extremos que expone, incluso aunque algunos de esos extremos usen protocolos distintos de HTTP).  
  
-   Dentro de un AppDomain, las características implementadas por el tiempo de ejecución de HTTP se aplican al contenido de ASP.NET pero no a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Muchas características específicas de HTTP de la plataforma de aplicaciones de ASP.NET no se aplican a los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hospedados dentro de un AppDomain que incluya contenido de ASP.NET. Ejemplos de estas características incluyen lo siguiente:  
  
    -   HttpContext: el valor de propiedad <xref:System.Web.HttpContext.Current%2A> siempre es `null` cuando se obtiene acceso a ella desde un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Use <!--zz <xref:System.ServiceModel.OperationContext.Current.RequestContext>--> `RequestContext` en su lugar.  
  
    -   Autorización basada en archivos: el modelo de seguridad de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no permite la lista de control de acceso (ACL) aplicada al archivo .svc del servicio a la hora de decidir si se autoriza una solicitud de servicio.  
  
    -   Autorización de dirección URL basada en configuración: de forma similar, el [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] modelo de seguridad no se adhiere a las reglas de autorización basada en URL especificadas en System.Web \<autorización > elemento de configuración. Estos valores se pasan por alto para solicitudes de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] si un servicio reside en un espacio de direcciones URL protegido por reglas de autorización de URL de ASP.NET.  
  
    -   Extensibilidad de HttpModule: la infraestructura de hospedaje de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] intercepta las solicitudes de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] cuando se genera el evento <xref:System.Web.HttpApplication.PostAuthenticateRequest> y no devuelve el procesamiento a la canalización HTTP de ASP.NET. Los módulos que están codificados para interceptar las solicitudes en fases posteriores de la canalización no interceptan las solicitudes de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
    -   Suplantación de ASP.NET: de forma predeterminada, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] solicita siempre se ejecuta como el proceso IIS identidad, aun cuando ASP.NET se configura para permitir la suplantación mediante System.Web \<identity impersonate = "true" / > opción de configuración.  
  
 Estas restricciones solo se aplican a los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hospedados en la aplicación de IIS. La presencia de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]no afecta al comportamiento del contenido de ASP.NET.  
  
 Las aplicaciones de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que requieren la funcionalidad que proporciona tradicionalmente la canalización HTTP deberían considerar la posibilidad de usar equivalentes de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], que no dependen del host ni del transporte:  
  
-   <xref:System.ServiceModel.OperationContext> en lugar de <xref:System.Web.HttpContext>.  
  
-   <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> en lugar de la autorización de archivo/URL de ASP.NET.  
  
-   <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector> o los canales dispuestos en capas personalizados en lugar de los módulos HTTP.  
  
-   Suplantación para cada operación utilizando [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] en lugar de la suplantación de System.Web.  
  
 De manera alternativa, puede considerar ejecutar sus servicios en el modo de compatibilidad ASP.NET de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## <a name="hosting-wcf-services-in-aspnet-compatibility-mode"></a>Hospedaje de servicios de WCF en el modo de compatibilidad de ASP.NET  
 Aunque el modelo de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] está diseñado para comportarse de forma coherente en los diferentes entornos de hospedaje y transportes, a menudo hay escenarios en los que una aplicación no requiere este grado de flexibilidad. El modo de compatibilidad de ASP.NET de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] es conveniente para escenarios que no requieren la capacidad de hospedar fuera de IIS ni de comunicarse sobre protocolos que no sean HTTP, pero que usan todas las características de la plataforma de aplicaciones web ASP.NET.  
  
 A diferencia de la configuración en paralelo predeterminada, donde la infraestructura de hospedaje de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] intercepta los mensajes de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y los enruta fuera de la canalización HTTP, los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que se ejecutan en modo de compatibilidad de ASP.NET participan totalmente en el ciclo de vida de la solicitud HTTP de ASP.NET. En el modo de compatibilidad, los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utilizan la canalización HTTP a través de una implementación <xref:System.Web.IHttpHandler>, de manera similar a la forma en que se tratan las solicitudes de páginas ASPX y servicios Web ASMX. Como resultado, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se comporta de manera idéntica a ASMX con respecto a las siguientes características de ASP.NET:  
  
-   <xref:System.Web.HttpContext>: los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que se ejecutan en modo de compatibilidad de ASP.NET pueden tener acceso a <xref:System.Web.HttpContext.Current%2A> y a su estado asociado.  
  
-   Autorización basada en archivo: los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que se ejecutan en modo de compatibilidad de ASP.NET pueden ser seguros si se asocian las listas de control de acceso (ACL) del sistema de archivos al archivo .svc del servicio.  
  
-   Autorización de URL configurable: las reglas de autorización de URL de ASP.NET se aplican para las solicitudes de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] cuando el servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se está ejecutando en modo de compatibilidad de ASP.NET.  
  
-   Extensibilidad de<xref:System.Web.HttpModuleCollection>: dado que los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que se ejecutan en modo de compatibilidad de ASP.NET participan totalmente en el ciclo de vida de la solicitud HTTP de ASP.NET, cualquier módulo HTTP configurado en la canalización HTTP puede funcionar en solicitudes de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] antes de y después de la invocación del servicio.  
  
-   Suplantación de ASP.NET: los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se ejecutan utilizando la identidad actual del subproceso ASP.NET suplantado, que puede diferir de la identidad de proceso de IIS si se ha habilitado la suplantación de ASP.NET de la aplicación. Si se habilitan la suplantación de ASP.NET y la de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para una operación de servicio determinada, la implementación del servicio se ejecuta finalmente utilizando la identidad obtenida de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 El modo de compatibilidad de ASP.NET de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se habilita en el nivel de la aplicación a través de la siguiente configuración (ubicada en el archivo Web.config de la aplicación):  
  
```xml  
<system.serviceModel>  
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true" />  
</system.serviceModel>  
```  
  
 El valor predeterminado es "`true`" Si no se especifica. Establecer este valor en "`false`" indica que todos los [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] servicios que se ejecutan en la aplicación no se ejecutarán en modo de compatibilidad de ASP.NET.  
  
 Dado que el modo de compatibilidad de ASP.NET implica una semántica de procesamiento de solicitudes diferente de la predeterminada de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], las implementaciones de servicios individuales tienen la capacidad de controlar si se ejecutan dentro de una aplicación para la que se ha habilitado el modo de compatibilidad de ASP.NET. Los servicios pueden utilizar el <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> para indicar si admiten el modo de compatibilidad de ASP.NET. El valor predeterminado para este atributo es <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed>.  
  
 `[AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]`  
  
 `public class CalculatorService : ICalculatorSession`  
  
 `{//Implement calculator service methods.}`  
  
 La siguiente tabla muestra cómo el valor del modo de compatibilidad de toda la aplicación interactúa con el nivel expresado de compatibilidad del servicio individual:  
  
|Valor de modo de compatibilidad de la aplicación|[AspNetCompatibilityRequirementsMode]<br /><br /> Parámetro|Resultado observado|  
|--------------------------------------------------|---------------------------------------------------------|---------------------|  
|aspNetCompatibilityEnabled = "`true`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required>|El servicio se activa correctamente.|  
|aspNetCompatibilityEnabled = "`true`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed>|El servicio se activa correctamente.|  
|aspNetCompatibilityEnabled = "`true`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.NotAllowed>|Se produce un error de activación cuando el servicio recibe un mensaje.|  
|aspNetCompatibilityEnabled = "`false`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required>|Se produce un error de activación cuando el servicio recibe un mensaje.|  
|aspNetCompatibilityEnabled = "`false`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed>|El servicio se activa correctamente.|  
|aspNetCompatibilityEnabled = "`false`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.NotAllowed>|El servicio se activa correctamente.|  
  
> [!NOTE]
>  IIS 7.0 y WAS permite a los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] comunicarse a través de protocolos que no sean HTTP. Sin embargo, no se permite a los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que se ejecutan en aplicaciones que han habilitado el modo de compatibilidad de ASP.NET exponer extremos que no sean HTTP. Este tipo de configuración genera una excepción de activación cuando el servicio recibe su primer mensaje.  
  
 Para obtener más información acerca de cómo habilitar el modo de compatibilidad ASP.NET para [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] servicios, vea <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode> y [compatibilidad de ASP.NET](../../../../docs/framework/wcf/samples/aspnet-compatibility.md) ejemplo.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute>  
 [Características de hospedaje de Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201276)
