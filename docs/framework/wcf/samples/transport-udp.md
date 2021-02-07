---
description: 'Más información acerca de: transporte: UDP'
title: 'Transporte: UDP'
ms.date: 03/30/2017
ms.assetid: 738705de-ad3e-40e0-b363-90305bddb140
ms.openlocfilehash: ab4afa8850f78258d2ef984a9b7be61e135cadca
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99685535"
---
# <a name="transport-udp"></a>Transporte: UDP

El ejemplo de transporte UDP muestra cómo implementar unidifusión y multidifusión de UDP como transporte de Windows Communication Foundation personalizado (WCF). El ejemplo describe el procedimiento recomendado para crear un transporte personalizado en WCF mediante el marco del canal y los siguientes procedimientos recomendados de WCF. Los pasos para crear un transporte personalizado son los siguientes:  
  
1. Decida qué [patrones de intercambio de mensajes](#MessageExchangePatterns) de canal (IOutputChannel, IInputChannel, IDuplexChannel, IRequestChannel o IReplyChannel) admitirán ChannelFactory y ChannelListener. A continuación, decida si se admitirán las variaciones con sesión de estas interfaces.  
  
2. Cree un generador de canales y un agente de escucha que admitan el patrón de intercambio de mensajes.  
  
3. Asegúrese de que se normalizan las excepciones específicas de red en la clase derivada adecuada de <xref:System.ServiceModel.CommunicationException>.  
  
4. Agregue un [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento que agrega el transporte personalizado a una pila de canales. Para obtener más información, vea [Agregar un elemento de enlace](#AddingABindingElement).  
  
5. Agregue una sección de extensión de elemento de enlace para exponer el nuevo elemento de enlace al sistema de configuración.  
  
6. Agregue las extensiones de metadatos para comunicar las funciones a otros puntos de conexión.  
  
7. Agregue un enlace que configura previamente una pila de elementos de enlace según un perfil bien determinado. Para obtener más información, vea [Agregar un enlace estándar](#AddingAStandardBinding).  
  
8. Agregue una sección de enlace y un elemento de configuración de enlace para exponer el enlace al sistema de configuración. Para obtener más información, consulte [Agregar compatibilidad con la configuración](#AddingConfigurationSupport).  
  
<a name="MessageExchangePatterns"></a>

## <a name="message-exchange-patterns"></a>Modelos de intercambio de mensajes  

 El primer paso a la hora de escribir un transporte personalizado es decidir qué patrones de intercambio de mensajes (MEP) son necesarios para el transporte. Hay tres MEP entre los que elegir:  
  
- Datagrama (IInputChannel/IOutputChannel)  
  
     Al utilizar un MEP de datagrama, un cliente envía un mensaje mediante un intercambio de tipo desencadenar y omitir. Un intercambio de este tipo es uno que exige una confirmación fuera de banda de entrega correcta. El mensaje se podría perderse por el camino y no llegar nunca al servicio. Si la operación de envío se completa correctamente en la parte del cliente, no garantiza que el extremo remoto haya recibido el mensaje. El datagrama es un bloque de creación fundamental para la mensajería, ya que puede crear sus propios protocolos encima de él, incluidos protocolos confiables y seguros. Los canales de datagrama del cliente implementan la interfaz <xref:System.ServiceModel.Channels.IOutputChannel> y los del servicio, la interfaz <xref:System.ServiceModel.Channels.IInputChannel>.  
  
- Solicitud-respuesta (IRequestChannel/IReplyChannel)  
  
     En este MEP, un mensaje se envía y se recibe una respuesta. El patrón está compuesto de los pares solicitud-respuesta. Los ejemplos de llamadas de solicitud-respuesta son llamadas a procedimiento remoto (RPC) y solicitudes GET del explorador. Este patrón también se conoce como "dúplex medio". En este MEP, los canales de cliente implementan <xref:System.ServiceModel.Channels.IRequestChannel> y los canales de servicio <xref:System.ServiceModel.Channels.IReplyChannel>.  
  
- Dúplex (IDuplexChannel)  
  
     El MEP dúplex permite que un cliente envíe un número arbitrario de mensajes y que se reciban en cualquier orden. El MEP de dúplex es como una conversación telefónica, donde cada palabra que se pronuncia es un mensaje. Dado que ambos lados pueden enviar y recibir en este MEP, la interfaz implementada por los canales de servicio y cliente es <xref:System.ServiceModel.Channels.IDuplexChannel>.  
  
 Cada uno de estos MEP también puede admitir sesiones. La funcionalidad agregada proporcionada por un canal con reconocimiento de sesión es que pone en correlación todos los mensajes enviados y recibidos en un canal. El patrón de solicitud-respuesta es una sesión autónoma de dos mensajes, ya que la solicitud y la respuesta se ponen en correlación. Por el contrario, el patrón de solicitud-respuesta que admite las sesiones implica que se ponen en correlación todos los pares de solicitud/respuesta en ese canal entre sí. Esto le da un total de seis MEP (datagrama, solicitud-respuesta, dúplex, datagrama con sesiones, solicitud-respuesta con sesiones y dúplex con sesiones) entre los que elegir.  
  
> [!NOTE]
> En el caso del transporte de UDP, el único MEP que se admite es el datagrama, ya que UDP es en sí mismo un protocolo de tipo "desencadenar y omitir".  
  
### <a name="the-icommunicationobject-and-the-wcf-object-lifecycle"></a>ICommunicationObject y el ciclo de vida del objeto WCF  

 WCF tiene una máquina de Estados común que se usa para administrar el ciclo de vida de objetos como <xref:System.ServiceModel.Channels.IChannel> , <xref:System.ServiceModel.Channels.IChannelFactory> y <xref:System.ServiceModel.Channels.IChannelListener> que se usan para la comunicación. Hay cinco estados donde estos objetos de comunicación pueden existir. La enumeración <xref:System.ServiceModel.CommunicationState> representa estos estados y son los siguientes:  
  
- Creado: este es el estado de una interfaz <xref:System.ServiceModel.ICommunicationObject> la primera vez que se crean instancias de ella. No se produce ninguna entrada/salida (E/S) en este estado.  
  
- Abriendo: transición de objetos a este estado cuando se llama al método <xref:System.ServiceModel.ICommunicationObject.Open%2A>. En este punto, las propiedades se convierten en inmutables y puede comenzar la entrada/salida. Esta transición solo es válida desde el estado Creado.  
  
- Abierto: los objetos pasan a este estado cuando el proceso de apertura se completa. Esta transición solo es válida desde el estado Abriendo. En este punto, se puede usar el objeto para la transferencia.  
  
- Cerrando: los objetos pasan a este estado cuando se llama al método <xref:System.ServiceModel.ICommunicationObject.Close%2A> para que el apagado sea correcto. Esta transición solo es válida desde el estado Abierto.  
  
- Cerrado: en este estado, no se pueden utilizar los objetos. En general, aún se puede acceder a la mayoría de la configuración para su inspección pero no se puede producir ninguna comunicación. Este estado es equivalente a eliminarse.  
  
- Con error: en este estado, se puede tener acceso a los objetos para inspeccionarlos pero no se pueden usar. Cuando se produce un error no recuperable, el objeto pasa a este estado. La única transición válida desde este estado es en el `Closed` Estado.  
  
 Hay eventos que se desencadenan para cada transición de estado. Se puede llamar al método <xref:System.ServiceModel.ICommunicationObject.Abort%2A> en cualquier momento, lo que provoca que el objeto pase inmediatamente de su estado actual al estado Cerrado. Al llamar <xref:System.ServiceModel.ICommunicationObject.Abort%2A>, se finaliza cualquier trabajo inacabado.  
  
<a name="ChannelAndChannelListener"></a>

## <a name="channel-factory-and-channel-listener"></a>Generador de canales y agente de escucha de canales  

 El paso siguiente para escribir un transporte personalizado es crear una implementación de <xref:System.ServiceModel.Channels.IChannelFactory> para los canales de cliente y de <xref:System.ServiceModel.Channels.IChannelListener> para los canales de servicio. La capa de canal usa un patrón de generador para crear canales. WCF proporciona aplicaciones auxiliares de clase base para este proceso.  
  
- La clase <xref:System.ServiceModel.Channels.CommunicationObject> implementa <xref:System.ServiceModel.ICommunicationObject> y aplica el equipo de estado descrito previamente en el paso 2.

- La <xref:System.ServiceModel.Channels.ChannelManagerBase> clase implementa <xref:System.ServiceModel.Channels.CommunicationObject> y proporciona una clase base unificada para <xref:System.ServiceModel.Channels.ChannelFactoryBase> y <xref:System.ServiceModel.Channels.ChannelListenerBase> . La clase <xref:System.ServiceModel.Channels.ChannelManagerBase> trabaja junto con <xref:System.ServiceModel.Channels.ChannelBase>, que es una clase base que implementa <xref:System.ServiceModel.Channels.IChannel>.  
  
- La <xref:System.ServiceModel.Channels.ChannelFactoryBase> clase implementa <xref:System.ServiceModel.Channels.ChannelManagerBase> y <xref:System.ServiceModel.Channels.IChannelFactory> y consolida las `CreateChannel` sobrecargas en un `OnCreateChannel` método abstracto.  
  
- La <xref:System.ServiceModel.Channels.ChannelListenerBase> clase implementa <xref:System.ServiceModel.Channels.IChannelListener> . Se encarga de la administración de estados básica.  
  
 En este ejemplo, la implementación del generador se encuentra en UdpChannelFactory.cs y la implementación del agente de escucha se encuentra en UdpChannelListener.cs. Las implementaciones <xref:System.ServiceModel.Channels.IChannel> están en UdpOutputChannel.cs y UdpInputChannel.cs.  
  
### <a name="the-udp-channel-factory"></a>Generador de canales UDP  

 La clase `UdpChannelFactory` se deriva de la clase <xref:System.ServiceModel.Channels.ChannelFactoryBase>. El ejemplo invalida <xref:System.ServiceModel.Channels.ChannelFactoryBase.GetProperty%2A> para proporcionar acceso a la versión del mensaje del codificador de mensajes. El ejemplo también invalida <xref:System.ServiceModel.Channels.ChannelFactoryBase.OnClose%2A> de manera que podamos anular nuestra instancia de <xref:System.ServiceModel.Channels.BufferManager> cuando se realizan las transiciones del equipo de estado.  
  
#### <a name="the-udp-output-channel"></a>Canal de salida UDP  

 La clase `UdpOutputChannel` implementa la interfaz <xref:System.ServiceModel.Channels.IOutputChannel>. El constructor valida los argumentos y construye un objeto de destino <xref:System.Net.EndPoint> basado en la <xref:System.ServiceModel.EndpointAddress> a la que se pasa.  
  
```csharp
this.socket = new Socket(this.remoteEndPoint.AddressFamily, SocketType.Dgram, ProtocolType.Udp);  
```  
  
 El canal puede cerrarse de forma correcta o incorrecta. Si el canal se cierra correctamente, el socket se cierra y se realiza una llamada al método `OnClose` de la clase base. Si se inicia una excepción, la infraestructura llama a `Abort` para garantizar que se limpia el canal.  
  
```csharp
this.socket.Close(0);  
```  
  
 A continuación, implementamos `Send()` y `BeginSend()` / `EndSend()` . De este modo se divide en dos secciones principales. Primero se serializa el mensaje en una matriz de bytes.  
  
```csharp
ArraySegment<byte> messageBuffer = EncodeMessage(message);  
```  
  
 A continuación, se envían los datos resultantes en la conexión.  
  
```csharp
this.socket.SendTo(messageBuffer.Array, messageBuffer.Offset, messageBuffer.Count, SocketFlags.None, this.remoteEndPoint);  
```  
  
### <a name="the-udpchannellistener"></a>UdpChannelListener  

 `UdpChannelListener`Que el ejemplo implementa se deriva de la <xref:System.ServiceModel.Channels.ChannelListenerBase> clase. Utiliza un socket UDP único para recibir datagramas. El método `OnOpen` recibe datos utilizando el socket UDP en un bucle asincrónico. Los datos se convierten en mensajes utilizando el marco de trabajo de codificación de mensajes:  
  
```csharp
message = MessageEncoderFactory.Encoder.ReadMessage(new ArraySegment<byte>(buffer, 0, count), bufferManager);  
```  
  
 Dado que el mismo canal del datagrama representa mensajes que llegan de varios orígenes, `UdpChannelListener` es un agente de escucha singleton. Hay, como máximo, un activo <xref:System.ServiceModel.Channels.IChannel> asociado a este agente de escucha a la vez. El ejemplo solo genera otro si se elimina subsiguientemente un canal que es devuelto por el método `AcceptChannel`. Cuando se recibe un mensaje, se pone en cola en este canal singleton.  
  
#### <a name="udpinputchannel"></a>UdpInputChannel  

 La `UdpInputChannel` clase implementa `IInputChannel` . Está compuesto de una cola de mensajes entrantes que es rellenada por el socket `UdpChannelListener`. Estos mensajes se quitan de la cola mediante el método `IInputChannel.Receive`.  
  
<a name="AddingABindingElement"></a>

## <a name="adding-a-binding-element"></a>Adición de un elemento de enlace  

 Ahora que se han creado los generadores y canales, se deben exponer en el tiempo de ejecución de ServiceModel mediante un enlace. Un enlace es una colección de elementos de enlace que representa la pila de comunicación asociada con una dirección de servicio. Cada elemento de la pila se representa mediante un [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento.  
  
 En el ejemplo, el elemento de enlace es `UdpTransportBindingElement`, que deriva de <xref:System.ServiceModel.Channels.TransportBindingElement>. Invalida los métodos siguientes para crear los generadores asociados con el enlace.  
  
```csharp
public IChannelFactory<TChannel> BuildChannelFactory<TChannel>(BindingContext context)  
{  
    return (IChannelFactory<TChannel>)(object)new UdpChannelFactory(this, context);  
}  
  
public IChannelListener<TChannel> BuildChannelListener<TChannel>(BindingContext context)  
{  
    return (IChannelListener<TChannel>)(object)new UdpChannelListener(this, context);  
}  
```  
  
 También contiene los miembros para clonar `BindingElement` y devolver nuestro esquema (soap.udp).  
  
## <a name="adding-metadata-support-for-a-transport-binding-element"></a>Agregación de compatibilidad con metadatos para un elemento de enlace de transporte  

 Para integrar nuestro transporte en el sistema de metadatos, debe admitir la importación y exportación de la directiva. Esto nos permite generar clientes de nuestro enlace a través de la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
### <a name="adding-wsdl-support"></a>Agregación de la compatibilidad con WSDL  

 El elemento de enlace del transporte en un enlace es el responsable de la exportación e importación de la información de direccionamiento en metadatos. Al utilizar un enlace SOAP, el elemento de enlace del transporte también debería exportar un URI de transporte correcto en los metadatos.  
  
#### <a name="wsdl-export"></a>Exportación de WSDL  

 Para exportar información de direccionamiento, `UdpTransportBindingElement` implementa la interfaz `IWsdlExportExtension`. El método `ExportEndpoint` agrega la información de direccionamiento correcta al puerto WSDL.  
  
```csharp
if (context.WsdlPort != null)  
{  
    AddAddressToWsdlPort(context.WsdlPort, context.Endpoint.Address, encodingBindingElement.MessageVersion.Addressing);  
}  
```  
  
 La implementación `UdpTransportBindingElement` del método `ExportEndpoint` también exporta un URI de transporte cuando el punto de conexión utiliza un enlace SOAP.  
  
```csharp
WsdlNS.SoapBinding soapBinding = GetSoapBinding(context, exporter);  
if (soapBinding != null)  
{  
    soapBinding.Transport = UdpPolicyStrings.UdpNamespace;  
}  
```  
  
#### <a name="wsdl-import"></a>Importación de WSDL  

 Para extender el sistema de importación de WSDL para que administre la importación de direcciones, debemos agregar la configuración siguiente al archivo de configuración para Svcutil.exe, tal y como se muestra en el archivo Svcutil.exe.config:  
  
```xml
<configuration>  
  <system.serviceModel>  
    <client>  
      <metadata>  
        <policyImporters>  
          <extension type=" Microsoft.ServiceModel.Samples.UdpBindingElementImporter, UdpTransport" />  
        </policyImporters>  
      </metadata>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
 Al ejecutar Svcutil.exe, hay dos opciones para conseguir que Svcutil.exe cargue las extensiones de importación de WSDL:  
  
1. Apunte Svcutil.exe a nuestro archivo de configuración mediante/SvcutilConfig: \<file> .  
  
2. Agregue la sección de configuración a Svcutil.exe.config en el mismo directorio como Svcutil.exe.  
  
 El tipo `UdpBindingElementImporter` implementa la interfaz `IWsdlImportExtension`. El método `ImportEndpoint` importa la dirección del puerto WSDL.  
  
```csharp
BindingElementCollection bindingElements = context.Endpoint.Binding.CreateBindingElements();  
TransportBindingElement transportBindingElement = bindingElements.Find<TransportBindingElement>();  
if (transportBindingElement is UdpTransportBindingElement)  
{  
    ImportAddress(context);  
}  
```  
  
### <a name="adding-policy-support"></a>Agregación de compatibilidad de directiva  

 El elemento de enlace personalizado puede exportar aserciones de directiva en el enlace de WSDL para que un extremo de servicio exprese las funciones de ese elemento de enlace.  
  
#### <a name="policy-export"></a>Exportación de directivas  

 El `UdpTransportBindingElement` tipo implementa `IPolicyExportExtension` para agregar compatibilidad para la exportación de la Directiva. Como resultado, `System.ServiceModel.MetadataExporter` incluye `UdpTransportBindingElement` en la generación de directiva para cualquier enlace que la incluya.  
  
 En `IPolicyExportExtension.ExportPolicy`, agregamos una aserción para UDP y otra si estamos en modo de multidifusión. Esto se debe a que el modo de multidifusión afecta a cómo se construye la pila de comunicaciones, y, por tanto, debe coordinarse entre ambos lados.  
  
```csharp
ICollection<XmlElement> bindingAssertions = context.GetBindingAssertions();  
XmlDocument xmlDocument = new XmlDocument();  
bindingAssertions.Add(xmlDocument.CreateElement(  
UdpPolicyStrings.Prefix, UdpPolicyStrings.TransportAssertion, UdpPolicyStrings.UdpNamespace));  
if (Multicast)  
{  
    bindingAssertions.Add(xmlDocument.CreateElement(
        UdpPolicyStrings.Prefix,
        UdpPolicyStrings.MulticastAssertion,
        UdpPolicyStrings.UdpNamespace));  
}  
```  
  
 Dado que los elementos de enlace de transporte personalizados son responsables de la administración del direccionamiento, la implementación `IPolicyExportExtension` en el `UdpTransportBindingElement` también debe administrar la exportación de las aserciones de directivas WS-Addressing adecuadas para indicar la versión de WS-Addressing que se está utilizando.  
  
```csharp
AddWSAddressingAssertion(context, encodingBindingElement.MessageVersion.Addressing);  
```  
  
#### <a name="policy-import"></a>Importación de directivas  

 Para extender el sistema de importación de directivas, debe agregar la siguiente configuración al archivo de configuración para Svcutil.exe tal y como se muestra en el archivo Svcutil.exe.config.  
  
```xml
<configuration>  
  <system.serviceModel>  
    <client>  
      <metadata>  
        <policyImporters>  
          <extension type=" Microsoft.ServiceModel.Samples.UdpBindingElementImporter, UdpTransport" />  
        </policyImporters>  
      </metadata>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
 A continuación, implementamos `IPolicyImporterExtension` desde nuestra clase registrada (`UdpBindingElementImporter`). En `ImportPolicy()`, examinamos las aserciones en nuestro espacio de nombres y procesamos las que se encargan de la generación del transporte y de la comprobación de si es multidifusión. También debemos quitar las aserciones que administramos de la lista de aserciones de enlace. De nuevo, al ejecutar Svcutil.exe, hay dos opciones para la integración:  
  
1. Apunte Svcutil.exe a nuestro archivo de configuración mediante/SvcutilConfig: \<file> .  
  
2. Agregue la sección de configuración a Svcutil.exe.config en el mismo directorio como Svcutil.exe.  
  
<a name="AddingAStandardBinding"></a>

## <a name="adding-a-standard-binding"></a>Adición de un enlace estándar  

 Nuestro elemento de enlace se puede utilizar de las dos maneras siguientes:  
  
- A través de un enlace personalizado: un enlace personalizado permite al usuario crear su propio enlace basado en un conjunto arbitrario de elementos de enlace.  
  
- Usando un enlace proporcionado por el sistema que incluye nuestro elemento de enlace. WCF proporciona varios de estos enlaces definidos por el sistema, como `BasicHttpBinding` , `NetTcpBinding` y `WsHttpBinding` . Cada uno de estos enlaces está asociado a un perfil bien definido.  
  
 El ejemplo implementa el enlace del perfil en `SampleProfileUdpBinding`, que deriva de <xref:System.ServiceModel.Channels.Binding>. `SampleProfileUdpBinding` contiene hasta cuatro elementos de enlace dentro de él: `UdpTransportBindingElement`, `TextMessageEncodingBindingElement CompositeDuplexBindingElement` y `ReliableSessionBindingElement`.  
  
```csharp
public override BindingElementCollection CreateBindingElements()  
{
    BindingElementCollection bindingElements = new BindingElementCollection();  
    if (ReliableSessionEnabled)  
    {  
        bindingElements.Add(session);  
        bindingElements.Add(compositeDuplex);  
    }  
    bindingElements.Add(encoding);  
    bindingElements.Add(transport);  
    return bindingElements.Clone();  
}  
```  
  
### <a name="adding-a-custom-standard-binding-importer"></a>Agregación de un importador de enlace estándar personalizado  

 Svcutil.exe y el tipo `WsdlImporter`, de forma predeterminada, reconocen e importan los enlaces definidos por el sistema. De lo contrario, el enlace se importa como una instancia `CustomBinding`. Para permitir que Svcutil.exe y `WsdlImporter` importen el `SampleProfileUdpBinding`, el `UdpBindingElementImporter` actúa también como un importador de enlaces estándar personalizado.  
  
 Un importador de este tipo implementa el método `ImportEndpoint` en la interfaz `IWsdlImportExtension` para examinar la instancia `CustomBinding` importada desde los metadatos para ver si el enlace estándar concreto podría haberla generado.  
  
```csharp
if (context.Endpoint.Binding is CustomBinding)  
{  
    Binding binding;  
    if (transportBindingElement is UdpTransportBindingElement)  
    {  
        //if TryCreate is true, the CustomBinding will be replace by a SampleProfileUdpBinding in the  
        //generated config file for better typed generation.  
        if (SampleProfileUdpBinding.TryCreate(bindingElements, out binding))  
        {  
            binding.Name = context.Endpoint.Binding.Name;  
            binding.Namespace = context.Endpoint.Binding.Namespace;  
            context.Endpoint.Binding = binding;  
        }  
    }  
}  
```  
  
 Generalmente, la implementación de un importador de enlaces estándar personalizado, implica la comprobación de las propiedades de los elementos de enlace importados para comprobar que solo las propiedades que pudo establecer el enlace estándar han cambiado y el resto propiedades son sus valores predeterminados. Una estrategia básica para implementar un importador de enlace estándar consiste en crear una instancia de enlace estándar, propagar las propiedades desde los elementos de enlace a la instancia de enlace estándar que admite enlaces estándar y, a continuación, comparar los elementos de enlace desde el enlace estándar con los elementos de enlace importados.  
  
<a name="AddingConfigurationSupport"></a>

## <a name="adding-configuration-support"></a>Agregación de la compatibilidad de configuración  

 Para exponer nuestro transporte a través de la configuración, debemos implementar dos secciones de configuración. El primero es `BindingElementExtensionElement` para `UdpTransportBindingElement`. Esto es para que las implementaciones de `CustomBinding` puedan hacer referencia a nuestro elemento de enlace. El segundo es `Configuration` para `SampleProfileUdpBinding`.  
  
### <a name="binding-element-extension-element"></a>Elemento de extensión de elemento de enlace  

 La sección `UdpTransportElement` es un objeto `BindingElementExtensionElement` que expone `UdpTransportBindingElement` en el sistema de configuración. Con algunas invalidaciones básicas, definimos el nombre de la sección de configuración, el tipo del elemento de enlace y cómo crear el elemento de enlace. Podemos registrar a continuación como se muestra nuestra sección de extensión en un archivo de configuración en el código siguiente.  
  
```xml
<configuration>  
  <system.serviceModel>  
    <extensions>  
      <bindingElementExtensions>  
        <add name="udpTransport" type="Microsoft.ServiceModel.Samples.UdpTransportElement, UdpTransport" />  
      </bindingElementExtensions>  
    </extensions>  
  </system.serviceModel>  
</configuration>  
```  
  
 Se puede hacer referencia a la extensión desde enlaces personalizados para utilizar UDP como el transporte.  
  
```xml
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <customBinding>  
       <binding configurationName="UdpCustomBinding">  
         <udpTransport/>  
       </binding>  
      </customBinding>  
    </bindings>  
  </system.serviceModel>  
</configuration>  
```  
  
### <a name="binding-section"></a>Sección de enlace  

 La sección `SampleProfileUdpBindingCollectionElement` es un objeto `StandardBindingCollectionElement` que expone `SampleProfileUdpBinding` en el sistema de configuración. El volumen de la implementación se delega a `SampleProfileUdpBindingConfigurationElement`, que deriva de `StandardBindingElement`. `SampleProfileUdpBindingConfigurationElement`Tiene propiedades que corresponden a las propiedades de `SampleProfileUdpBinding` y a las funciones que se van a asignar desde el `ConfigurationElement` enlace. Finalmente, se invalida el método `OnApplyConfiguration` en nuestro `SampleProfileUdpBinding`, tal y como se muestra en el siguiente código muestra.  
  
```csharp
protected override void OnApplyConfiguration(string configurationName)  
{  
    if (binding == null)
        throw new ArgumentNullException("binding");

    if (binding.GetType() != typeof(SampleProfileUdpBinding))
    {
        throw new ArgumentException(string.Format(CultureInfo.CurrentCulture,
            "Invalid type for binding. Expected type: {0}. Type passed in: {1}.",
            typeof(SampleProfileUdpBinding).AssemblyQualifiedName,
            binding.GetType().AssemblyQualifiedName));
    }
    SampleProfileUdpBinding udpBinding = (SampleProfileUdpBinding)binding;

    udpBinding.OrderedSession = this.OrderedSession;
    udpBinding.ReliableSessionEnabled = this.ReliableSessionEnabled;
    udpBinding.SessionInactivityTimeout = this.SessionInactivityTimeout;
    if (this.ClientBaseAddress != null)
        udpBinding.ClientBaseAddress = ClientBaseAddress;
}
```  
  
 Para registrar este controlador con el sistema de configuración, agregamos la siguiente sección al archivo de configuración pertinente.  
  
```xml
<configuration>  
  <configSections>  
     <sectionGroup name="system.serviceModel">  
        <sectionGroup name="bindings">  
          <section name="sampleProfileUdpBinding" type="Microsoft.ServiceModel.Samples.SampleProfileUdpBindingCollectionElement, UdpTransport" />  
        </sectionGroup>  
     </sectionGroup>  
  </configSections>  
</configuration>  
```  
  
 A continuación, se puede establecer la referencia desde la sección de configuración serviceModel.  
  
```xml
<configuration>  
  <system.serviceModel>  
    <client>  
      <endpoint configurationName="calculator"  
                address="soap.udp://localhost:8001/"
                bindingConfiguration="CalculatorServer"  
                binding="sampleProfileUdpBinding"
                contract= "Microsoft.ServiceModel.Samples.ICalculatorContract">  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="the-udp-test-service-and-client"></a>Servicio de pruebas y cliente UDP  

 El código de prueba para usar este transporte de ejemplo está disponible en los directorios UdpTestService y UdpTestClient. El código de servicio está compuesto de dos pruebas: una configura los enlaces y puntos de conexión desde el código y la otra lo hace a través de la configuración. Ambas pruebas utilizan dos extremos. Un punto de conexión utiliza `SampleUdpProfileBinding` con [\<reliableSession>](/previous-versions/ms731375(v=vs.90)) establecido en `true` . El otro extremo utiliza un enlace personalizado con `UdpTransportBindingElement`. Esto es equivalente a usar `SampleUdpProfileBinding` con [\<reliableSession>](/previous-versions/ms731375(v=vs.90)) establecido en `false` . Ambas pruebas crean un servicio, agregan un extremo para cada enlace, abren el servicio y, a continuación, esperan a que el usuario presione ENTRAR antes de cerrar el servicio.  
  
 Al iniciar la aplicación de prueba del servicio, debería ver el resultado siguiente.  
  
```console
Testing Udp From Code.  
Service is started from code...  
Press <ENTER> to terminate the service and start service from config...  
```  
  
 Puede ejecutar a continuación la aplicación cliente de prueba con los extremos publicados. La aplicación de prueba del cliente crea un cliente para cada extremo y envía cinco mensajes a cada extremo. El resultado siguiente se encuentra en el cliente.  
  
```console
Testing Udp From Imported Files Generated By SvcUtil.  
0  
3  
6  
9  
12  
Press <ENTER> to complete test.  
```  
  
 A continuación, se muestra el resultado completo en el servicio.  
  
```console
Service is started from code...  
Press <ENTER> to terminate the service and start service from config...  
Hello, world!  
Hello, world!  
Hello, world!  
Hello, world!  
Hello, world!  
   adding 0 + 0  
   adding 1 + 2  
   adding 2 + 4  
   adding 3 + 6  
   adding 4 + 8  
```  
  
 Para ejecutar la aplicación cliente en los extremos publicados utilizando la configuración, presione ENTRAR en el servicio y después ejecute de nuevo el cliente de prueba. Debería ver el siguiente resultado en el servicio.  
  
```console
Testing Udp From Config.  
Service is started from config...  
Press <ENTER> to terminate the service and exit...  
```  
  
 Ejecutar de nuevo el cliente produce lo mismo que los resultados anteriores.  
  
 Para regenerar el código de cliente y la configuración utilizando Svcutil.exe, inicie la aplicación de servicio y, a continuación, ejecute Svcutil.exe siguiente desde el directorio raíz del ejemplo.  
  
```console
svcutil http://localhost:8000/udpsample/ /reference:UdpTransport\bin\UdpTransport.dll /svcutilConfig:svcutil.exe.config  
```  
  
 Observe que Svcutil.exe no genera la configuración de extensión de enlace para `SampleProfileUdpBinding`, por lo que deberá agregarla manualmente.  
  
```xml
<configuration>  
  <system.serviceModel>
    <extensions>  
      <!-- This was added manually because svcutil.exe does not add this extension to the file -->  
      <bindingExtensions>  
        <add name="sampleProfileUdpBinding" type="Microsoft.ServiceModel.Samples.SampleProfileUdpBindingCollectionElement, UdpTransport" />  
      </bindingExtensions>  
    </extensions>  
  </system.serviceModel>  
</configuration>  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).  
  
2. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).  
  
3. Consulte la sección anterior "Servicio de pruebas y cliente UDP".  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Transport\Udp`
