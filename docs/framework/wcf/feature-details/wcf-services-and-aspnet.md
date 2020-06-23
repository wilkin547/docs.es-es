---
title: Servicios WCF y ASP.NET
description: Obtenga información acerca de cómo hospedar servicios WCF en paralelo con ASP.NET y hospedarlos en el modo de compatibilidad ASP.NET.
ms.date: 03/30/2017
ms.assetid: b980496a-f0b0-4319-8e55-a0f0fa32da70
ms.openlocfilehash: 1d7401f6a326bc50923123acf803e26ce8238415
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246420"
---
# <a name="wcf-services-and-aspnet"></a>Servicios WCF y ASP.NET

En este tema se describen los servicios de hospedaje Windows Communication Foundation (WCF) en paralelo con ASP.NET y los hospedan en el modo de compatibilidad de ASP.NET.

## <a name="hosting-wcf-side-by-side-with-aspnet"></a>Hospedaje de WCF en paralelo con ASP.NET

Los servicios WCF hospedados en Internet Information Services (IIS) se pueden encontrar con. Páginas ASPX y servicios web ASMX dentro de un único dominio de aplicación común. ASP.NET proporciona servicios de infraestructura comunes, como administración de AppDomain y compilación dinámica para el tiempo de ejecución HTTP de WCF y ASP.NET. La configuración predeterminada para WCF es en paralelo con ASP.NET.

![Captura de pantalla que muestra los servicios WCF y ASP .NET: estado compartido.](./media/wcf-services-and-aspnet/windows-communication-foundation-services-asp-dotnet-configuration.gif)

El tiempo de ejecución HTTP de ASP.NET controla las solicitudes de ASP.NET, pero no participa en el procesamiento de las solicitudes destinadas a servicios WCF, aunque estos servicios se hospedan en el mismo AppDomain que el contenido de ASP.NET. En su lugar, el modelo de servicio WCF intercepta los mensajes dirigidos a los servicios WCF y los enruta a través de la pila de canales y transporte WCF.

Los resultados del modelo en paralelo son de la siguiente manera:

- Los servicios ASP.NET y WCF pueden compartir el estado de AppDomain. Dado que los dos marcos pueden coexistir en el mismo AppDomain, WCF también puede compartir el estado de AppDomain con ASP.NET (incluidas las variables estáticas, los eventos, etc.).

- Los servicios WCF se comportan de forma coherente, independientemente del entorno de hospedaje y del transporte. El tiempo de ejecución de HTTP de ASP.NET se acopla de manera intencionada al entorno de hospedaje de IIS/ASP.NET y a la comunicación HTTP. Por el contrario, WCF está diseñado para comportarse de forma coherente en los entornos de hospedaje (WCF se comporta de manera coherente tanto dentro como fuera de IIS) y en el transporte (un servicio hospedado en IIS 7,0 y versiones posteriores tiene un comportamiento coherente en todos los extremos que expone, incluso si algunos de esos puntos de conexión usan protocolos distintos de HTTP).

- Dentro de un AppDomain, las características implementadas por el tiempo de ejecución HTTP se aplican al contenido de ASP.NET, pero no a WCF. Muchas características específicas de HTTP de la plataforma de aplicaciones ASP.NET no se aplican a los servicios WCF hospedados dentro de un AppDomain que contiene contenido de ASP.NET. Ejemplos de estas características incluyen lo siguiente:

  - HttpContext: <xref:System.Web.HttpContext.Current%2A> siempre se `null` obtiene acceso a desde dentro de un servicio WCF. Utilice <xref:System.ServiceModel.Channels.RequestContext> en su lugar.

  - Autorización basada en archivos: el modelo de seguridad de WCF no permite la lista de control de acceso (ACL) aplicada al archivo. SVC del servicio al decidir si se autoriza una solicitud de servicio.

  - Autorización de URL basada en configuración: de forma similar, el modelo de seguridad de WCF no se adhiere a ninguna regla de autorización basada en URL especificada en el elemento de configuración System. Web \<authorization> . Esta configuración se omite para las solicitudes WCF si un servicio se encuentra en un espacio de direcciones URL protegido por ASP. Reglas de autorización de dirección URL de la red.

  - Extensibilidad de HttpModule: la infraestructura de hospedaje de WCF intercepta las solicitudes WCF cuando <xref:System.Web.HttpApplication.PostAuthenticateRequest> se genera el evento y no devuelve el procesamiento a la canalización HTTP ASP.net. Los módulos codificados para interceptar solicitudes en fases posteriores de la canalización no interceptan solicitudes WCF.

  - Suplantación de ASP.NET: de forma predeterminada, las solicitudes WCF siempre se ejecutan como la identidad de proceso de IIS, incluso si ASP.NET está establecido para habilitar la suplantación mediante la opción de configuración System. Web \<identity impersonate="true" /> .

Estas restricciones solo se aplican a servicios WCF hospedados en la aplicación IIS. El comportamiento del contenido de ASP.NET no se ve afectado por la presencia de WCF.

Las aplicaciones WCF que requieren la funcionalidad tradicionalmente proporcionada por la canalización HTTP deben considerar el uso de equivalentes de WCF, que son independientes del host y del transporte:

- <xref:System.ServiceModel.OperationContext> en lugar de <xref:System.Web.HttpContext>.

- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> en lugar de la autorización de archivo/URL de ASP.NET.

- <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector> o los canales dispuestos en capas personalizados en lugar de los módulos HTTP.

- Suplantación para cada operación mediante WCF en lugar de la suplantación System. Web.

Como alternativa, puede considerar la posibilidad de ejecutar los servicios en el modo de compatibilidad de ASP.NET de WCF.

## <a name="hosting-wcf-services-in-aspnet-compatibility-mode"></a>Hospedaje de servicios WCF en el modo de compatibilidad de ASP.NET

Aunque el modelo WCF está diseñado para comportarse de forma coherente entre entornos de hospedaje y transportes, a menudo hay escenarios en los que una aplicación no requiere este grado de flexibilidad. El modo de compatibilidad ASP.NET de WCF es adecuado para escenarios que no requieren la capacidad de hospedar fuera de IIS o para comunicarse a través de protocolos distintos de HTTP, pero que usan todas las características de la plataforma de aplicación Web ASP.NET.

A diferencia de la configuración en paralelo predeterminada, en la que la infraestructura de hospedaje de WCF intercepta los mensajes de WCF y los enruta fuera de la canalización HTTP, los servicios WCF que se ejecutan en modo de compatibilidad ASP.NET participan completamente en el ciclo de vida de la solicitud HTTP ASP.NET. En el modo de compatibilidad, los servicios WCF utilizan la canalización HTTP a través de una <xref:System.Web.IHttpHandler> implementación de, de manera similar a la forma en que se administran las solicitudes de páginas aspx y servicios web asmx. Como resultado, WCF se comporta de forma idéntica a ASMX con respecto a las siguientes características de ASP.NET:

- <xref:System.Web.HttpContext>: Los servicios WCF que se ejecutan en el modo de compatibilidad ASP.NET pueden tener acceso <xref:System.Web.HttpContext.Current%2A> y su estado asociado.

- Autorización basada en archivos: los servicios WCF que se ejecutan en el modo de compatibilidad de ASP.NET pueden ser seguros si se adjuntan las listas de control de acceso (ACL) del sistema de archivos al archivo. SVC del servicio.

- Autorización de URL configurable: ASP. Las reglas de autorización de dirección URL de la red se aplican a las solicitudes WCF cuando el servicio WCF se está ejecutando en el modo de compatibilidad de ASP.NET.

- <xref:System.Web.HttpModuleCollection>extensibilidad: dado que los servicios WCF que se ejecutan en modo de compatibilidad de ASP.NET participan completamente en el ciclo de vida de la solicitud HTTP de ASP.NET, cualquier módulo HTTP configurado en la canalización HTTP puede funcionar en solicitudes WCF antes y después de la invocación del servicio.

- Suplantación de ASP.NET: los servicios WCF se ejecutan con la identidad actual del subproceso suplantado ASP.NET, que puede ser diferente de la identidad de proceso de IIS si se ha habilitado la suplantación ASP.NET para la aplicación. Si la suplantación de ASP.NET y la suplantación de WCF están habilitadas para una operación de servicio determinada, la implementación del servicio se ejecuta en última instancia con la identidad obtenida de WCF.

El modo de compatibilidad de ASP.NET de WCF se habilita en el nivel de aplicación a través de la configuración siguiente (que se encuentra en el archivo de Web.config de la aplicación):

```xml
<system.serviceModel>
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true" />
</system.serviceModel>
```

De forma predeterminada, este valor es `false` si no se especifica. El valor de `false` indica que todos los servicios WCF que se ejecutan en la aplicación no se ejecutarán en el modo de compatibilidad de ASP.net.

Dado que el modo de compatibilidad de ASP.NET implica una semántica de procesamiento de solicitudes que es fundamentalmente diferente del valor predeterminado de WCF, las implementaciones de servicio individuales tienen la capacidad de controlar si se ejecutan dentro de una aplicación para la que se ha habilitado el modo de compatibilidad ASP.NET. Los servicios pueden utilizar el <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> para indicar si admiten el modo de compatibilidad de ASP.NET. El valor predeterminado para este atributo es <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed>.

```csharp
[AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
public class CalculatorService : ICalculatorSession
{//Implement calculator service methods.}
```

La siguiente tabla muestra cómo el valor del modo de compatibilidad de toda la aplicación interactúa con el nivel expresado de compatibilidad del servicio individual:

|Valor de modo de compatibilidad de la aplicación|[AspNetCompatibilityRequirementsMode]<br /><br /> Configuración|Resultado observado|
|--------------------------------------------------|---------------------------------------------------------|---------------------|
|aspNetCompatibilityEnabled = " `true` "|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required>|El servicio se activa correctamente.|
|aspNetCompatibilityEnabled = " `true` "|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed>|El servicio se activa correctamente.|
|aspNetCompatibilityEnabled = " `true` "|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.NotAllowed>|Se produce un error de activación cuando el servicio recibe un mensaje.|
|aspNetCompatibilityEnabled = " `false` "|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required>|Se produce un error de activación cuando el servicio recibe un mensaje.|
|aspNetCompatibilityEnabled = " `false` "|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed>|El servicio se activa correctamente.|
|aspNetCompatibilityEnabled = " `false` "|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.NotAllowed>|El servicio se activa correctamente.|

> [!NOTE]
> IIS 7,0 y WAS permite que los servicios WCF se comuniquen a través de protocolos distintos de HTTP. Sin embargo, los servicios WCF que se ejecutan en aplicaciones que tienen habilitado el modo de compatibilidad ASP.NET no pueden exponer extremos que no sean HTTP. Este tipo de configuración genera una excepción de activación cuando el servicio recibe su primer mensaje.

Para obtener más información acerca de cómo habilitar el modo de compatibilidad de ASP.NET para los servicios WCF, vea <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode> y el ejemplo de [compatibilidad ASP.net](../samples/aspnet-compatibility.md) .

## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute>
- [Características de hospedaje de Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))
