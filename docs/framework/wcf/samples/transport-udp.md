---
title: "Transporte: UDP | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 738705de-ad3e-40e0-b363-90305bddb140
caps.latest.revision: 48
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 48
---
# Transporte: UDP
El ejemplo de transporte UDP muestra cómo implementar unidifusión y multidifusión de UDP como un transporte de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] personalizado.El ejemplo describe el procedimiento recomendado para crear un transporte personalizado en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], utilizando el marco del canal y los siguientes procedimientos recomendados de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].Los pasos para crear un transporte personalizado son los siguientes:  
  
1.  Decida qué [Modelos de intercambio de mensajes](#MessageExchangePatterns) del canal \(IOutputChannel, IInputChannel, IDuplexChannel, IRequestChannel o IReplyChannel\) admitirán ChannelFactory y ChannelListener.A continuación, decida si se admitirán las variaciones con sesión de estas interfaces.  
  
2.  Cree un generador de canales y un agente de escucha que admitan el modelo de intercambio de mensajes.  
  
3.  Asegúrese de que se normalizan las excepciones específicas de red en la clase derivada adecuada de <xref:System.ServiceModel.CommunicationException>.  
  
4.  Agregue un elemento [\<enlace\>](../../../../docs/framework/misc/binding.md) que añada el transporte personalizado a una pila de canales.Para obtener más información, vea [Adición de un elemento de enlace](#AddingABindingElement).  
  
5.  Agregue una sección de extensión de elemento de enlace para exponer el nuevo elemento de enlace al sistema de configuración.  
  
6.  Agregue las extensiones de metadatos para comunicar las funciones a otros extremos.  
  
7.  Agregue un enlace que configura previamente una pila de elementos de enlace según un perfil bien determinado.Para obtener más información, vea [Adición de un enlace estándar](#AddingAStandardBinding).  
  
8.  Agregue una sección de enlace y un elemento de configuración de enlace para exponer el enlace al sistema de configuración.Para obtener más información, vea [Agregación de la compatibilidad de configuración](#AddingConfigurationSupport).  
  
<a name="MessageExchangePatterns"></a>   
## Modelos de intercambio de mensajes  
 El primer paso a la hora de escribir un transporte personalizado es decidir qué modelos de intercambio de mensajes \(MEP\) son necesarios para el transporte.Hay tres MEP entre los que elegir:  
  
-   Datagrama \(IInputChannel\/IOutputChannel\)  
  
     Al utilizar un MEP de datagrama, un cliente envía un mensaje mediante un intercambio de tipo desencadenar y omitir.Un intercambio de este tipo es uno que exige una confirmación fuera de banda de entrega correcta.El mensaje se podría perderse por el camino y no llegar nunca al servicio.Si la operación de envío se completa correctamente en la parte del cliente, no garantiza que el extremo remoto haya recibido el mensaje.El datagrama es un bloque de creación fundamental para la mensajería, ya que puede crear sus propios protocolos encima de él, incluidos protocolos confiables y seguros.Los canales de datagrama del cliente implementan la interfaz <xref:System.ServiceModel.Channels.IOutputChannel> y los del servicio, la interfaz <xref:System.ServiceModel.Channels.IInputChannel>.  
  
-   Solicitud\-respuesta \(IRequestChannel\/IReplyChannel\)  
  
     En este MEP, un mensaje se envía y se recibe una respuesta.El modelo está compuesto de los pares solicitud\-respuesta.Los ejemplos de llamadas de solicitud\-respuesta son llamadas a procedimiento remoto \(RPC\) y solicitudes GET del explorador.Este modelo también se conoce como "dúplex medio".En este MEP, los canales de cliente implementan <xref:System.ServiceModel.Channels.IRequestChannel> y los canales de servicio <xref:System.ServiceModel.Channels.IReplyChannel>.  
  
-   Dúplex \(IDuplexChannel\)  
  
     El MEP dúplex permite que un cliente envíe un número arbitrario de mensajes y que se reciban en cualquier orden.El MEP dúplex es como una conversación telefónica, donde cada palabra que se pronuncia es un mensaje.Dado que ambos lados pueden enviar y recibir en este MEP, la interfaz implementada por los canales de servicio y cliente es <xref:System.ServiceModel.Channels.IDuplexChannel>.  
  
 Cada uno de estos MEP también puede admitir sesiones.La funcionalidad agregada proporcionada por un canal con reconocimiento de sesión es que pone en correlación todos los mensajes enviados y recibidos en un canal.El modelo de solicitud\-respuesta es una sesión autónoma de dos mensajes, ya que la solicitud y la respuesta se ponen en correlación.Por el contrario, el modelo de solicitud\-respuesta que admite las sesiones implica que se ponen en correlación todos los pares de solicitud\/respuesta en ese canal entre sí.Esto le da un total de seis MEP \(datagrama, solicitud\-respuesta, dúplex, datagrama con sesiones, solicitud\-respuesta con sesiones y dúplex con sesiones\) entre los que elegir.  
  
> [!NOTE]
>  En el caso del transporte de UDP, el único MEP que se admite es el datagrama, ya que UDP es en sí mismo un protocolo de tipo "desencadenar y omitir".  
  
### ICommunicationObject y el ciclo de vida del objeto WCF  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] tiene un equipo de estados común que se utiliza para administrar el ciclo de vida de objetos como <xref:System.ServiceModel.Channels.IChannel>, <xref:System.ServiceModel.Channels.IChannelFactory> y <xref:System.ServiceModel.Channels.IChannelListener> que se utilizan para la comunicación.Hay cinco estados donde estos objetos de comunicación pueden existir.La enumeración <xref:System.ServiceModel.CommunicationState> representa estos estados y son los siguientes:  
  
-   Creado: este es el estado de una interfaz <xref:System.ServiceModel.ICommunicationObject> la primera vez que se crean instancias de ella.No se produce ninguna entrada\/salida \(E\/S\) en este estado.  
  
-   Abriendo: transición de objetos a este estado cuando se llama al método <xref:System.ServiceModel.ICommunicationObject.Open%2A>.En este punto, las propiedades se convierten en inmutables y puede comenzar la entrada\/salida.Esta transición solo es válida desde el estado Creado.  
  
-   Abierto: los objetos pasan a este estado cuando el proceso de apertura se completa.Esta transición solo es válida desde el estado Abriendo.En este punto, se puede usar el objeto para la transferencia.  
  
-   Cerrando: los objetos pasan a este estado cuando se llama al método <xref:System.ServiceModel.ICommunicationObject.Close%2A> para que el apagado sea correcto.Esta transición solo es válida desde el estado Abierto.  
  
-   Cerrado: en este estado, no se pueden utilizar los objetos.En general, aún se puede acceder a la mayoría de la configuración para su inspección pero no se puede producir ninguna comunicación.Este estado es equivalente a eliminarse.  
  
-   Con error: en este estado, se puede tener acceso a los objetos para inspeccionarlos pero no se pueden usar.Cuando se produce un error no recuperable, el objeto pasa a este estado.La única transición válida desde este estado es al estado `Closed`.  
  
 Hay eventos que se desencadenan para cada transición de estado.Se puede llamar al método <xref:System.ServiceModel.ICommunicationObject.Abort%2A> en cualquier momento, lo que provoca que el objeto pase inmediatamente de su estado actual al estado Cerrado.Al llamar <xref:System.ServiceModel.ICommunicationObject.Abort%2A>, se finaliza cualquier trabajo inacabado.  
  
<a name="ChannelAndChannelListener"></a>   
## Generador de canales y agente de escucha de canales  
 El paso siguiente para escribir un transporte personalizado es crear una implementación de <xref:System.ServiceModel.Channels.IChannelFactory> para los canales de cliente y de <xref:System.ServiceModel.Channels.IChannelListener> para los canales de servicio.La capa de canal usa un modelo de generador para crear canales.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona los elementos auxiliares de clase base para este proceso.  
  
-   La clase <xref:System.ServiceModel.Channels.CommunicationObject> implementa <xref:System.ServiceModel.ICommunicationObject> y aplica el equipo de estado descrito previamente en el paso 2.  
  
-   La clase ``<xref:System.ServiceModel.Channels.ChannelManagerBase> implementa <xref:System.ServiceModel.Channels.CommunicationObject> y proporciona una clase base unificada para <xref:System.ServiceModel.Channels.ChannelFactoryBase> y <xref:System.ServiceModel.Channels.ChannelListenerBase>.La clase <xref:System.ServiceModel.Channels.ChannelManagerBase> trabaja junto con <xref:System.ServiceModel.Channels.ChannelBase>, que es una clase base que implementa <xref:System.ServiceModel.Channels.IChannel>.  
  
-   La clase ``<xref:System.ServiceModel.Channels.ChannelFactoryBase> implementa <xref:System.ServiceModel.Channels.ChannelManagerBase> y <xref:System.ServiceModel.Channels.IChannelFactory>, y consolida las sobrecargas de `CreateChannel` en un método abstracto `OnCreateChannel`.  
  
-   La clase <xref:System.ServiceModel.Channels.ChannelListenerBase> implementa la interfaz <xref:System.ServiceModel.Channels.IChannelListener>.Se encarga de la administración de estados básica.  
  
 En este ejemplo, la implementación del generador se encuentra en UdpChannelFactory.cs y la implementación del agente de escucha se encuentra en UdpChannelListener.cs.Las implementaciones <xref:System.ServiceModel.Channels.IChannel> están en UdpOutputChannel.cs y UdpInputChannel.cs.  
  
### Generador de canales UDP  
 La clase `UdpChannelFactory` se deriva de la clase <xref:System.ServiceModel.Channels.ChannelFactoryBase>.El ejemplo invalida <xref:System.ServiceModel.Channels.ChannelFactoryBase.GetProperty%2A> para proporcionar acceso a la versión del mensaje del codificador de mensajes.El ejemplo también invalida <xref:System.ServiceModel.Channels.ChannelFactoryBase.OnClose%2A> de manera que podamos anular nuestra instancia de <xref:System.ServiceModel.Channels.BufferManager> cuando se realizan las transiciones del equipo de estado.  
  
#### Canal de salida UDP  
 La clase `UdpOutputChannel` implementa la interfaz <xref:System.ServiceModel.Channels.IOutputChannel>.El constructor valida los argumentos y construye un objeto de destino <xref:System.Net.EndPoint> basado en <xref:System.ServiceModel.EndpointAddress> en la que se pasa.  
  
```  
this.socket = new Socket(this.remoteEndPoint.AddressFamily, SocketType.Dgram, ProtocolType.Udp);  
  
```  
  
 El canal puede cerrarse de forma correcta o incorrecta.Si el canal se cierra correctamente, el socket se cierra y se realiza una llamada al método `OnClose` de la clase base.Si se inicia una excepción, la infraestructura llama a `Abort` para garantizar que se limpia el canal.  
  
```  
this.socket.Close(0);  
  
```  
  
 Implementamos a continuación `Send()` y `BeginSend()`\/`EndSend()`.De este modo se divide en dos secciones principales.Primero se serializa el mensaje en una matriz de bytes.  
  
```  
ArraySegment<byte> messageBuffer = EncodeMessage(message);  
  
```  
  
 A continuación, se envían los datos resultantes en la conexión.  
  
```  
this.socket.SendTo(messageBuffer.Array, messageBuffer.Offset, messageBuffer.Count, SocketFlags.None, this.remoteEndPoint);  
```  
  
### UdpChannelListener  
 El``UdpChannelListener que implementa el ejemplo se deriva de la clase <xref:System.ServiceModel.Channels.ChannelListenerBase>.Utiliza un socket UDP único para recibir datagramas.El método `OnOpen` recibe datos utilizando el socket UDP en un bucle asincrónico.Los datos se convierten en mensajes utilizando el marco de trabajo de codificación de mensajes:  
  
```  
message = MessageEncoderFactory.Encoder.ReadMessage(new ArraySegment<byte>(buffer, 0, count), bufferManager);  
```  
  
 Dado que el mismo canal del datagrama representa mensajes que llegan de varios orígenes, `UdpChannelListener` es un agente de escucha singleton.Hay a lo sumo un <xref:System.ServiceModel.Channels.IChannel>``activo asociado a la vez a este agente de escucha.El ejemplo solo genera otro si se elimina a continuación un canal que es devuelto por el método `AcceptChannel`.Cuando se recibe un mensaje, se pone en cola en este canal singleton.  
  
#### UdpInputChannel  
 La clase `UdpInputChannel` implementa la interfaz `IInputChannel`.Está compuesto de una cola de mensajes entrantes que es rellenada por el socket de `UdpChannelListener`.Estos mensajes se quitan de la cola mediante el método `IInputChannel.Receive```.  
  
<a name="AddingABindingElement"></a>   
## Adición de un elemento de enlace  
 Ahora que se han creado los generadores y canales, se deben exponer en el tiempo de ejecución de ServiceModel mediante un enlace.Un enlace es una colección de elementos de enlace que representa la pila de comunicación asociada con una dirección de servicio.Un elemento de enlace está representado por un elemento de [\<enlace\>](../../../../docs/framework/misc/binding.md).  
  
 En el ejemplo, el elemento de enlace es `UdpTransportBindingElement`, que deriva de <xref:System.ServiceModel.Channels.TransportBindingElement>.Invalida los métodos siguientes para crear los generadores asociados con el enlace.  
  
```  
public IChannelFactory<TChannel> BuildChannelFactory<TChannel>(BindingContext context)  
{  
            return (IChannelFactory<TChannel>)(object)new UdpChannelFactory(this, context);  
}  
  
public IChannelListener<TChannel> BuildChannelListener<TChannel>(BindingContext context)  
{  
            return (IChannelListener<TChannel>)(object)new UdpChannelListener(this, context);  
}  
```  
  
 También contiene los miembros para clonar `BindingElement` y devolver nuestro esquema \(soap.udp\).  
  
## Agregación de compatibilidad con metadatos para un elemento de enlace de transporte  
 Para integrar nuestro transporte en el sistema de metadatos, debe admitir la importación y exportación de la directiva.Esto nos permite generar clientes de nuestro enlace a través de [Herramienta de utilidad de metadatos de ServiceModel \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
### Agregación de la compatibilidad con WSDL  
 El elemento de enlace del transporte en un enlace es el responsable de la exportación e importación de la información de direccionamiento en metadatos.Al utilizar un enlace SOAP, el elemento de enlace del transporte también debería exportar un URI de transporte correcto en los metadatos.  
  
#### Exportación de WSDL  
 Para exportar información de direccionamiento, `UdpTransportBindingElement` implementa la interfaz `IWsdlExportExtension`.El método `ExportEndpoint` agrega la información de direccionamiento correcta al puerto WSDL.  
  
```  
if (context.WsdlPort != null)  
{  
    AddAddressToWsdlPort(context.WsdlPort, context.Endpoint.Address, encodingBindingElement.MessageVersion.Addressing);  
}  
```  
  
 La implementación `UdpTransportBindingElement` del método `ExportEndpoint` también exporta un URI de transporte cuando el extremo utiliza un enlace SOAP.  
  
```  
WsdlNS.SoapBinding soapBinding = GetSoapBinding(context, exporter);  
if (soapBinding != null)  
{  
    soapBinding.Transport = UdpPolicyStrings.UdpNamespace;  
}  
```  
  
#### Importación de WSDL  
 Para extender el sistema de importación de WSDL para que administre la importación de direcciones, debemos agregar la configuración siguiente al archivo de configuración para Svcutil.exe, tal y como se muestra en el archivo Svcutil.exe.config:  
  
```  
<configuration>  
  <system.serviceModel>  
    <client>  
      <metadata>  
        <wsdlImporters>  
          <extension type=" Microsoft.ServiceModel.Samples.UdpBindingElementImporter, UdpTransport" />  
        </policyImporters>  
      </metadata>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
 Al ejecutar Svcutil.exe, hay dos opciones para conseguir que Svcutil.exe cargue las extensiones de importación de WSDL:  
  
1.  Señale Svcutil.exe a nuestro archivo de configuración utilizando el \/SvcutilConfig:\<archivo\>.  
  
2.  Agregue la sección de configuración a Svcutil.exe.config en el mismo directorio como Svcutil.exe.  
  
 El tipo `UdpBindingElementImporter` implementa la interfaz `IWsdlImportExtension`.El método `ImportEndpoint` importa la dirección del puerto WSDL.  
  
```  
BindingElementCollection bindingElements = context.Endpoint.Binding.CreateBindingElements();  
TransportBindingElement transportBindingElement = bindingElements.Find<TransportBindingElement>();  
if (transportBindingElement is UdpTransportBindingElement)  
{  
    ImportAddress(context);  
}  
```  
  
### Agregación de compatibilidad de directiva  
 El elemento de enlace personalizado puede exportar aserciones de directiva en el enlace de WSDL para que un extremo de servicio exprese las funciones de ese elemento de enlace.  
  
#### Exportación de directivas  
 El tipo `UdpTransportBindingElement` implementa```IPolicyExportExtension` para agregar la compatibilidad para la exportación de la directiva.Como resultado, `System.ServiceModel.MetadataExporter` incluye `UdpTransportBindingElement` en la generación de directiva para cualquier enlace que la incluya.  
  
 En `IPolicyExportExtension.ExportPolicy`, agregamos una aserción para UDP y otra si estamos en modo de multidifusión.Esto se debe a que el modo de multidifusión afecta a cómo se construye la pila de comunicaciones, y, por tanto, debe coordinarse entre ambos lados.  
  
```  
ICollection<XmlElement> bindingAssertions = context.GetBindingAssertions();  
XmlDocument xmlDocument = new XmlDocument();  
bindingAssertions.Add(xmlDocument.CreateElement(  
UdpPolicyStrings.Prefix, UdpPolicyStrings.TransportAssertion, UdpPolicyStrings.UdpNamespace));  
if (Multicast)  
{  
    bindingAssertions.Add(xmlDocument.CreateElement(  
UdpPolicyStrings.Prefix, UdpPolicyStrings.MulticastAssertion,     UdpPolicyStrings.UdpNamespace));  
}  
```  
  
 Dado que los elementos de enlace de transporte personalizados son responsables de la administración del direccionamiento, la implementación `IPolicyExportExtension` en el `UdpTransportBindingElement` también debe administrar la exportación de las aserciones de directivas WS\-Addressing adecuadas para indicar la versión de WS\-Addressing que se está utilizando.  
  
```  
AddWSAddressingAssertion(context, encodingBindingElement.MessageVersion.Addressing);  
```  
  
#### Importación de directivas  
 Para extender el sistema de importación de directivas, debe agregar la siguiente configuración al archivo de configuración para Svcutil.exe tal y como se muestra en el archivo Svcutil.exe.config.  
  
```  
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
  
 A continuación, implementamos `IPolicyImporterExtension` desde nuestra clase registrada \(`UdpBindingElementImporter`\).En `ImportPolicy()`, examinamos las aserciones en nuestro espacio de nombres y procesamos las que se encargan de la generación del transporte y de la comprobación de si es multidifusión.También debemos quitar las aserciones que administramos de la lista de aserciones de enlace.De nuevo, al ejecutar Svcutil.exe, hay dos opciones para la integración:  
  
1.  Señale Svcutil.exe a nuestro archivo de configuración utilizando \/SvcutilConfig:\<file\>.  
  
2.  Agregue la sección de configuración a Svcutil.exe.config en el mismo directorio como Svcutil.exe.  
  
<a name="AddingAStandardBinding"></a>   
## Adición de un enlace estándar  
 Nuestro elemento de enlace se puede utilizar de las dos maneras siguientes:  
  
-   A través de un enlace personalizado: un enlace personalizado permite al usuario crear su propio enlace basado en un conjunto arbitrario de elementos de enlace.  
  
-   Usando un enlace proporcionado por el sistema que incluye nuestro elemento de enlace.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona varios de estos enlaces definidos por el sistema, como `BasicHttpBinding`, `NetTcpBinding` y `WsHttpBinding`.Cada uno de estos enlaces está asociado a un perfil bien definido.  
  
 El ejemplo implementa el enlace del perfil en `SampleProfileUdpBinding`, que deriva de <xref:System.ServiceModel.Channels.Binding>.`SampleProfileUdpBinding` contiene hasta cuatro elementos de enlace dentro de él: `UdpTransportBindingElement`, `TextMessageEncodingBindingElement CompositeDuplexBindingElement` y `ReliableSessionBindingElement`.  
  
```  
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
  
### Agregación de un importador de enlace estándar personalizado  
 Svcutil.exe y el tipo `WsdlImporter`, de forma predeterminada, reconocen e importan los enlaces definidos por el sistema.De lo contrario, el enlace se importa como una instancia `CustomBinding`.Para permitir que Svcutil.exe y `WsdlImporter` importen el `SampleProfileUdpBinding`, el `UdpBindingElementImporter` actúa también como un importador de enlaces estándar personalizado.  
  
 Un importador de este tipo implementa el método `ImportEndpoint` en la interfaz `IWsdlImportExtension` para examinar la instancia `CustomBinding` importada desde los metadatos para ver si el enlace estándar concreto podría haberla generado.  
  
```  
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
  
 Generalmente, la implementación de un importador de enlaces estándar personalizado, implica la comprobación de las propiedades de los elementos de enlace importados para comprobar que solo las propiedades que pudo establecer el enlace estándar han cambiado y el resto propiedades son sus valores predeterminados.Una estrategia básica para implementar un importador de enlace estándar consiste en crear una instancia de enlace estándar, propagar las propiedades desde los elementos de enlace a la instancia de enlace estándar que admite enlaces estándar y, a continuación, comparar los elementos de enlace desde el enlace estándar con los elementos de enlace importados.  
  
<a name="AddingConfigurationSupport"></a>   
## Agregación de la compatibilidad de configuración  
 Para exponer nuestro transporte a través de la configuración, debemos implementar dos secciones de configuración.El primero es `BindingElementExtensionElement` para `UdpTransportBindingElement`.Esto es para que las implementaciones de `CustomBinding` puedan hacer referencia a nuestro elemento de enlace.El segundo es `Configuration` para `SampleProfileUdpBinding`.  
  
### Elemento de extensión de elemento de enlace  
 La sección`````UdpTransportElement` es un `BindingElementExtensionElement` que expone `UdpTransportBindingElement` en el sistema de configuración.Con algunas invalidaciones básicas, definimos el nombre de la sección de configuración, el tipo del elemento de enlace y cómo crear el elemento de enlace.Podemos registrar a continuación como se muestra nuestra sección de extensión en un archivo de configuración en el código siguiente.  
  
```  
<configuration>  
  \<system.serviceModel>  
    <extensions>  
      <bindingElementExtensions>  
      \<add name="udpTransport" type="Microsoft.ServiceModel.Samples.UdpTransportElement, UdpTransport />  
      </bindingElementExtensions>  
    </extensions>  
  \</system.serviceModel>  
</configuration>  
  
```  
  
 Se puede hacer referencia a la extensión desde enlaces personalizados para utilizar UDP como el transporte.  
  
```  
<configuration>  
  \<system.serviceModel>  
    <bindings>  
      <customBinding>  
       <binding configurationName="UdpCustomBinding">  
         <udpTransport/>  
       </binding>  
      </customBinding>  
    </bindings>  
  \</system.serviceModel>  
</configuration>  
  
```  
  
### Sección de enlace  
 La sección `SampleProfileUdpBindingCollectionElement` es un objeto `StandardBindingCollectionElement` que expone `SampleProfileUdpBinding` en el sistema de configuración.El volumen de la implementación se delega a `SampleProfileUdpBindingConfigurationElement`, que deriva de `StandardBindingElement`.El `SampleProfileUdpBindingConfigurationElement` tiene propiedades que se corresponden con las propiedades en `SampleProfileUdpBinding` y funciones que asignar desde el enlace `ConfigurationElement` .Finalmente, se invalida el método `OnApplyConfiguration` en nuestro `SampleProfileUdpBinding`, tal y como se muestra en el siguiente código muestra.  
  
```  
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
  
```  
<configuration>  
  <configSections>  
     <sectionGroup name="system.serviceModel">  
         <sectionGroup name="bindings">  
                 \<section name="sampleProfileUdpBinding" type="Microsoft.ServiceModel.Samples.SampleProfileUdpBindingCollectionElement, UdpTransport />  
         </sectionGroup>  
     </sectionGroup>  
  </configSections>  
</configuration>  
```  
  
 A continuación, se puede establecer la referencia desde la sección de configuración serviceModel.  
  
```  
<configuration>  
  \<system.serviceModel>  
    <client>  
      <endpoint configurationName="calculator"  
                address="soap.udp://localhost:8001/"   
                bindingConfiguration="CalculatorServer"  
                binding="sampleProfileUdpBinding"   
                contract= "Microsoft.ServiceModel.Samples.ICalculatorContract">  
      </endpoint>  
    </client>  
  \</system.serviceModel>  
</configuration>  
```  
  
## Servicio de pruebas y cliente UDP  
 El código de prueba para usar este transporte de ejemplo está disponible en los directorios UdpTestService y UdpTestClient.El código de servicio está compuesto de dos pruebas: una configura los enlaces y extremos desde el código y la otra lo hace a través de la configuración.Ambas pruebas utilizan dos extremos.Un extremo utiliza `SampleUdpProfileBinding` con [\<reliableSession\>](http://msdn.microsoft.com/es-es/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b) establecido en `true`.El otro extremo utiliza un enlace personalizado con `UdpTransportBindingElement`.Esto es equivalente a utilizar `SampleUdpProfileBinding` con [\<reliableSession\>](http://msdn.microsoft.com/es-es/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b) establecido en `false`.Ambas pruebas crean un servicio, agregan un extremo para cada enlace, abren el servicio y, a continuación, esperan a que el usuario presione ENTRAR antes de cerrar el servicio.  
  
 Al iniciar la aplicación de prueba del servicio, debería ver el resultado siguiente.  
  
```  
Testing Udp From Code.  
Service is started from code...  
Press <ENTER> to terminate the service and start service from config...  
```  
  
 Puede ejecutar a continuación la aplicación cliente de prueba con los extremos publicados.La aplicación de prueba del cliente crea un cliente para cada extremo y envía cinco mensajes a cada extremo.El resultado siguiente se encuentra en el cliente.  
  
```  
Testing Udp From Imported Files Generated By SvcUtil.  
0  
3  
6  
9  
12  
Press <ENTER> to complete test.  
```  
  
 A continuación, se muestra el resultado completo en el servicio.  
  
```  
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
  
 Para ejecutar la aplicación cliente en los extremos publicados utilizando la configuración, presione ENTRAR en el servicio y después ejecute de nuevo el cliente de prueba.Debería ver el siguiente resultado en el servicio.  
  
```  
Testing Udp From Config.  
Service is started from config...  
Press <ENTER> to terminate the service and exit...  
```  
  
 Ejecutar de nuevo el cliente produce lo mismo que los resultados anteriores.  
  
 Para regenerar el código de cliente y la configuración utilizando Svcutil.exe, inicie la aplicación de servicio y, a continuación, ejecute Svcutil.exe siguiente desde el directorio raíz del ejemplo.  
  
```  
svcutil http://localhost:8000/udpsample/ /reference:UdpTranport\bin\UdpTransport.dll /svcutilConfig:svcutil.exe.config  
```  
  
 Observe que Svcutil.exe no genera la configuración de extensión de enlace para `SampleProfileUdpBinding`, por lo que deberá agregarla manualmente.  
  
```  
<configuration>  
    \<system.serviceModel>      
        …  
        <extensions>  
            \<!-- This was added manually because svcutil.exe does not add this extension to the file -->  
            <bindingExtensions>  
                <add name="sampleProfileUdpBinding" type="Microsoft.ServiceModel.Samples.SampleProfileUdpBindingCollectionElement, UdpTransport" />  
            </bindingExtensions>  
        </extensions>  
    \</system.serviceModel>  
</configuration>  
```  
  
#### Para configurar, compilar y ejecutar el ejemplo  
  
1.  Para compilar la solución, siga las instrucciones de [Compilación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
2.  Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [Ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
3.  Vea la sección anterior "Servicio de pruebas y cliente UDP".  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Extensibility\Transport\Udp`  
  
## Vea también