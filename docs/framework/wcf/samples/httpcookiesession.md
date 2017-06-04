---
title: "HttpCookieSession | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 101cb624-8303-448a-a3af-933247c1e109
caps.latest.revision: 31
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 31
---
# HttpCookieSession
Este ejemplo muestra cómo generar un canal de protocolo personalizado para usar cookies de HTTP para la administración de sesiones.Este canal habilita la comunicación entre los servicios [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y clientes ASMX o entre los clientes [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y servicios ASMX.  
  
 Cuando un cliente llama a un método web en un servicio Web de ASMX que se basa en la sesión, el motor [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] hace lo siguiente:  
  
-   Genera un id. único \(id. de sesión\).  
  
-   Genera el objeto de sesión y lo asocia con el id. único.  
  
-   Agrega el id. único a un encabezado de respuesta HTTP Set\-Cookie y lo envía al cliente.  
  
-   Identifica el cliente en las llamadas subsiguientes basadas en el id. de sesión que lo envía.  
  
 El cliente incluye este id. de sesión en sus solicitudes subsiguientes al servidor.El servidor utiliza el identificador de sesión del cliente para cargar el objeto de sesión adecuado para el contexto de HTTP actual.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Extensibility\Channels\HttpCookieSession`  
  
## Modelo de intercambio de mensajes de canal de HttpCookieSession  
 Este ejemplo habilita las sesiones para los escenarios de tipo ASMX.En la parte inferior de nuestra pila de canales, tenemos el transporte HTTP que admite <xref:System.ServiceModel.Channels.IRequestChannel> y <xref:System.ServiceModel.Channels.IReplyChannel>.Es trabajo del canal proporcionar sesiones en los niveles más altos de la pila de canales.El ejemplo implementa dos canales, \(<xref:System.ServiceModel.Channels.IRequestSessionChannel> y <xref:System.ServiceModel.Channels.IReplySessionChannel>\) que admiten sesiones.  
  
## Canal de servicio  
 El ejemplo proporciona un canal de servicio en la clase `HttpCookieReplySessionChannelListener`.Esta clase implementa la interfaz <xref:System.ServiceModel.Channels.IChannelListener> y convierte el canal <xref:System.ServiceModel.Channels.IReplyChannel> desde la parte inferior de la pila de canales en un <xref:System.ServiceModel.Channels.IReplySessionChannel>.Este proceso puede estar dividido en las partes siguientes:  
  
-   Cuando se abre el agente de escucha del canal, acepta un canal interno desde su agente de escucha interno.Dado que éste es un agente de escucha de datagrama y la duración de un canal aceptado se desacopla de la duración del agente de escucha, podemos cerrar el agente de escucha interno y solo mantener el canal interno  
  
    ```  
                this.innerChannelListener.Open(timeoutHelper.RemainingTime());  
    this.innerChannel = this.innerChannelListener.AcceptChannel(timeoutHelper.RemainingTime());  
    this.innerChannel.Open(timeoutHelper.RemainingTime());  
    this.innerChannelListener.Close(timeoutHelper.RemainingTime());  
    ```  
  
-   Cuando el proceso abierto se completa, configuramos un bucle de mensajes para recibirlos desde el canal interno.  
  
    ```  
    IAsyncResult result = BeginInnerReceiveRequest();  
    if (result != null && result.CompletedSynchronously)  
    {  
       // do not block the user thread  
       if (this.completeReceiveCallback == null)  
       {  
          this.completeReceiveCallback = new WaitCallback(CompleteReceiveCallback);  
       }  
       ThreadPool.QueueUserWorkItem(this.completeReceiveCallback, result);  
    }  
    ```  
  
-   Cuando llega un mensaje, el canal del servicio examina el identificador de la sesión y demultiplexa en el canal de sesión adecuado.El agente de escucha del canal mantiene un diccionario que asigna los identificadores de la sesión a las instancias del canal de sesión.  
  
    ```  
    Dictionary<string, IReplySessionChannel> channelMapping;  
    ```  
  
 La clase `HttpCookieReplySessionChannel` implementa <xref:System.ServiceModel.Channels.IReplySessionChannel>.Los niveles más altos de la pila de canales llaman al método <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> para leer las solicitudes de esta sesión.Cada canal de la sesión tiene una cola de mensajes privada que el canal de servicio rellena.  
  
```  
InputQueue<RequestContext> requestQueue;  
```  
  
 En el caso de que alguien llame al método <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> y no haya ningún mensaje en la cola de mensajes, el canal espera un periodo de tiempo especificado antes de apagarse.Esto limpia los canales de sesión creados para clientes que no sean de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 Utilizamos `channelMapping` para realizar el seguimiento de `ReplySessionChannels` y no cerramos nuestro `innerChannel` subyacente hasta que se hayan cerrado todos los canales aceptados.De esta manera `HttpCookieReplySessionChannel`, puede existir más allá de la duración de `HttpCookieReplySessionChannelListener`.Además, no nos tenemos que preocupar por el hecho de que el agente de escucha recopile elementos no utilizados debajo de nosotros porque los canales aceptados mantienen una referencia para su agente de escucha mediante la devolución de llamada `OnClosed`.  
  
## Canal del cliente  
 El canal de cliente correspondiente está en la clase `HttpCookieSessionChannelFactory`.Durante la creación del canal, el generador de canales ajusta el canal de solicitud interno con `HttpCookieRequestSessionChannel`.La clase `HttpCookieRequestSessionChannel` reenvía las llamadas al canal de solicitud subyacente.Cuando el cliente cierra el proxy, `HttpCookieRequestSessionChannel` envía un mensaje al servicio que indica que se cierra el canal.Así, la pila del canal del servicio puede apagar correctamente el canal de la sesión que está en uso.  
  
## Enlace y elemento de enlace  
 Después de crear los canales de cliente y servicio, el paso siguiente es integrarlos en el tiempo de ejecución de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].Los canales se exponen en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] a través de los enlaces y elementos de enlace.Un enlace consta de uno o varios elementos de enlace.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ofrece varios enlaces definidos por el sistema; por ejemplo, BasicHttpBinding o WSHttpBinding.La clase `HttpCookieSessionBindingElement` contiene la implementación para el elemento de enlace.Invalida el agente de escucha del canal y los métodos de creación del generador de canales para crear las instancias del agente de escucha del canal y el generador de canales necesarios.  
  
 El ejemplo utiliza las aserciones de directiva para la descripción del servicio.Esto permite al ejemplo publicar sus requisitos de canal en otros clientes que pueden utilizar el servicio.Por ejemplo, este elemento de enlace publica las aserciones de directiva para que los clientes potenciales sepan que admite sesiones.Dado que el ejemplo habilita la propiedad `ExchangeTerminateMessage` en la configuración del elemento de enlace, agrega las aserciones necesarias para mostrar que el servicio admite una acción de intercambio de mensajes adicional para finalizar la conversación de la sesión.Los clientes pueden utilizar a continuación esta acción.El código WSDL siguiente muestra las aserciones de directiva creadas a partir de `HttpCookieSessionBindingElement`.  
  
```  
<wsp:Policy wsu:Id="HttpCookieSessionBinding_IWcfCookieSessionService_policy" xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy" xmlns:wsu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
<wsp:ExactlyOne>  
<wsp:All>  
<wspe:Utf816FFFECharacterEncoding xmlns:wspe="http://schemas.xmlsoap.org/ws/2004/09/policy/encoding"/>  
<mhsc:httpSessionCookie xmlns:mhsc="http://samples.microsoft.com/wcf/mhsc/policy"/>  
</wsp:All>  
</wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 La clase `HttpCookieSessionBinding` es un enlace proporcionado por el sistema que utiliza el elemento de enlace descrito previamente.  
  
## Adición del canal al sistema de configuración  
 El ejemplo proporciona dos clases que exponen el canal del ejemplo a través de la configuración.El primero es <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> para `HttpCookieSessionBindingElement`.El volumen de la implementación se delega a `HttpCookieSessionBindingConfigurationElement`, que deriva de <xref:System.ServiceModel.Configuration.StandardBindingElement>.`HttpCookieSessionBindingConfigurationElement` tiene propiedades que se corresponden con las propiedades en `HttpCookieSessionBindingElement`.  
  
### Sección de extensión de elemento de enlace  
 La sección `HttpCookieSessionBindingElementSection` es un <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> que expone `HttpCookieSessionBindingElement` en el sistema de configuración.Con algunas invalidaciones se define el nombre de la sección de configuración, el tipo del elemento de enlace y cómo crear el elemento de enlace.Podemos registrar a continuación la sección de extensión en un archivo de configuración de la siguiente manera:  
  
```  
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
  
## Código de prueba  
 El código de prueba para utilizar este transporte del ejemplo está disponible en los directorios de cliente y servicio.Está compuesto de dos pruebas: una utiliza un enlace con `allowCookies`  establecido en `true` en el cliente.La segunda prueba habilita el apagado explícito \(utilizando el intercambio de mensajes de finalización\) en el enlace.  
  
 Al ejecutar el ejemplo, deberá ver el resultado siguiente:  
  
```  
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
  
#### Para configurar, compilar y ejecutar el ejemplo  
  
1.  Instale [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 mediante el siguiente comando.  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
  
    ```  
  
2.  Asegúrese de realizar los [Procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
3.  Para compilar la solución, siga las instrucciones de [Compilación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4.  Para ejecutar el ejemplo en una configuración con un único equipo o con varios, siga las instrucciones de [Ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## Vea también