---
title: Novedades de Windows Communication Foundation 4.5
description: En este artículo se describen las características nuevas de Windows Communication Foundation (WCF) versión 4,5 y vínculos a recursos adicionales.
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], what's new
- Windows Communication Foundation [WCF], what's new
ms.assetid: 7e93fe73-af93-46b5-9f63-32f761ee40cf
ms.openlocfilehash: b6ce7fe19a8d7cc00823502e322ee53a1bd0a931
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245627"
---
# <a name="whats-new-in-windows-communication-foundation-45"></a>Novedades de Windows Communication Foundation 4.5

En este tema se describen las características nuevas de Windows Communication Foundation (WCF) versión 4,5.

## <a name="wcf-simplification-features"></a>Características de simplificación de WCF

Se ha hecho un gran esfuerzo para simplificar el desarrollo y el mantenimiento de las aplicaciones de WCF 4.5. Para obtener más información, consulte [características de simplificación de WCF](wcf-simplification-features.md).

### <a name="task-based-async-support"></a>Compatibilidad asincrónica basada en tareas

De forma predeterminada, la característica Agregar referencia de servicio genera métodos de operación de servicio asincrónicos de devolución de tarea. Se realiza tanto para los métodos sincrónicos como para los asincrónicos. De este modo, puede llamar a las operaciones de servicio asincrónicamente mediante el nuevo modelo de programación asincrónico basado en tareas. Cuando llama al método proxy generado, WCF crea un objeto de tarea para representar la operación asincrónica y devuelve dicha tarea. La tarea se completa cuando se completa la operación. Al implementar una operación asincrónica, puede implementarla como una operación asincrónica basada en tareas. Para obtener más información, vea [operaciones sincrónicas y asincrónicas](synchronous-and-asynchronous-operations.md).

### <a name="simplified-generated-configuration-files"></a>Archivos de configuración generados simplificados

Al agregar una referencia de servicio en Visual Studio o al usar la herramienta SvcUtil.exe, se genera un archivo de configuración de cliente. En versiones anteriores de WCF, estos archivos de configuración contenían el valor de cada propiedad de enlace incluso si el valor era el predeterminado. En WCF 4.5, los archivos de configuración generados solo contienen las propiedades de enlace que se establecen en un valor no predeterminado.

Para obtener más información, consulte [características de simplificación de WCF](wcf-simplification-features.md).

### <a name="contract-first-development"></a>Desarrollo de contrato primero

WCF admite ahora el desarrollo de contrato primero. El svcutil.exe tiene un modificador/serviceContract que permite generar contratos de datos y de servicio a partir de un documento WSDL.

### <a name="add-service-reference-from-a-portable-subset-project"></a>Agregar referencia de servicio desde un proyecto de subconjuntos portátiles

Los proyectos de subconjuntos portátiles permiten a los programadores de ensamblados .NET mantener un único árbol de origen y un sistema de compilación, al mismo tiempo que se admiten varias plataformas .NET (escritorio, Silverlight, Windows Phone y Xbox). Los proyectos de subconjuntos portátiles solo hacen referencia a bibliotecas portables de .NET que son ensamblados que se pueden usar en cualquier plataforma .NET. La experiencia del desarrollador es igual que agregar una referencia de servicio en cualquier otra aplicación cliente de WCF. Para obtener más información, vea [Agregar referencia de servicio en un proyecto de subconjunto portátil](add-service-reference-in-a-portable-subset-project.md).

### <a name="aspnet-compatibility-mode-default-changed"></a>Valor predeterminado del modo de compatibilidad de ASP.NET cambiado

WCF proporciona el modo de compatibilidad de ASP.NET para conceder a los desarrolladores acceso total a las características en la canalización HTTP de ASP.NET al escribir servicios WCF. Para usar este modo, debe establecer el `aspNetCompatibilityEnabled` atributo en true en la [\<serviceHostingEnvironment>](../configure-apps/file-schema/wcf/servicehostingenvironment.md) sección de web.config. Además, cualquier servicio de este appDomain debe tener la `RequirementsMode` propiedad <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> establecida en <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed> o <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required> . De forma predeterminada, <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> ahora está establecido en <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed> . Para obtener más información, vea [servicios WCF y ASP.net](./feature-details/wcf-services-and-aspnet.md).

### <a name="new-transport-default-values"></a>Nuevos valores de transporte predeterminados

Para simplificar la configuración, han cambiado varios valores de propiedad de transporte predeterminados. Para obtener más información, consulte [características de simplificación de WCF](wcf-simplification-features.md).

### <a name="xmldictionaryreaderquotas"></a>XmlDictionaryReaderQuotas

<xref:System.Xml.XmlDictionaryReaderQuotas> contiene valores de cuota configurables para los lectores de diccionario de XML que restringen la cantidad de memoria usada por un codificador mientras se crea un mensaje. Aunque estas cuotas son configurables, los valores predeterminados han cambiado para reducir la posibilidad de que un desarrollador tenga que establecerlas explícitamente. Para obtener más información, consulte [características de simplificación de WCF](wcf-simplification-features.md).

### <a name="wcf-configuration-validation"></a>Validación de la configuración de WCF

Como parte del proceso de compilación en Visual Studio, los archivos de configuración de WCF se validan ahora para los atributos definidos en el proyecto. Se muestra una lista de errores de validación o advertencias en Visual Studio si se produce un error en la validación.

### <a name="xml-editor-tooltips"></a>Información sobre herramientas del editor XML

Para ayudar a los desarrolladores de servicios WCF nuevos y existentes a configurar sus servicios, el Editor XML de Visual Studio proporciona ahora información sobre herramientas para cada elemento de configuración que forma parte del archivo de configuración del servicio y sus propiedades.

## <a name="streaming-improvements"></a>Mejoras en streaming

Se agregó compatibilidad con el verdadero streaming asincrónico donde el lado de envío ahora no bloquea los subprocesos si el lado de recepción no está leyendo o lee despacio, lo que aumenta la escalabilidad. Se quitó la limitación de almacenamiento en búfer de mensaje cuando un cliente envía un mensaje transmitido por secuencias a un servicio WCF hospedado en IIS. Para obtener más información, consulte [características de simplificación de WCF](wcf-simplification-features.md).

## <a name="simplifying-exposing-an-endpoint-over-https-with-iis"></a>Simplificar la exposición de un punto de conexión sobre HTTPS con IIS

Se ha agregado una asignación de protocolo HTTPS para simplificar la exposición de un extremo sobre HTTPS. Para habilitar un punto de conexión HTTPS, asegúrese de que el sitio web tenga un enlace HTTPS y un certificado SSL configurado y, a continuación, habilite simplemente HTTPS para el directorio virtual que hospeda el servicio. Si los metadatos están habilitados para el servicio, también se expondrán mediante HTTPS.

## <a name="generating-a-single-wsdl-document"></a>Generar un único documento WSDL

Algunas pilas de procesamiento WSDL de terceros no pueden procesar los documentos WSDL que tienen dependencias de otros documentos mediante xsd:import. WCF permite especificar ahora que toda la información del WSDL se devuelva en un único documento. Para solicitar un solo documento WSDL, anexe "? singleWSDL" al URI al solicitar metadatos del servicio.

## <a name="websocket-support"></a>Compatibilidad de WebSocket

WebSockets es una tecnología que proporciona comunicación bidireccional verdadera por los puertos 80 y 443 con características de rendimiento similares a TCP. Se han agregado dos nuevos enlaces para admitir la comunicación mediante un transporte WebSocket. <xref:System.ServiceModel.NetHttpBinding> y <xref:System.ServiceModel.NetHttpsBinding>. Para obtener más información, vea: [enlaces proporcionados por el sistema](system-provided-bindings.md).

## <a name="new-transport-default-values"></a>Nuevos valores de transporte predeterminados

En la tabla siguiente se describen los valores que han cambiado y dónde encontrar información adicional.

|Propiedad.|Activado|Nuevo valor predeterminado|Para obtener más información, vea|
|--------------|--------|-----------------|------------------------------|
|channelInitializationTimeout|<xref:System.ServiceModel.NetTcpBinding>|30 segundos|<xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.ChannelInitializationTimeout%2A>|
|listenBacklog|<xref:System.ServiceModel.NetTcpBinding>|12 * número de procesadores|<xref:System.ServiceModel.NetTcpBinding.ListenBacklog%2A>|
|maxPendingAccepts|ConnectionOrientedTransportBindingElement<br /><br /> SMSvcHost.exe|2 * número de procesadores para transporte<br /><br /> 4 \* número de procesadores para SMSvcHost.exe|<xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.MaxPendingAccepts%2A> [Configuración del servicio de uso compartido de puertos Net.TCP](./feature-details/configuring-the-net-tcp-port-sharing-service.md)|
|maxPendingConnections|ConnectionOrientedTransportBindingElement|12 * número de procesadores|<xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.MaxPendingConnections%2A>|
|receiveTimeout|SMSvcHost.exe|30 segundos|[Configuración del servicio de uso compartido de puertos Net.TCP](./feature-details/configuring-the-net-tcp-port-sharing-service.md)|

## <a name="xml-editor-tooltips"></a>Información sobre herramientas del editor XML

Para ayudar a los desarrolladores de servicios WCF nuevos y existentes a configurar sus servicios, el Editor XML de Visual Studio proporciona ahora información sobre herramientas para cada elemento de configuración que forma parte del archivo de configuración del servicio y sus propiedades.

## <a name="configuring-wcf-services-in-code"></a>Configurar servicios WCF en el código

Windows Communication Foundation (WCF) permite a los desarrolladores configurar servicios mediante el código o los archivos de configuración. Los archivos de configuración son útiles cuando un servicio se debe configurar después de implementarse. Cuando se usan archivos de configuración, un profesional de TI solo debe actualizar el archivo de configuración; no es necesario que realice ninguna recompilación. Los archivos de configuración, sin embargo, pueden ser complejos y difíciles de mantener. No se admite la depuración de archivos de configuración y se hace referencia a los elementos de configuración por nombre, con lo que la creación de archivos de configuración resulta propensa a errores y difícil. WCF también permite configurar servicios en el código. En versiones anteriores de WCF (4,0 y anteriores), la configuración de servicios en código era muy fácil en escenarios autohospedados, la <xref:System.ServiceModel.ServiceHost> clase permitía configurar los extremos y comportamientos antes de llamar a ServiceHost. Open. En escenarios hospedados en web, sin embargo, no tiene acceso a la clase <xref:System.ServiceModel.ServiceHost>. Para configurar un servicio hospedado en web era necesario crear un `System.ServiceModel.ServiceHostFactory` que creó el <xref:System.ServiceModel.Activation.ServiceHostFactory> y realizar cualquier configuración necesaria. A partir de .NET 4,5, WCF proporciona una manera más fácil de configurar servicios hospedados en Web y autohospedados en el código. Para obtener más información, vea [configuración de servicios WCF en el código](configuring-wcf-services-in-code.md).

## <a name="channelfactory-caching"></a>Almacenamiento en caché de ChannelFactory

Las aplicaciones cliente de WCF usan la clase <xref:System.ServiceModel.ChannelFactory%601> para crear un canal de comunicación con un servicio WCF. La crear de instancias de <xref:System.ServiceModel.ChannelFactory%601> genera sobrecarga porque implica las siguientes operaciones:

1. Construir el árbol <xref:System.ServiceModel.Description.ContractDescription>

2. Reflejar todos los tipos de CLR necesarios

3. Construir la pila del canal

4. Desechar recursos

Para ayudar a reducir esta sobrecarga, WCF puede almacenar en caché los generadores de canal cuando se usa un proxy de cliente de WCF. Para obtener más información, consulte [generador de canales y almacenamiento en caché](./feature-details/channel-factory-and-caching.md).

## <a name="compression-and-the-binary-encoder"></a>Compresión y el codificador binario

A partir de WCF 4.5, el codificador binario de WCF agrega compatibilidad con la compresión. El tipo de compresión se configura con la propiedad <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement.CompressionFormat%2A>. Tanto el cliente como el servicio deben configurar la propiedad <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement.CompressionFormat%2A>. La compresión funcionará para los protocolos HTTP, HTTPS y TCP. Si un cliente especifica usar compresión pero el servicio no la admite, se produce una excepción de protocolo que indica que no coinciden los protocolos. Para obtener más información, vea [elegir un codificador de mensajes](./feature-details/choosing-a-message-encoder.md).

## <a name="udp"></a>UDP

Se ha agregado compatibilidad con un transporte UDP que permite a los desarrolladores escribir servicios que utilizan mensajería "desencadenar y olvidar". Un cliente envía un mensaje a un servicio y no espera ninguna respuesta de él.

## <a name="multiple-authentication-support"></a>Compatibilidad con autenticación múltiple

Se ha agregado compatibilidad para admitir varios modos de autenticación, como compatibles con IIS, en un solo extremo de WCF cuando se usa el transporte HTTP y la seguridad de transporte. IIS permite habilitar varios modos de autenticación en un directorio virtual; esta característica permite que un solo punto de conexión WCF admita los distintos modos de autenticación habilitados para el directorio virtual donde se hospeda el servicio WCF.

## <a name="idn-support"></a>Compatibilidad con IDN

Se ha agregado compatibilidad para permitir servicios WCF con nombres de dominio internacionalizados. Para obtener más información [, consulte WCF y nombres de dominio internacionalizados](./feature-details/wcf-and-internationalized-domain-names.md).

## <a name="httpclient"></a>HttpClient

Se ha agregado una nueva clase denominada <xref:System.Net.Http.HttpClient> para simplificar el trabajo con solicitudes HTTP. Para obtener más información, consulte [creación de aplicaciones sociales y conexiones con servicios http](https://channel9.msdn.com/Events/BUILD/BUILD2011/PLAT-581T) y el [ejemplo de cliente http](https://code.msdn.microsoft.com/windowsapps/HttpClient-sample-55700664).

## <a name="configuration-intellisense"></a>IntelliSense de configuración

Los valores de atributo de los archivos de configuración para los atributos personalizados definidos en el proyecto ahora admiten IntelliSense para facilitar el trabajo con configuraciones de forma rápida y precisa.

## <a name="configuration-tooltips"></a>Información sobre herramientas de configuración

Los elementos y atributos de WCF ahora tienen información sobre herramientas en el editor XML, para identificar con mayor facilidad y precisión el propósito del elemento o atributo.

## <a name="paste-data-as-classes"></a>Pegar datos como clases

En un proyecto de WCF, los tipos de datos definidos en XML (como los expuestos en un servicio) se pueden pegar directamente en una página de códigos. El tipo XML se pegará como un tipo de CLR. Vea [generar clases de tipos de datos a partir de XML](generating-data-type-classes-from-xml.md) para obtener más detalles.

## <a name="webservicehost-and-default-endpoints"></a>WebServiceHost y los puntos de conexión predeterminados

En Visual Studio 2010, WebServiceHost creaba automáticamente un extremo predeterminado sin importar si se había especificado explícitamente un extremo o no. En Visual Studio 2012 y versiones posteriores, WebServiceHost solo crea un punto de conexión predeterminado si no se agregan puntos de conexión explícitamente. Si el cliente espera el punto de conexión predeterminado, puede Agregar explícitamente un punto de conexión y apuntar al cliente. Como alternativa, puede pedirle a WCF que vuelva al comportamiento anterior; para ello, agregue la siguiente configuración al archivo de configuración de aplicaciones

```xml
<appSettings>
    <add key="wcf:webservicehost:enableautomaticendpointscompatability" value="true"/>
  </appSettings>
```

## <a name="ihttpcookiecontainermanager"></a>IHttpCookieContainerManager

Esta interfaz, expuesta por <xref:System.ServiceModel.Channels.IChannelFactory%601>, facilita considerablemente el trabajo con cookies en el lado cliente. Cuando AllowCookies se establece en true en el enlace, puede obtener acceso a las cookies con el siguiente código:

```csharp
IHttpCookieContainerManager cookieManager = factory.GetProperty<IHttpCookieContainerManager>();
System.Net.CookieContainer container = cookieManager.CookieContainer;
```

A continuación, puede establecer o recuperar las cookies desde <xref:System.Net.CookieContainer>. Cuando AllowCookies se establece en false, puede recuperar manualmente las cookies mediante <xref:System.ServiceModel.OperationContext> y enviarlo en otras solicitudes con otro <xref:System.ServiceModel.OperationContext> o inspector de mensaje. La interfaz de IHttpCookieContainerManager permite autenticar un usuario con un servicio y usar la cookie de autenticación devuelta por dicho servicio para autenticar con otros servicios.
