---
description: 'Más información acerca de: características de simplificación de WCF'
title: Características de simplificación de WCF
ms.date: 03/30/2017
ms.assetid: 4535a511-6064-4da0-b361-80262a891663
ms.openlocfilehash: cf89ff7775e2a162760c3c6c598a045ddccdf8d8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99703384"
---
# <a name="wcf-simplification-features"></a>Características de simplificación de WCF

En este tema se describen las características nuevas que simplifican la escritura de aplicaciones WCF.

## <a name="simplified-generated-configuration-files"></a>Archivos de configuración generados simplificados

Al agregar una referencia de servicio en Visual Studio o al usar la herramienta SvcUtil.exe se genera un archivo de configuración de cliente. En versiones anteriores de WCF, estos archivos de configuración contenían el valor de cada propiedad de enlace incluso si el valor era el predeterminado. En WCF 4.5, los archivos de configuración generados solo contienen las propiedades de enlace que se establecen en un valor no predeterminado.

El siguiente es un ejemplo de un archivo de configuración generado por WCF 3.0.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
    <system.serviceModel>
        <bindings>
            <basicHttpBinding>
                <binding name="BasicHttpBinding_IService1" closeTimeout="00:01:00"
                    openTimeout="00:01:00" receiveTimeout="00:10:00" sendTimeout="00:01:00"
                    allowCookies="false" bypassProxyOnLocal="false"
                    hostNameComparisonMode="StrongWildcard" maxBufferSize="65536"
                    maxBufferPoolSize="524288" maxReceivedMessageSize="65536"
                    messageEncoding="Text" textEncoding="utf-8" transferMode="Buffered"
                    useDefaultWebProxy="true">
                    <readerQuotas maxDepth="32" maxStringContentLength="8192"
                        maxArrayLength="16384" maxBytesPerRead="4096"
                        maxNameTableCharCount="16384" />
                    <security mode="None">
                        <transport clientCredentialType="None" proxyCredentialType="None"
                            realm="" />
                        <message clientCredentialType="UserName" algorithmSuite="Default" />
                    </security>
                </binding>
            </basicHttpBinding>
        </bindings>
        <client>
            <endpoint address="http://localhost:36906/Service1.svc" binding="basicHttpBinding"
                bindingConfiguration="BasicHttpBinding_IService1" contract="IService1"
                name="BasicHttpBinding_IService1" />
        </client>
    </system.serviceModel>
</configuration>
```

El siguiente es un ejemplo del mismo archivo de configuración generado por WCF 4.5.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
    <system.serviceModel>
        <bindings>
            <basicHttpBinding>
                <binding name="BasicHttpBinding_IService1" />
            </basicHttpBinding>
        </bindings>
        <client>
            <endpoint address="http://localhost:36906/Service1.svc" binding="basicHttpBinding"
                bindingConfiguration="BasicHttpBinding_IService1" contract="IService1"
                name="BasicHttpBinding_IService1" />
        </client>
    </system.serviceModel>
</configuration>
```

## <a name="contract-first-development"></a>Desarrollo de contrato primero

WCF admite ahora el desarrollo de contrato primero. La herramienta svcutil.exe tiene un modificador/serviceContract que permite generar contratos de datos y de servicio a partir de un documento WSDL.

## <a name="add-service-reference-from-a-portable-subset-project"></a>Agregar referencia de servicio desde un proyecto de subconjuntos portátiles

Los proyectos de subconjuntos portátiles permiten a los programadores de ensamblados .NET mantener un único árbol de origen y un sistema de compilación, al mismo tiempo que se admiten varias implementaciones de .NET (escritorio, Silverlight, Windows Phone y Xbox). Los proyectos de subconjuntos portátiles solo hacen referencia a bibliotecas portables de .NET que son ensamblados que se pueden usar en cualquier implementación de .NET. La experiencia del desarrollador es igual que agregar una referencia de servicio en cualquier otra aplicación cliente de WCF. Para obtener más información, vea [Agregar referencia de servicio en un proyecto de subconjunto portátil](add-service-reference-in-a-portable-subset-project.md).

## <a name="aspnet-compatibility-mode-default-changed"></a>Valor predeterminado del modo de compatibilidad de ASP.NET cambiado

WCF proporciona el modo de compatibilidad de ASP.NET para conceder a los desarrolladores acceso total a las características en la canalización HTTP de ASP.NET al escribir servicios WCF. Para usar este modo, debe establecer el `aspNetCompatibilityEnabled` atributo en true en la [\<serviceHostingEnvironment>](../configure-apps/file-schema/wcf/servicehostingenvironment.md) sección de web.config. Además, cualquier servicio de este appDomain debe tener la `RequirementsMode` propiedad <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> establecida en <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed> o <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required> . De forma predeterminada, <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> ahora está establecido en <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed> y la plantilla de aplicación de servicio WCF predeterminada establece el `aspNetCompatibilityEnabled` atributo en `true` . Para obtener más información, vea [novedades de Windows Communication Foundation 4,5](whats-new.md) y [servicios WCF y ASP.net](./feature-details/wcf-services-and-aspnet.md).

## <a name="streaming-improvements"></a>Mejoras en streaming

- Se ha agregado a WCF una nueva compatibilidad para streaming asincrónico. Para habilitar el streaming asincrónico, agregue el comportamiento de punto de conexión <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior> al host de servicio y establezca la propiedad <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior.AsynchronousSendEnabled%2A> en `true`. Esto puede beneficiar a la escalabilidad cuando un servicio envía mensajes de secuencias a varios clientes que leen despacio. WCF ya no bloquea un subproceso por cliente y liberará el subproceso para atender a otro cliente.

- Se han quitado las limitaciones sobre el almacenamiento en búfer de mensajes cuando un servicio está hospedado en IIS. En versiones anteriores de WCF, al recibir un mensaje para un servicio hospedado por IIS que usaba transferencia de mensajes de streaming, ASP.NET almacenaba en búfer todo el mensaje antes de enviarlo a WCF. Esto provocaba que el consumo de memoria fuera grande. Este almacenamiento en búfer se ha quitado en .NET Framework 4,5 y ahora los servicios WCF hospedados en IIS pueden iniciar el procesamiento del flujo entrante antes de que se haya recibido el mensaje completo, lo que permite una transmisión por secuencias verdadera. Esto permite que WCF responda inmediatamente a los mensajes y permite mejorar el rendimiento. Además, ya no es necesario especificar un valor para `maxRequestLength`, el límite de tamaño de ASP.NET en las solicitudes entrantes. Si se establece esta propiedad, se omite. Para obtener más información, `maxRequestLength` vea [ \<httpRuntime> elemento de configuración](/previous-versions/dotnet/netframework-1.1/e1f13641(v=vs.71)). Todavía tendrá que configurar el maxAllowedContentLength. para obtener más información, consulte [límites de solicitudes de IIS](/previous-versions/iis/settings-schema/ms689462(v=vs.90)).

## <a name="new-transport-default-values"></a>Nuevos valores de transporte predeterminados

En la tabla siguiente se describen los valores que han cambiado y dónde encontrar información adicional.

|Propiedad|Activado|Nuevo valor predeterminado|Más información|
|--------------|--------|-----------------|----------------------|
|channelInitializationTimeout|<xref:System.ServiceModel.NetTcpBinding>|30 segundos|Esta propiedad determina cuánto tiempo puede tardar una conexión TCP en autenticarse a sí misma mediante el protocolo de tramas .NET. Un cliente debe enviar algunos datos iniciales antes de que el servidor tenga información suficiente para realizar la autenticación. Este tiempo de expiración se ha hecho intencionadamente más breve que ReceiveTimeout (10 min) para que los clientes no autenticados y malintencionados no conserven las conexiones con el servidor durante mucho tiempo. El valor predeterminado es 30 segundos. Para obtener más información acerca de <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.ChannelInitializationTimeout%2A>|
|listenBacklog|<xref:System.ServiceModel.NetTcpBinding>|16 * número de procesadores|Esta propiedad del nivel de socket describe el número de solicitudes "pendientes de aceptación" que se van a poner en cola. Si la cola de trabajos pendientes de escucha se llena, las nuevas solicitudes de socket se rechazarán. Para obtener más información acerca de <xref:System.ServiceModel.NetTcpBinding.ListenBacklog%2A>|
|maxPendingAccepts|ConnectionOrientedTransportBindingElement<br /><br /> SMSvcHost.exe|2 * número de procesadores para transporte<br /><br /> 4 \* número de procesadores para SMSvcHost.exe|Esta propiedad limita el número de canales que el servidor pueda tener en espera en un agente de escucha. Cuando MaxPendingAccepts es demasiado bajo, hay un pequeño intervalo de tiempo en el que todos los canales en espera han iniciado conexiones de mantenimiento, pero sin que ningún canal nuevo haya empezado a escuchar. Una conexión puede llegar durante este intervalo y producirá un error porque no hay nada en espera en el servidor. Esta propiedad se puede configurar si se establece la propiedad <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.MaxPendingConnections%2A> en un número mayor. Para obtener más información, vea <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.MaxPendingAccepts%2A> y [configurar el servicio de uso compartido de puertos net. TCP.](./feature-details/configuring-the-net-tcp-port-sharing-service.md)|
|maxPendingConnections|ConnectionOrientedTransportBindingElement|12 * número de procesadores|Esta propiedad controla cuántas conexiones ha aceptado un transporte pero no las ha seleccionado el distribuidor de ServiceModel. Para establecer este valor, use `MaxConnections` en el enlace o `maxOutboundConnectionsPerEndpoint` en el elemento de enlace. Para obtener más información acerca de <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.MaxPendingConnections%2A>|
|receiveTimeout|SMSvcHost.exe|30 segundos|Esta propiedad especifica el tiempo de expiración para la lectura de datos de trama de TCP y para la conexión mediante el envío desde las conexiones subyacentes. Existe para limitar el tiempo que el servicio SMSvcHost.exe se mantiene ocupado para leer los datos de preámbulo de una conexión entrante. Para obtener más información, vea [configurar el servicio de uso compartido de puertos net. TCP](./feature-details/configuring-the-net-tcp-port-sharing-service.md).|

> [!NOTE]
> Estos valores predeterminados nuevos se usan solo si implementa el servicio WCF en un equipo con .NET Framework 4.5. Si implementa el mismo servicio en un equipo con .NET Framework 4.0, se usan los valores predeterminados de .NET Framework 4.0. En tales casos se recomienda configurar estos valores de forma explícita.

## <a name="xmldictionaryreaderquotas"></a>XmlDictionaryReaderQuotas

<xref:System.Xml.XmlDictionaryReaderQuotas> contiene valores de cuota configurables para los lectores de diccionario de XML que restringen la cantidad de memoria usada por un codificador mientras se crea un mensaje. Aunque estas cuotas son configurables, los valores predeterminados han cambiado para reducir la posibilidad de que un desarrollador tenga que establecerlas explícitamente. La cuota de `MaxReceivedMessageSize` no se ha cambiado, de modo que aún puede limitar el consumo de memoria para evitar que sea necesario tratar la complejidad de <xref:System.Xml.XmlDictionaryReaderQuotas>. En la tabla siguiente se muestran las cuotas, sus nuevos valores predeterminados y una breve descripción de para qué se usa cada cuota.

|Nombre de cuota|Valor predeterminado|Descripción|
|----------------|-------------------|-----------------|
|<xref:System.Xml.XmlDictionaryReaderQuotas.MaxArrayLength%2A>|Int32.MaxValue|Obtiene y establece la longitud máxima permitida de matriz. Esta cuota limita el tamaño máximo de una matriz de primitivas que devuelve el lector XML, incluidas las matrices de bytes. Esta cuota no limita el consumo de la memoria en el propio lector XML, sino en cualquier componente que esté utilizando el lector. Por ejemplo, cuando <xref:System.Runtime.Serialization.DataContractSerializer> utiliza un lector protegido con <xref:System.Xml.XmlDictionaryReaderQuotas.MaxArrayLength%2A>, no deserializa matrices de bytes mayores que esta cuota.|
|<xref:System.Xml.XmlDictionaryReaderQuotas.MaxBytesPerRead%2A>|Int32.MaxValue|Obtiene y establece el máximo permitido de bytes devueltos para cada lectura. Esta cuota limita el número de bytes que se leen en una operación de lectura única al leer la etiqueta de inicio de elemento y sus atributos. (En los casos en que no haya transmisión, el propio nombre del elemento no se cuenta para la cuota). Tener demasiados atributos XML puede usar un tiempo de proceso desproporcionado porque se tiene que comprobar la unicidad de los nombres de atributo. <xref:System.Xml.XmlDictionaryReaderQuotas.MaxBytesPerRead%2A> mitiga esta amenaza.|
|<xref:System.Xml.XmlDictionaryReaderQuotas.MaxDepth%2A>|128 nodos de profundidad|Esta cuota limita la profundidad máxima del anidamiento de elementos XML. <xref:System.Xml.XmlDictionaryReaderQuotas.MaxDepth%2A> interactúa con <xref:System.Xml.XmlDictionaryReaderQuotas.MaxBytesPerRead%2A>: el lector siempre mantiene los datos en memoria para el elemento vigente y todos sus antecesores, por lo que el consumo máximo de la memoria del lector es proporcional al producto de estos dos valores. Al deserializar un gráfico de objetos profundamente anidado, el deserializador se ve obligado a obtener acceso a la pila completa e iniciar una <xref:System.StackOverflowException>irrecuperable. Existe una correlación directa entre anidamiento de XML y anidamiento de objeto para <xref:System.Runtime.Serialization.DataContractSerializer> y <xref:System.Xml.Serialization.XmlSerializer>. <xref:System.Xml.XmlDictionaryReaderQuotas.MaxDepth%2A> se usa para mitigar esta amenaza.|
|<xref:System.Xml.XmlDictionaryReaderQuotas.MaxNameTableCharCount%2A>|Int32.MaxValue|Esta cuota limita el número máximo de caracteres permitidos en un objeto nametable. La tabla de nombres contiene ciertas cadenas (como espacios de nombres y prefijos) que se encuentran al procesar un documento XML. Como estas cadenas están almacenadas en búfer en la memoria, esta cuota se usa para evitar el almacenamiento en búfer excesivo cuando se espera streaming.|
|<xref:System.Xml.XmlDictionaryReaderQuotas.MaxStringContentLength%2A>|Int32.MaxValue|Esta cuota limita el tamaño máximo de la cadena que el lector XML devuelve. Esta cuota no limita el consumo de la memoria en el propio lector XML, sino en el componente que está utilizando el lector. Por ejemplo, cuando <xref:System.Runtime.Serialization.DataContractSerializer> utiliza un lector protegido con <xref:System.Xml.XmlDictionaryReaderQuotas.MaxStringContentLength%2A>, no deserializa cadenas mayores que esta cuota.|

> [!IMPORTANT]
> Consulte "uso de XML de forma segura" en [consideraciones de seguridad para datos](./feature-details/security-considerations-for-data.md) para obtener más información sobre la protección de los datos.

> [!NOTE]
> Estos valores predeterminados nuevos se usan solo si implementa el servicio WCF en un equipo con .NET Framework 4.5. Si implementa el mismo servicio en un equipo con .NET Framework 4.0, se usan los valores predeterminados de .NET Framework 4.0. En tales casos se recomienda configurar estos valores de forma explícita.

## <a name="wcf-configuration-validation"></a>Validación de la configuración de WCF

Como parte del proceso de compilación en Visual Studio, los archivos de configuración de WCF ahora se validan. Se muestra una lista de errores de validación o advertencias en Visual Studio si se produce un error en la validación.

## <a name="xml-editor-tooltips"></a>Información sobre herramientas del editor XML

Para ayudar a los desarrolladores de servicios WCF nuevos y existentes a configurar sus servicios, el Editor XML de Visual Studio proporciona ahora información sobre herramientas para cada elemento de configuración que forma parte del archivo de configuración del servicio y sus propiedades.

## <a name="basichttpbinding-improvements"></a>Mejoras de BasicHttpBinding

1. Permite a un único extremo de WCF responder a distintos modos de autenticación.

2. Permite que la configuración de seguridad de un servicio WCF esté controlada por IIS
