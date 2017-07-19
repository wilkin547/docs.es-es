---
title: "Novedades de Windows Communication Foundation 4.5 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WCF [WCF], novedades"
  - "Windows Communication Foundation [WCF], novedades"
ms.assetid: 7e93fe73-af93-46b5-9f63-32f761ee40cf
caps.latest.revision: 35
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 35
---
# Novedades de Windows Communication Foundation 4.5
En este tema, se describen las características nuevas de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].  
  
## Características de simplificación de WCF  
 Se ha hecho un gran esfuerzo para simplificar el desarrollo y el mantenimiento de las aplicaciones de WCF 4.5.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Características de simplificación de WCF](../../../docs/framework/wcf/wcf-simplification-features.md).  
  
### Compatibilidad asincrónica basada en tareas  
 De forma predeterminada, la característica Agregar referencia de servicio genera métodos de operación de servicio asincrónicos de devolución de tarea.Se realiza tanto para los métodos sincrónicos como para los asincrónicos.De este modo, puede llamar a las operaciones de servicio asincrónicamente mediante el nuevo modelo de programación asincrónico basado en tareas.Cuando llama al método proxy generado, WCF crea un objeto de tarea para representar la operación asincrónica y devuelve dicha tarea.La tarea se completa cuando finaliza la operación. Al implementar una operación asincrónica se puede implementar como una operación asincrónica basada en tareas.Para obtener más información, vea [Operaciones sincrónicas y asincrónicas](../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).  
  
### Archivos de configuración generados simplificados  
 Al agregar una referencia de servicio en Visual Studio o al usar la herramienta SvcUtil.exe, se genera un archivo de configuración de cliente.En versiones anteriores de WCF, estos archivos de configuración contenían el valor de cada propiedad de enlace incluso si el valor era el predeterminado.En WCF 4.5, los archivos de configuración generados solo contienen las propiedades de enlace que se establecen en un valor no predeterminado.  
  
 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [Características de simplificación de WCF](../../../docs/framework/wcf/wcf-simplification-features.md)  
  
### Desarrollo de contrato primero  
 WCF admite ahora el desarrollo de contrato primero.Svcutl.exe tiene un modificador \/serviceContract que permite generar contratos de servicio y datos a partir de un documento WSDL.  
  
### Agregar referencia de servicio desde un proyecto de subconjuntos portátiles  
 Los proyectos de subconjuntos portátiles permiten a los programadores de ensamblados .NET mantener un único árbol de origen y un sistema de compilación a la vez que se admiten varias plataformas .NET \(escritorio, Silverlight, Windows Phone y XBOX\).Los proyectos de subconjuntos portátiles solo hacen referencia a bibliotecas portátiles de .NET que son un ensamblado de .NET Framework que puede usarse en cualquier plataforma básica de .NET.La experiencia del desarrollador es igual que agregar una referencia de servicio en cualquier otra aplicación cliente de WCF.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Agregar referencia de servicio en un proyecto de subconjuntos portátiles](../../../docs/framework/wcf/add-service-reference-in-a-portable-subset-project.md).  
  
### Valor predeterminado del modo de compatibilidad de ASP.NET cambiado  
 WCF proporciona el modo de compatibilidad de ASP.NET para conceder a los desarrolladores acceso total a las características en la canalización HTTP de ASP.NET al escribir servicios WCF.Para usar este modo, debe establecer el atributo `aspNetCompatibilityEnabled` en true en la sección [\<serviceHostingEnvironment\>](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) de web.config.Además, cualquier servicio de este appDomain debe tener la propiedad `RequirementsMode` en su <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> establecida en <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode> o en <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode>.De manera predeterminada, <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> se establece ahora en <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode>.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][What's New in Windows Communication Foundation](../../../docs/framework/wcf/whats-new.md) y [Servicios WCF y ASP.NET](../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).  
  
### Nuevos valores predeterminados de transporte  
 Para simplificar la configuración, han cambiado varios valores de propiedad de transporte predeterminados.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Características de simplificación de WCF](../../../docs/framework/wcf/wcf-simplification-features.md).  
  
### XmlDictionaryReaderQuotas  
 <xref:System.Xml.XmlDictionaryReaderQuotas> contiene valores de cuota configurables para los lectores de diccionario de XML que restringen la cantidad de memoria usada por un codificador mientras se crea un mensaje.Aunque estas cuotas son configurables, los valores predeterminados han cambiado para reducir la posibilidad de que un desarrollador tenga que establecerlas explícitamente.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Características de simplificación de WCF](../../../docs/framework/wcf/wcf-simplification-features.md).  
  
### Validación de la configuración de WCF  
 Como parte del proceso de compilación en Visual Studio, los archivos de configuración de WCF se validan ahora para los atributos definidos en el proyecto.Se muestra una lista de errores de validación o advertencias en Visual Studio si se produce un error en la validación.  
  
### Información sobre herramientas del editor XML  
 Para ayudar a los desarrolladores de servicios WCF nuevos y existentes a configurar sus servicios, el Editor XML de Visual Studio proporciona ahora información sobre herramientas para cada elemento de configuración que forma parte del archivo de configuración del servicio y sus propiedades .  
  
## Mejoras en streaming  
 Se agregó compatibilidad con el verdadero streaming asincrónico donde el lado de envío ahora no bloquea los subprocesos si el lado de recepción no está leyendo o lee despacio, lo que aumenta la escalabilidad.Se quitó la limitación de almacenamiento en búfer de mensaje cuando un cliente envía un mensaje transmitido por secuencias a un servicio WCF hospedado en IIS.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Características de simplificación de WCF](../../../docs/framework/wcf/wcf-simplification-features.md).  
  
## Simplificar la exposición de un extremo sobre HTTPS con IIS  
 Se ha agregado una asignación de protocolo HTTPS para simplificar la exposición de un extremo sobre HTTPS.Para habilitar un extremo HTTPS, asegúrese de que el sitio web tenga un enlace HTTPS y un certificado SSL configurado y, a continuación, habilite simplemente HTTPS para el directorio virtual que hospeda el servicio.Si los metadatos están habilitados para el servicio, también se expondrán mediante HTTPS.  
  
## Generar un único documento WSDL  
 Algunas pilas de procesamiento WSDL de terceros no pueden procesar los documentos WSDL que tienen dependencias de otros documentos mediante xsd:import.WCF permite especificar ahora que toda la información del WSDL se devuelva en un único documento.Para solicitar un solo documento WSDL, anexe “?singleWSDL” al URI cuando solicite metadatos del servicio.  
  
## Compatibilidad de WebSocket  
 WebSockets es una tecnología que proporciona comunicación bidireccional verdadera por los puertos 80 y 443 con características de rendimiento similares a TCP.Se han agregado dos nuevos enlaces para admitir la comunicación mediante un transporte WebSocket.<xref:System.ServiceModel.NetHttpBinding> y <xref:System.ServiceModel.NetHttpsBinding>.Para obtener más información, vea [Enlaces proporcionados por el sistema](../../../docs/framework/wcf/system-provided-bindings.md).  
  
## Nuevos valores de transporte predeterminados  
 En la tabla siguiente se describen los valores que han cambiado y dónde encontrar información adicional.  
  
|Propiedad|On|Nuevo valor predeterminado|Para obtener más información, vea|  
|---------------|--------|--------------------------------|---------------------------------------|  
|channelInitializationTimeout|<xref:System.ServiceModel.NetTcpBinding>|30 segundos|<xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.ChannelInitializationTimeout%2A>|  
|listenBacklog|<xref:System.ServiceModel.NetTcpBinding>|12 \* número de procesadores|<xref:System.ServiceModel.NetTcpBinding.ListenBacklog%2A>|  
|maxPendingAccepts|ConnectionOrientedTransportBindingElement<br /><br /> SMSvcHost.exe|2 \* número de procesadores para transporte<br /><br /> 4 \* número de procesadores para SMSvcHost.exe|<xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.MaxPendingAccepts%2A> [Configuring the Net.TCP Port Sharing Service](http://msdn.microsoft.com/es-es/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0)|  
|maxPendingConnections|ConnectionOrientedTransportBindingElement|12 \* número de procesadores|<xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.MaxPendingConnections%2A>|  
|receiveTimeout|SMSvcHost.exe|30 segundos|[Configuring the Net.TCP Port Sharing Service](http://msdn.microsoft.com/es-es/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0)|  
  
## Información sobre herramientas del editor XML  
 Para ayudar a los desarrolladores de servicios WCF nuevos y existentes a configurar sus servicios, el Editor XML de Visual Studio proporciona ahora información sobre herramientas para cada elemento de configuración que forma parte del archivo de configuración del servicio y sus propiedades.  
  
## Configurar servicios WCF en el código  
 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] permite a los desarrolladores configurar servicios mediante archivos de configuración o código.Los archivos de configuración son útiles cuando un servicio se debe configurar después de implementarse.Cuando se usan archivos de configuración, un profesional de TI solo debe actualizar el archivo de configuración; no es necesario que realice ninguna recompilación.Los archivos de configuración, sin embargo, pueden ser complejos y difíciles de mantener.No se admite la depuración de archivos de configuración y se hace referencia a los elementos de configuración por nombre, con lo que la creación de archivos de configuración resulta propensa a errores y difícil.[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] también permite configurar servicios en el código.En versiones anteriores de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] \(4.0 y anteriores\), la configuración de servicios en código era sencilla en escenarios autohospedados; la clase <xref:System.ServiceModel.ServiceHost> permitía configurar extremos y comportamientos antes de llamar a ServiceHost.Open.En escenarios hospedados en web, sin embargo, no tiene acceso a la clase <xref:System.ServiceModel.ServiceHost>.Para configurar un servicio hospedado en web era necesario crear un <xref:System.ServiceModel.ServiceHostFactory> que creó el <xref:System.ServiceModel.ServiceHost> y realizar cualquier configuración necesaria.A partir de .NET 4.5, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] proporciona una manera más fácil de configurar los servicios autohospedados y los hospedados en web en el código.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Configurar servicios WCF en el código](../../../docs/framework/wcf/configuring-wcf-services-in-code.md).  
  
## Almacenamiento en caché de ChannelFactory  
 Las aplicaciones cliente de WCF usan la clase <xref:System.ServiceModel.ChannelFactory%601> para crear un canal de comunicación con un servicio WCF.La crear de instancias de <xref:System.ServiceModel.ChannelFactory%601> genera sobrecarga porque implica las siguientes operaciones:  
  
1.  Construir el árbol <xref:System.ServiceModel.Description.ContractDescription>  
  
2.  Reflejar todos los tipos de CLR necesarios  
  
3.  Construir la pila del canal  
  
4.  Desechar recursos  
  
 Para ayudar a reducir esta sobrecarga, WCF puede almacenar en caché los generadores de canal cuando se usa un proxy de cliente de WCF.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Generador de canales y almacenamiento en memoria caché](../../../docs/framework/wcf/feature-details/channel-factory-and-caching.md).  
  
## Compresión y el codificador binario  
 A partir de WCF 4.5, el codificador binario de WCF agrega compatibilidad con la compresión.El tipo de compresión se configura con la propiedad <xref:System.ServiceModel.Channels.BinaryMessageEncodingElement.CompressionFormat%2A>.Tanto el cliente como el servicio deben configurar la propiedad <xref:System.ServiceModel.Channels.BinaryMessageEncodingElement.CompressionFormat%2A>.La compresión funcionará para los protocolos HTTP, HTTPS y TCP.Si un cliente especifica usar compresión pero el servicio no la admite, se produce una excepción de protocolo que indica que no coinciden los protocolos.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Elección de un codificador de mensajes](../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
  
## UDP  
 Se ha agregado compatibilidad para un transporte UDP que permite a los desarrolladores escribir servicios que usan mensajería “dispare y olvídese".Un cliente envía un mensaje a un servicio y no espera ninguna respuesta de él.  
  
## Compatibilidad con autenticación múltiple  
 Se ha agregado compatibilidad para admitir varios modos de autenticación, como compatibles con IIS, en un solo extremo de WCF cuando se usa el transporte HTTP y la seguridad de transporte.IIS permite habilitar varios modos de autenticación en un directorio virtual; esta característica permite que un solo extremo WCF admita los distintos modos de autenticación habilitados para el directorio virtual donde se hospeda el servicio WCF.  
  
## Compatibilidad con IDN  
 Se ha agregado compatibilidad para permitir servicios WCF con nombres de dominio internacionalizados.Para obtener más información, vea [WCF y nombres de dominio internacionalizados](../../../docs/framework/wcf/feature-details/wcf-and-internationalized-domain-names.md).  
  
## HttpClient  
 Se ha agregado una nueva clase denominada <xref:System.Net.Http.HttpClient> para simplificar el trabajo con solicitudes HTTP.Para obtener más información, vea [Crear aplicaciones sociales y conectadas a servicios HTTP](http://go.microsoft.com/fwlink/?LinkId=231886) y [Ejemplo de cliente HTTP](http://code.msdn.microsoft.com/windowsapps/HttpClient-sample-55700664).  
  
## IntelliSense de configuración  
 Los valores de atributo de los archivos de configuración para los atributos personalizados definidos en el proyecto ahora admiten IntelliSense para facilitar el trabajo con configuraciones de forma rápida y precisa.  
  
## Información sobre herramientas de configuración  
 Los elementos y atributos de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] ahora tienen información sobre herramientas en el Editor XML, para identificar con mayor facilidad y exactitud el propósito del elemento o atributo.  
  
## Pegar datos como clases  
 En un proyecto de WCF, los tipos de datos definidos en XML \(como los expuestos en un servicio\) se pueden pegar directamente en una página de códigos.El tipo XML se pegará como un tipo de CLR.Vea [Generar clases de tipos de datos a partir de XML](../../../docs/framework/wcf/generating-data-type-classes-from-xml.md) para obtener más información.  
  
## WebServiceHost y los extremos predeterminados  
 En Visual Studio 2010, WebServiceHost creaba automáticamente un extremo predeterminado sin importar si se había especificado explícitamente un extremo o no.En Visual Studio 2012, WebServiceHost solo creará un extremo predeterminado si no se agrega ningún extremo explícitamente.Si el cliente espera el extremo predeterminado, se puede agregar explícitamente un extremo y dirigir el cliente a él.Como alternativa, puede pedirle a WCF que vuelva al comportamiento anterior; para ello, agregue la siguiente configuración al archivo de configuración de aplicaciones  
  
```xml  
<appSettings>  
    <add key="wcf:webservicehost:enableautomaticendpointscompatability" value="true"/>  
  </appSettings>  
  
```  
  
## IHttpCookieContainerManager  
 Esta interfaz, expuesta por <xref:System.ServiceModel.Channels.HttpChannelFactory>, facilita considerablemente el trabajo con cookies en el lado cliente.Cuando AllowCookies se establece en true en el enlace, puede obtener acceso a las cookies con el siguiente código:  
  
```csharp  
IHttpCookieContainerManager cookieManager = factory.GetProperty<IHttpCookieContainerManager>();   
System.Net.CookieContainer container = cookieManager.CookieContainer;  
  
```  
  
 A continuación, puede establecer o recuperar las cookies desde <xref:System.Net.CookieContainer>.Cuando AllowCookies se establece en false, puede recuperar manualmente las cookies mediante <xref:System.ServiceModel.OperationContext> y enviarlo en otras solicitudes con otro <xref:System.ServiceModel.OperationContext> o inspector de mensaje.La interfaz de IHttpCookieContainerManager permite autenticar un usuario con un servicio y usar la cookie de autenticación devuelta por dicho servicio para autenticar con otros servicios.