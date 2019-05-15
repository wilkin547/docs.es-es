---
title: Servicios WCF y ASP.NET
ms.date: 03/30/2017
ms.assetid: b980496a-f0b0-4319-8e55-a0f0fa32da70
ms.openlocfilehash: ef772a360ea53c2b5f177ed88ad14c4a1e1277ef
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65637550"
---
# <a name="wcf-services-and-aspnet"></a>Servicios WCF y ASP.NET

En este tema se describe hospedaje Windows Communication Foundation (WCF) servicios side-by-side con ASP.NET y hospedarlas en modo de compatibilidad ASP.NET.

## <a name="hosting-wcf-side-by-side-with-aspnet"></a>Hospedaje de WCF en paralelo con ASP.NET

Servicios WCF hospedados en Internet Information Services (IIS) pueden encontrarse con. Las páginas ASPX y servicios Web ASMX dentro de un dominio de aplicación único y común. ASP.NET proporciona servicios de infraestructura común como administración de AppDomain y compilación dinámica para WCF y el tiempo de ejecución HTTP de ASP.NET. La configuración predeterminada de WCF es en paralelo con ASP.NET.

![Captura de pantalla muestra los servicios WCF y ASP.NET: uso compartido del estado.](./media/wcf-services-and-aspnet/windows-communication-foundation-services-asp-dotnet-configuration.gif)

El tiempo de ejecución HTTP de ASP.NET controla las solicitudes ASP.NET, pero no participa en el procesamiento de solicitudes destinadas a los servicios WCF, aunque estos servicios se hospedan en el mismo AppDomain, como es el contenido ASP.NET. En su lugar, el modelo de servicio WCF intercepta los mensajes dirigidos a los servicios de WCF y los enruta a través de la pila de transporte/canal WCF.

Los resultados del modelo en paralelo son de la siguiente manera:

- Servicios ASP.NET y WCF pueden compartir el estado del AppDomain. Dado que los dos marcos pueden coexistir en el mismo AppDomain, WCF también puede compartir el estado del AppDomain con ASP.NET (incluidas las variables estáticas, eventos y así sucesivamente).

- Servicios WCF comportan de forma coherente, independientemente del transporte y el entorno de hospedaje. El tiempo de ejecución de HTTP de ASP.NET se acopla de manera intencionada al entorno de hospedaje de IIS/ASP.NET y a la comunicación HTTP. Por el contrario, WCF está diseñado para comportarse de forma coherente entre entornos de hospedaje (WCF comporta de forma coherente tanto dentro como fuera de IIS) y transportes (un servicio hospedado en IIS 7.0 y posterior tiene un comportamiento coherente en todos los extremos que expone, incluso si algunos de esos extremos usan protocolos distintos de HTTP).

- Dentro de un AppDomain, implementadas por el tiempo de ejecución HTTP de características se aplican al contenido de ASP.NET, pero no a WCF. Muchas características específicas de HTTP de la plataforma de aplicaciones de ASP.NET no se aplican a los servicios WCF hospedados dentro de un AppDomain que incluya contenido de ASP.NET. Ejemplos de estas características incluyen lo siguiente:

    - HttpContext: <xref:System.Web.HttpContext.Current%2A> siempre `null` al acceder desde dentro de un servicio WCF. Utilice <xref:System.ServiceModel.Channels.RequestContext> en su lugar.

    - Autorización basada en archivo: El modelo de seguridad WCF no permite la lista de control de acceso (ACL) que se aplica al archivo .svc del servicio de hora de decidir si se autoriza una solicitud de servicio.

    - Autorización de URL basada en la configuración: De forma similar, el modelo de seguridad WCF no se adhiere a ninguna regla de autorización basada en la dirección URL especificada en de System.Web \<autorización > elemento de configuración. Estos valores se omiten para las solicitudes WCF si un servicio reside en un espacio de direcciones URL protegido por ASP. Reglas de autorización de dirección URL de la red.

    - Extensibilidad de HttpModule: La infraestructura de hospedaje de WCF intercepta WCF solicita cuando el <xref:System.Web.HttpApplication.PostAuthenticateRequest> se provoca el evento y no devuelve el procesamiento a la canalización HTTP de ASP.NET. Los módulos que están codificados para interceptar las solicitudes en las fases posteriores de la canalización no interceptan las solicitudes WCF.

    - Suplantación de ASP.NET: De forma predeterminada, WCF solicita siempre se ejecuta como IIS identidad de proceso, aun cuando ASP.NET se configura para permitir la suplantación mediante de System.Web \<identity impersonate = "true" / > opción de configuración.

Estas restricciones se aplican sólo a los servicios WCF hospedados en la aplicación de IIS. El comportamiento del contenido de ASP.NET no se ve afectado por la presencia de WCF.

Las aplicaciones WCF que requieren la funcionalidad que proporciona tradicionalmente la canalización HTTP deben considerar el uso de los equivalentes de WCF, que son host ni del transportan:

- <xref:System.ServiceModel.OperationContext> en lugar de <xref:System.Web.HttpContext>.

- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> en lugar de la autorización de archivo/URL de ASP.NET.

- <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector> o los canales dispuestos en capas personalizados en lugar de los módulos HTTP.

- Suplantación para cada operación con WCF en lugar de suplantación de System.Web.

Como alternativa, puede considerar ejecutar sus servicios en modo de compatibilidad ASP.NET de WCF.

## <a name="hosting-wcf-services-in-aspnet-compatibility-mode"></a>Hospedaje de servicios WCF en modo de compatibilidad ASP.NET

Aunque el modelo de WCF está diseñado para comportarse de forma coherente entre entornos de hospedaje y transportes, a menudo hay escenarios donde una aplicación no requiere este grado de flexibilidad. Modo de compatibilidad ASP.NET de WCF es adecuado para escenarios que no requieren la capacidad de hospedar fuera de IIS o para comunicarse a través de protocolos que no sean HTTP, pero que utilizan todas las características de la plataforma de aplicaciones Web ASP.NET.

A diferencia de la configuración predeterminada en paralelo, donde la infraestructura de hospedaje de WCF intercepta los mensajes WCF y los enruta fuera de la canalización HTTP, los servicios WCF que se ejecuta en modo de compatibilidad de ASP.NET participan totalmente en el ciclo de vida de la solicitud HTTP de ASP.NET. En el modo de compatibilidad, los servicios de WCF utilizan la canalización HTTP a través de un <xref:System.Web.IHttpHandler> implementación, similar a las solicitudes de manera para las páginas ASPX y servicios Web ASMX se administran. Como resultado, WCF se comporta de forma idéntica a ASMX con respecto a las siguientes características ASP.NET:

- <xref:System.Web.HttpContext>: Pueden tener acceso los servicios WCF que se ejecuta en modo de compatibilidad ASP.NET <xref:System.Web.HttpContext.Current%2A> y su estado asociado.

- Autorización basada en archivo: Los servicios WCF que se ejecuta en modo de compatibilidad ASP.NET pueden ser seguros mediante la asociación de listas de control de acceso (ACL) de archivos del sistema para el archivo .svc del servicio.

- Autorización de URL configurable: ASP. Cuando el servicio WCF se ejecuta en modo de compatibilidad de ASP.NET, se aplican las reglas de autorización de dirección URL de la red para las solicitudes WCF.

- <xref:System.Web.HttpModuleCollection> extensibilidad: Dado que los servicios WCF que se ejecuta en modo de compatibilidad de ASP.NET participan totalmente en el ciclo de vida de la solicitud HTTP de ASP.NET, cualquier módulo HTTP configurado en la canalización HTTP es capaz de funcionar en las solicitudes WCF, tanto antes como después de la invocación del servicio.

- Suplantación de ASP.NET: Se ejecutan con la identidad actual de ASP.NET los servicios WCF suplantar subproceso, que puede ser diferente de la identidad del proceso IIS si se ha habilitado la suplantación de ASP.NET para la aplicación. Si la suplantación de ASP.NET y la suplantación de WCF están habilitadas para una operación de servicio determinado, la implementación del servicio se ejecuta finalmente utilizando la identidad obtenida de WCF.

Modo de compatibilidad ASP.NET de WCF está habilitado en el nivel de aplicación a través de la configuración siguiente (que se encuentra en el archivo Web.config de la aplicación):

```xml
<system.serviceModel>
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true" />
</system.serviceModel>
```

El valor predeterminado es "`true`" Si no se especifica. Establecer este valor en "`false`" indica que todos los servicios WCF que se ejecutan en la aplicación no se ejecutarán en modo de compatibilidad ASP.NET.

Porque el modo de compatibilidad ASP.NET implica la semántica de procesamiento de solicitud que es fundamentalmente diferente del valor predeterminado WCF, implementaciones de servicios individuales tienen la capacidad para controlar si se ejecutan dentro de una aplicación para que ASP.NET Se ha habilitado el modo de compatibilidad. Los servicios pueden utilizar el <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> para indicar si admiten el modo de compatibilidad de ASP.NET. El valor predeterminado para este atributo es <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed>.

```csharp
[AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
public class CalculatorService : ICalculatorSession
{//Implement calculator service methods.}
```

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
> IIS 7.0 y WAS permite a los servicios WCF para comunicarse a través de protocolos que no sean HTTP. Sin embargo, los servicios WCF que se ejecutan en las aplicaciones que han habilitado el modo de compatibilidad ASP.NET no se permiten exponer los extremos no HTTP. Este tipo de configuración genera una excepción de activación cuando el servicio recibe su primer mensaje.

Para obtener más información acerca de cómo habilitar el modo de compatibilidad ASP.NET para los servicios WCF, vea <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode> y [compatibilidad de ASP.NET](../samples/aspnet-compatibility.md) ejemplo.

## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute>
- [Características de hospedaje de Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))
