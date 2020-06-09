---
title: HttpCookieSession
ms.date: 03/30/2017
ms.assetid: 101cb624-8303-448a-a3af-933247c1e109
ms.openlocfilehash: 8dba147ace7ada221b5d274cd233e4b9618835d9
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84585135"
---
# <a name="httpcookiesession"></a><span data-ttu-id="3e18b-102">HttpCookieSession</span><span class="sxs-lookup"><span data-stu-id="3e18b-102">HttpCookieSession</span></span>
<span data-ttu-id="3e18b-103">Este ejemplo muestra cómo generar un canal de protocolo personalizado para usar cookies de HTTP para la administración de sesiones.</span><span class="sxs-lookup"><span data-stu-id="3e18b-103">This sample demonstrates how to build a custom protocol channel to use HTTP cookies for session management.</span></span> <span data-ttu-id="3e18b-104">Este canal permite la comunicación entre los servicios de Windows Communication Foundation (WCF) y los clientes ASMX o entre los clientes de WCF y los servicios ASMX.</span><span class="sxs-lookup"><span data-stu-id="3e18b-104">This channel enables communication between Windows Communication Foundation (WCF) services and ASMX clients or between WCF clients and ASMX services.</span></span>  
  
 <span data-ttu-id="3e18b-105">Cuando un cliente llama a un método Web en un servicio Web ASMX basado en sesión, el motor ASP.NET realiza lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3e18b-105">When a client calls a Web method in an ASMX Web service that is session-based, the ASP.NET engine does the following:</span></span>  
  
- <span data-ttu-id="3e18b-106">Genera un id. único (id. de sesión).</span><span class="sxs-lookup"><span data-stu-id="3e18b-106">Generates a unique ID (session ID).</span></span>  
  
- <span data-ttu-id="3e18b-107">Genera el objeto de sesión y lo asocia con el id. único.</span><span class="sxs-lookup"><span data-stu-id="3e18b-107">Generates the session object and associates it with the unique ID.</span></span>  
  
- <span data-ttu-id="3e18b-108">Agrega el id. único a un encabezado de respuesta HTTP Set-Cookie y lo envía al cliente.</span><span class="sxs-lookup"><span data-stu-id="3e18b-108">Adds the unique ID to a Set-Cookie HTTP response header and sends it to the client.</span></span>  
  
- <span data-ttu-id="3e18b-109">Identifica el cliente en las llamadas subsiguientes basadas en el id. de sesión que lo envía.</span><span class="sxs-lookup"><span data-stu-id="3e18b-109">Identifies the client on subsequent calls based on the session ID it sends to it.</span></span>  
  
 <span data-ttu-id="3e18b-110">El cliente incluye este id. de sesión en sus solicitudes subsiguientes al servidor.</span><span class="sxs-lookup"><span data-stu-id="3e18b-110">The client includes this session ID in its subsequent requests to the server.</span></span> <span data-ttu-id="3e18b-111">El servidor utiliza el identificador de sesión del cliente para cargar el objeto de sesión adecuado para el contexto de HTTP actual.</span><span class="sxs-lookup"><span data-stu-id="3e18b-111">The server uses the session ID from the client to load the appropriate session object for the current HTTP context.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3e18b-112">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="3e18b-112">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3e18b-113">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="3e18b-113">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="3e18b-114">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="3e18b-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3e18b-115">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="3e18b-115">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\HttpCookieSession`  
  
## <a name="httpcookiesession-channel-message-exchange-pattern"></a><span data-ttu-id="3e18b-116">Modelo de intercambio de mensajes de canal de HttpCookieSession</span><span class="sxs-lookup"><span data-stu-id="3e18b-116">HttpCookieSession Channel Message Exchange Pattern</span></span>  
 <span data-ttu-id="3e18b-117">Este ejemplo habilita las sesiones para los escenarios de tipo ASMX.</span><span class="sxs-lookup"><span data-stu-id="3e18b-117">This sample enables sessions for ASMX-like scenarios.</span></span> <span data-ttu-id="3e18b-118">En la parte inferior de nuestra pila de canales, tenemos el transporte HTTP que admite <xref:System.ServiceModel.Channels.IRequestChannel> y <xref:System.ServiceModel.Channels.IReplyChannel>.</span><span class="sxs-lookup"><span data-stu-id="3e18b-118">At the bottom of our channel stack, we have the HTTP transport that supports <xref:System.ServiceModel.Channels.IRequestChannel> and <xref:System.ServiceModel.Channels.IReplyChannel>.</span></span> <span data-ttu-id="3e18b-119">Es trabajo del canal proporcionar sesiones en los niveles más altos de la pila de canales.</span><span class="sxs-lookup"><span data-stu-id="3e18b-119">It is the job of the channel to provide sessions to the higher levels of the channel stack.</span></span> <span data-ttu-id="3e18b-120">El ejemplo implementa dos canales, (<xref:System.ServiceModel.Channels.IRequestSessionChannel> y <xref:System.ServiceModel.Channels.IReplySessionChannel>) que admiten sesiones.</span><span class="sxs-lookup"><span data-stu-id="3e18b-120">The sample implements two channels, (<xref:System.ServiceModel.Channels.IRequestSessionChannel> and <xref:System.ServiceModel.Channels.IReplySessionChannel>) that support sessions.</span></span>  
  
## <a name="service-channel"></a><span data-ttu-id="3e18b-121">Canal de servicio</span><span class="sxs-lookup"><span data-stu-id="3e18b-121">Service Channel</span></span>  
 <span data-ttu-id="3e18b-122">El ejemplo proporciona un canal de servicio en la clase `HttpCookieReplySessionChannelListener`.</span><span class="sxs-lookup"><span data-stu-id="3e18b-122">The sample provides a service channel in the `HttpCookieReplySessionChannelListener` class.</span></span> <span data-ttu-id="3e18b-123">Esta clase implementa la interfaz <xref:System.ServiceModel.Channels.IChannelListener> y convierte el canal <xref:System.ServiceModel.Channels.IReplyChannel> desde la parte inferior de la pila de canales en un <xref:System.ServiceModel.Channels.IReplySessionChannel>.</span><span class="sxs-lookup"><span data-stu-id="3e18b-123">This class implements the <xref:System.ServiceModel.Channels.IChannelListener> interface and converts the <xref:System.ServiceModel.Channels.IReplyChannel> channel from lower in the channel stack to a <xref:System.ServiceModel.Channels.IReplySessionChannel>.</span></span> <span data-ttu-id="3e18b-124">Este proceso puede estar dividido en las partes siguientes:</span><span class="sxs-lookup"><span data-stu-id="3e18b-124">This process can be divided into the following parts:</span></span>  
  
- <span data-ttu-id="3e18b-125">Cuando se abre el agente de escucha del canal, acepta un canal interno desde su agente de escucha interno.</span><span class="sxs-lookup"><span data-stu-id="3e18b-125">When the channel listener is opened, it accepts an inner channel from its inner listener.</span></span> <span data-ttu-id="3e18b-126">Dado que éste es un agente de escucha de datagrama y la duración de un canal aceptado se desacopla de la duración del agente de escucha, podemos cerrar el agente de escucha interno y solo mantener el canal interno</span><span class="sxs-lookup"><span data-stu-id="3e18b-126">Because the inner listener is a datagram listener and the lifetime of an accepted channel is decoupled from the lifetime of the listener, we can close the inner listener and only hold on to the inner channel</span></span>  
  
    ```csharp  
                this.innerChannelListener.Open(timeoutHelper.RemainingTime());  
    this.innerChannel = this.innerChannelListener.AcceptChannel(timeoutHelper.RemainingTime());  
    this.innerChannel.Open(timeoutHelper.RemainingTime());  
    this.innerChannelListener.Close(timeoutHelper.RemainingTime());  
    ```  
  
- <span data-ttu-id="3e18b-127">Cuando el proceso abierto se completa, configuramos un bucle de mensajes para recibirlos desde el canal interno.</span><span class="sxs-lookup"><span data-stu-id="3e18b-127">When the open process completes, we set up a message loop to receive messages from the inner channel.</span></span>  
  
    ```csharp  
    IAsyncResult result = BeginInnerReceiveRequest();  
    if (result != null && result.CompletedSynchronously)  
    {  
       // do not block the user thread  
       this.completeReceiveCallback ??= new WaitCallback(CompleteReceiveCallback);
       ThreadPool.QueueUserWorkItem(this.completeReceiveCallback, result);  
    }  
    ```  
  
- <span data-ttu-id="3e18b-128">Cuando llega un mensaje, el canal del servicio examina el identificador de la sesión y demultiplexa en el canal de sesión adecuado.</span><span class="sxs-lookup"><span data-stu-id="3e18b-128">When a message arrives, the service channel examines the session identifier and de-multiplexes to the appropriate session channel.</span></span> <span data-ttu-id="3e18b-129">El agente de escucha del canal mantiene un diccionario que asigna los identificadores de la sesión a las instancias del canal de sesión.</span><span class="sxs-lookup"><span data-stu-id="3e18b-129">The channel listener maintains a dictionary that maps the session identifiers to the session channel instances.</span></span>  
  
    ```csharp  
    Dictionary<string, IReplySessionChannel> channelMapping;  
    ```  
  
 <span data-ttu-id="3e18b-130">La `HttpCookieReplySessionChannel` clase implementa <xref:System.ServiceModel.Channels.IReplySessionChannel> .</span><span class="sxs-lookup"><span data-stu-id="3e18b-130">The `HttpCookieReplySessionChannel` class implements <xref:System.ServiceModel.Channels.IReplySessionChannel>.</span></span> <span data-ttu-id="3e18b-131">Los niveles más altos de la pila de canales llaman al método <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> para leer las solicitudes de esta sesión.</span><span class="sxs-lookup"><span data-stu-id="3e18b-131">Higher levels of the channel stack call the <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> method to read requests for this session.</span></span> <span data-ttu-id="3e18b-132">Cada canal de la sesión tiene una cola de mensajes privada que el canal de servicio rellena.</span><span class="sxs-lookup"><span data-stu-id="3e18b-132">Each session channel has a private message queue that is populated by the service channel.</span></span>  
  
```csharp  
InputQueue<RequestContext> requestQueue;  
```  
  
 <span data-ttu-id="3e18b-133">En el caso de que alguien llame al método <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> y no haya ningún mensaje en la cola de mensajes, el canal espera un periodo de tiempo especificado antes de apagarse.</span><span class="sxs-lookup"><span data-stu-id="3e18b-133">In the case when someone calls the <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> method and there are no messages in the message queue, the channel waits for a specified amount of time before shutting itself down.</span></span> <span data-ttu-id="3e18b-134">Esto limpia los canales de sesión creados para clientes que no son de WCF.</span><span class="sxs-lookup"><span data-stu-id="3e18b-134">This cleans up the session channels created for non-WCF clients.</span></span>  
  
 <span data-ttu-id="3e18b-135">Utilizamos `channelMapping` para realizar el seguimiento de `ReplySessionChannels` y no cerramos nuestro `innerChannel` subyacente hasta que se hayan cerrado todos los canales aceptados.</span><span class="sxs-lookup"><span data-stu-id="3e18b-135">We use the `channelMapping` to track the `ReplySessionChannels`, and we do not close our underlying `innerChannel` until all the accepted channels have been closed.</span></span> <span data-ttu-id="3e18b-136">De esta manera `HttpCookieReplySessionChannel`, puede existir más allá de la duración de `HttpCookieReplySessionChannelListener`.</span><span class="sxs-lookup"><span data-stu-id="3e18b-136">This way `HttpCookieReplySessionChannel` can exist beyond the lifetime of `HttpCookieReplySessionChannelListener`.</span></span> <span data-ttu-id="3e18b-137">Además, no nos tenemos que preocupar por el hecho de que el agente de escucha recopile elementos no utilizados debajo de nosotros porque los canales aceptados mantienen una referencia para su agente de escucha mediante la devolución de llamada `OnClosed`.</span><span class="sxs-lookup"><span data-stu-id="3e18b-137">We also do not have to worry about the listener getting garbage collected underneath us because the accepted channels keep a reference to their listener through the `OnClosed` callback.</span></span>  
  
## <a name="client-channel"></a><span data-ttu-id="3e18b-138">Canal del cliente</span><span class="sxs-lookup"><span data-stu-id="3e18b-138">Client channel</span></span>  
 <span data-ttu-id="3e18b-139">El canal de cliente correspondiente está en la clase `HttpCookieSessionChannelFactory`.</span><span class="sxs-lookup"><span data-stu-id="3e18b-139">The corresponding client channel is in the `HttpCookieSessionChannelFactory` class.</span></span> <span data-ttu-id="3e18b-140">Durante la creación del canal, el generador de canales ajusta el canal de solicitud interno con `HttpCookieRequestSessionChannel`.</span><span class="sxs-lookup"><span data-stu-id="3e18b-140">During channel creation, the channel factory wraps the inner request channel with an `HttpCookieRequestSessionChannel`.</span></span> <span data-ttu-id="3e18b-141">La clase `HttpCookieRequestSessionChannel` reenvía las llamadas al canal de solicitud subyacente.</span><span class="sxs-lookup"><span data-stu-id="3e18b-141">The `HttpCookieRequestSessionChannel` class forwards the calls to the underlying request channel.</span></span> <span data-ttu-id="3e18b-142">Cuando el cliente cierra el proxy, `HttpCookieRequestSessionChannel` envía un mensaje al servicio que indica que se cierra el canal.</span><span class="sxs-lookup"><span data-stu-id="3e18b-142">When the client closes the proxy, `HttpCookieRequestSessionChannel` sends a message to the service that indicates that the channel is being closed.</span></span> <span data-ttu-id="3e18b-143">Así, la pila del canal del servicio puede apagar correctamente el canal de la sesión que está en uso.</span><span class="sxs-lookup"><span data-stu-id="3e18b-143">Thus, the service channel stack can gracefully shutdown the session channel that is in use.</span></span>  
  
## <a name="binding-and-binding-element"></a><span data-ttu-id="3e18b-144">Enlace y elemento de enlace</span><span class="sxs-lookup"><span data-stu-id="3e18b-144">Binding and Binding Element</span></span>  
 <span data-ttu-id="3e18b-145">Después de crear los canales de servicio y cliente, el paso siguiente consiste en integrarlos en el tiempo de ejecución de WCF.</span><span class="sxs-lookup"><span data-stu-id="3e18b-145">After creating the service and client channels, the next step is to integrate them into the WCF runtime.</span></span> <span data-ttu-id="3e18b-146">Los canales se exponen a WCF a través de enlaces y elementos de enlace.</span><span class="sxs-lookup"><span data-stu-id="3e18b-146">Channels are exposed to WCF through bindings and binding elements.</span></span> <span data-ttu-id="3e18b-147">Un enlace consta de uno o varios elementos de enlace.</span><span class="sxs-lookup"><span data-stu-id="3e18b-147">A binding consists of one or many binding elements.</span></span> <span data-ttu-id="3e18b-148">WCF ofrece varios enlaces definidos por el sistema; por ejemplo, BasicHttpBinding o WSHttpBinding.</span><span class="sxs-lookup"><span data-stu-id="3e18b-148">WCF offers several system-defined bindings; for example, BasicHttpBinding or WSHttpBinding.</span></span> <span data-ttu-id="3e18b-149">La clase `HttpCookieSessionBindingElement` contiene la implementación para el elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="3e18b-149">The `HttpCookieSessionBindingElement` class contains the implementation for the binding element.</span></span> <span data-ttu-id="3e18b-150">Invalida el agente de escucha del canal y los métodos de creación del generador de canales para crear las instancias del agente de escucha del canal y el generador de canales necesarios.</span><span class="sxs-lookup"><span data-stu-id="3e18b-150">It overrides the channel listener and channel factory creation methods to do the necessary channel listener or channel factory instantiations.</span></span>  
  
 <span data-ttu-id="3e18b-151">El ejemplo utiliza las aserciones de directiva para la descripción del servicio.</span><span class="sxs-lookup"><span data-stu-id="3e18b-151">The sample uses policy assertions for the service description.</span></span> <span data-ttu-id="3e18b-152">Esto permite al ejemplo publicar sus requisitos de canal en otros clientes que pueden utilizar el servicio.</span><span class="sxs-lookup"><span data-stu-id="3e18b-152">This allows the sample to publish its channel requirements to other clients that can consume the service.</span></span> <span data-ttu-id="3e18b-153">Por ejemplo, este elemento de enlace publica las aserciones de directiva para que los clientes potenciales sepan que admite sesiones.</span><span class="sxs-lookup"><span data-stu-id="3e18b-153">For example, this binding element publishes policy assertions to let potential clients know that it supports sessions.</span></span> <span data-ttu-id="3e18b-154">Dado que el ejemplo habilita la propiedad `ExchangeTerminateMessage` en la configuración del elemento de enlace, agrega las aserciones necesarias para mostrar que el servicio admite una acción de intercambio de mensajes adicional para finalizar la conversación de la sesión.</span><span class="sxs-lookup"><span data-stu-id="3e18b-154">Because the sample enables the `ExchangeTerminateMessage` property in the binding element configuration, it adds the necessary assertions to show that the service supports an extra message exchange action to terminate the session conversation.</span></span> <span data-ttu-id="3e18b-155">Los clientes pueden utilizar a continuación esta acción.</span><span class="sxs-lookup"><span data-stu-id="3e18b-155">Clients can then use this action.</span></span> <span data-ttu-id="3e18b-156">El código WSDL siguiente muestra las aserciones de directiva creadas a partir de `HttpCookieSessionBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="3e18b-156">The following WSDL code shows the policy assertions created from the `HttpCookieSessionBindingElement`.</span></span>  
  
```xml  
<wsp:Policy wsu:Id="HttpCookieSessionBinding_IWcfCookieSessionService_policy" xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy" xmlns:wsu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
<wsp:ExactlyOne>  
<wsp:All>  
<wspe:Utf816FFFECharacterEncoding xmlns:wspe="http://schemas.xmlsoap.org/ws/2004/09/policy/encoding"/>  
<mhsc:httpSessionCookie xmlns:mhsc="http://samples.microsoft.com/wcf/mhsc/policy"/>  
</wsp:All>  
</wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="3e18b-157">La clase `HttpCookieSessionBinding` es un enlace proporcionado por el sistema que utiliza el elemento de enlace descrito previamente.</span><span class="sxs-lookup"><span data-stu-id="3e18b-157">The `HttpCookieSessionBinding` class is a system-provided binding that uses the binding element described previously.</span></span>  
  
## <a name="adding-the-channel-to-the-configuration-system"></a><span data-ttu-id="3e18b-158">Adición del canal al sistema de configuración</span><span class="sxs-lookup"><span data-stu-id="3e18b-158">Adding the Channel to the Configuration System</span></span>  
 <span data-ttu-id="3e18b-159">El ejemplo proporciona dos clases que exponen el canal del ejemplo a través de la configuración.</span><span class="sxs-lookup"><span data-stu-id="3e18b-159">The sample provides two classes that expose the sample channel through configuration.</span></span> <span data-ttu-id="3e18b-160">El primero es <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> para `HttpCookieSessionBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="3e18b-160">The first is a <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> for the `HttpCookieSessionBindingElement`.</span></span> <span data-ttu-id="3e18b-161">El volumen de la implementación se delega a `HttpCookieSessionBindingConfigurationElement`, que deriva de <xref:System.ServiceModel.Configuration.StandardBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="3e18b-161">The bulk of the implementation is delegated to the `HttpCookieSessionBindingConfigurationElement`, which derives from <xref:System.ServiceModel.Configuration.StandardBindingElement>.</span></span> <span data-ttu-id="3e18b-162">`HttpCookieSessionBindingConfigurationElement` tiene propiedades que se corresponden con las propiedades en `HttpCookieSessionBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="3e18b-162">The `HttpCookieSessionBindingConfigurationElement` has properties that correspond to the properties on `HttpCookieSessionBindingElement`.</span></span>  
  
### <a name="binding-element-extension-section"></a><span data-ttu-id="3e18b-163">Sección de extensión de elemento de enlace</span><span class="sxs-lookup"><span data-stu-id="3e18b-163">Binding Element Extension Section</span></span>  
 <span data-ttu-id="3e18b-164">La sección `HttpCookieSessionBindingElementSection` es un objeto <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> que expone `HttpCookieSessionBindingElement` en el sistema de configuración.</span><span class="sxs-lookup"><span data-stu-id="3e18b-164">The section `HttpCookieSessionBindingElementSection` is a <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> that exposes `HttpCookieSessionBindingElement` to the configuration system.</span></span> <span data-ttu-id="3e18b-165">Con algunas invalidaciones se define el nombre de la sección de configuración, el tipo del elemento de enlace y cómo crear el elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="3e18b-165">With a few overrides the configuration section name, the type of the binding element and how to create the binding element are defined.</span></span> <span data-ttu-id="3e18b-166">Podemos registrar a continuación la sección de extensión en un archivo de configuración de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="3e18b-166">We can then register the extension section in a configuration file as follows:</span></span>  
  
```xml  
<configuration>
    <system.serviceModel>
      <extensions>
        <bindingElementExtensions>
          <add name="httpCookieSession"
               type=  
"Microsoft.ServiceModel.Samples.HttpCookieSessionBindingElementElement,
                    HttpCookieSessionExtension, Version=1.0.0.0,
                    Culture=neutral, PublicKeyToken=null"/>  
        </bindingElementExtensions >  
      </extensions>  
  
      <bindings>  
      <customBinding>  
        <binding name="allowCookiesBinding">  
          <textMessageEncoding messageVersion="Soap11WSAddressing10" />  
          <httpCookieSession sessionTimeout="10" exchangeTerminateMessage="true" />  
          <httpTransport allowCookies="true" />  
        </binding>  
      </customBinding>  
      </bindings>
    </system.serviceModel>
</configuration>  
```  
  
## <a name="test-code"></a><span data-ttu-id="3e18b-167">Código de prueba</span><span class="sxs-lookup"><span data-stu-id="3e18b-167">Test Code</span></span>  
 <span data-ttu-id="3e18b-168">El código de prueba para utilizar este transporte del ejemplo está disponible en los directorios de cliente y servicio.</span><span class="sxs-lookup"><span data-stu-id="3e18b-168">Test code for using this sample transport is available in the Client and Service directories.</span></span> <span data-ttu-id="3e18b-169">Consta de dos pruebas: una prueba usa un enlace con `allowCookies` establecido en `true` en el cliente.</span><span class="sxs-lookup"><span data-stu-id="3e18b-169">It consists of two tests—one test uses a binding with `allowCookies` set to `true` on the client.</span></span> <span data-ttu-id="3e18b-170">La segunda prueba habilita el apagado explícito (utilizando el intercambio de mensajes de finalización) en el enlace.</span><span class="sxs-lookup"><span data-stu-id="3e18b-170">The second test enables explicit shutdown (using the terminate message exchange) on the binding.</span></span>  
  
 <span data-ttu-id="3e18b-171">Al ejecutar el ejemplo, deberá ver el resultado siguiente:</span><span class="sxs-lookup"><span data-stu-id="3e18b-171">When you run the sample, you should see the following output:</span></span>  
  
```console  
Simple binding:  
AddItem(10000,2): ItemCount=2  
AddItem(10550,5): ItemCount=7  
RemoveItem(10550,2): ItemCount=5  
Items  
10000, 2  
10550, 3  
Smart binding:  
AddItem(10000,2): ItemCount=2  
AddItem(10550,5): ItemCount=7  
RemoveItem(10550,2): ItemCount=5  
Items  
10000, 2  
10550, 3  
  
Press <ENTER> to terminate client.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="3e18b-172">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="3e18b-172">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="3e18b-173">Instale ASP.NET 4,0 con el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="3e18b-173">Install ASP.NET 4.0 using the following command.</span></span>  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. <span data-ttu-id="3e18b-174">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3e18b-174">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3. <span data-ttu-id="3e18b-175">Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3e18b-175">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="3e18b-176">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3e18b-176">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
