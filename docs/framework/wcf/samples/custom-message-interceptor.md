---
title: Interceptador de mensajes personalizados
ms.date: 03/30/2017
ms.assetid: 73f20972-53f8-475a-8bfe-c133bfa225b0
ms.openlocfilehash: 433b14433a7e2dd6edad551a2732e9049a9861ea
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145091"
---
# <a name="custom-message-interceptor"></a>Interceptador de mensajes personalizados
Este ejemplo muestra el uso del modelo de extensibilidad del canal. En particular, muestra cómo implementar un elemento de enlace personalizado que crea generadores de canales y agentes de escucha de canales para interceptar todos los mensajes entrantes y salientes en un punto concreto en la pila de tiempo de ejecución. El ejemplo también incluye un cliente y un servidor que muestran el uso de estos generadores personalizados.  
  
 En este ejemplo, el cliente y el servicio son programas de consola (.exe). El cliente y el servicio hacen uso de una biblioteca común (.dll) que contiene el elemento de enlace personalizado y sus objetos en tiempo de ejecución asociados.  
  
> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\MessageInterceptor`  
  
 En el ejemplo se describe el procedimiento recomendado para crear un canal en capas personalizado en Windows Communication Foundation (WCF), mediante el marco de trabajo de canal y siguiendo los procedimientos recomendados de WCF. Los pasos para crear un canal superpuesto personalizado son los siguientes:  
  
1. Decida cuál de las formas del canal admitirá el generador de canales y el agente de escucha del canal.  
  
2. Cree un generador de canales y un agente de escucha del canal que admita las formas del canal.  
  
3. Agregue un elemento de enlace que añada el canal superpuesto personalizado a una pila de canales.  
  
4. Agregue una sección de extensión de elemento de enlace para exponer el nuevo elemento de enlace al sistema de configuración.  
  
## <a name="channel-shapes"></a>Formas del canal  
 El primer paso para escribir un canal superpuesto personalizado es decidir qué formas son necesarias para el canal. Para nuestro inspector de mensajes, admitimos cualquier forma que admita el nivel debajo de nosotros (por ejemplo, si la capa debajo de nosotros puede compilar <xref:System.ServiceModel.Channels.IOutputChannel> y <xref:System.ServiceModel.Channels.IDuplexSessionChannel>, también exponemos <xref:System.ServiceModel.Channels.IOutputChannel> y <xref:System.ServiceModel.Channels.IDuplexSessionChannel>).  
  
## <a name="channel-factory-and-listener-factory"></a>Generador de canales y de agentes de escucha  
 El paso siguiente para escribir un canal superpuesto personalizado es crear una implementación de <xref:System.ServiceModel.Channels.IChannelFactory> para los canales de cliente y de <xref:System.ServiceModel.Channels.IChannelListener> para los canales de servicio.  
  
 Estas clases escogen un generador y un agente de escucha internos y delegan todas las llamadas excepto `OnCreateChannel` y `OnAcceptChannel` al generador y agente de escucha internos.  
  
```csharp
class InterceptingChannelFactory<TChannel> : ChannelFactoryBase<TChannel>  
{
    //...
}

class InterceptingChannelListener<TChannel> : ListenerFactoryBase<TChannel>  
{
    //...
}  
```  
  
## <a name="adding-a-binding-element"></a>Adición de un elemento de enlace  
 El ejemplo define un elemento de enlace personalizado: `InterceptingBindingElement`. `InterceptingBindingElement`toma `ChannelMessageInterceptor` una como entrada y `ChannelMessageInterceptor` usa esto para manipular los mensajes que pasan a través de él. Ésta es la única clase que debe ser pública. El generador, agente de escucha y canales pueden ser implementaciones internas de las interfaces en tiempo de ejecución públicas.  
  
```csharp
public class InterceptingBindingElement : BindingElement
{
}
```  
  
## <a name="adding-configuration-support"></a>Agregación de la compatibilidad de configuración  
 Para integrar con la configuración de enlace, la biblioteca define un controlador de la sección de configuración como una sección de extensión de elemento de enlace. Los archivos de configuración del servidor y el cliente deben registrar la extensión del elemento de enlace con el sistema de configuración. Los implementadores que desean exponer su elemento de enlace al sistema de configuración pueden derivar de esta clase.  
  
```csharp
public abstract class InterceptingElement : BindingElementExtensionElement
{
    //...
}
```  
  
## <a name="adding-policy"></a>Adición de directivas  
 Para integrar con nuestro sistema de directivas, `InterceptingBindingElement` implementa IPolicyExportExtension para señalar que deberíamos participar en la generación de directivas. Para permitir importar la directiva en un cliente generado, el usuario puede registrar una clase derivada de `InterceptingBindingElementImporter` e invalidar `CreateMessageInterceptor`() para generar su clase `ChannelMessageInterceptor` habilitada por la directiva.  
  
## <a name="example-droppable-message-inspector"></a>Ejemplo: inspector de mensajes que pueden quitarse  
 En este ejemplo se incluye una implementación de ejemplo de `ChannelMessageInspector` que quita mensajes.  
  
```csharp
class DroppingServerElement : InterceptingElement  
{  
    protected override ChannelMessageInterceptor CreateMessageInterceptor()  
    {  
        return new DroppingServerInterceptor();  
    }  
}  
```  
  
 Puede tener acceso a ella desde la configuración de la manera siguiente:  
  
```xml  
<configuration>  
    ...  
    <system.serviceModel>  
        ...  
        <extensions>  
            <bindingElementExtensions>  
                <add name="droppingInterceptor"
                   type=  
          "Microsoft.ServiceModel.Samples.DroppingServerElement, library"/>  
            </bindingElementExtensions>  
        </extensions>  
    </system.serviceModel>  
</configuration>  
```  
  
 El cliente y servidor usan esta sección de configuración que se acaba de crear para insertar los generadores personalizados en el nivel más bajo de sus pilas de canales en el tiempo de ejecución (por encima del nivel de transporte).  
  
```xml  
<customBinding>  
  <binding name="sampleBinding">  
    <droppingInterceptor/>  
    <httpTransport/>  
  </binding>  
</customBinding>  
```  
  
 El cliente utiliza la biblioteca `MessageInterceptor` para agregar un encabezado personalizado a mensajes con número par. Por otra parte, el servicio utiliza la biblioteca `MessageInterceptor` para colocar cualquier mensaje que no tenga este encabezado especial.  
  
 Debería ver el siguiente resultado del cliente después de ejecutar primero el servicio y después el cliente.  
  
```console  
Reporting the next 10 wind speed  
100 kph  
Server dropped a message.  
90 kph  
80 kph  
Server dropped a message.  
70 kph  
60 kph  
Server dropped a message.  
50 kph  
40 kph  
Server dropped a message.  
30 kph  
20 kph  
Server dropped a message.  
10 kph  
Press ENTER to shut down client  
```  
  
 El cliente informa sobre 10 velocidades de viento diferentes para el servicio, pero solo marca la mitad con el encabezado especial.  
  
 En el servicio, debería ver el resultado siguiente:  
  
```console  
Press ENTER to exit.  
Dangerous wind detected! Reported speed (90) is greater than 64 kph.  
Dangerous wind detected! Reported speed (70) is greater than 64 kph.  
5 wind speed reports have been received.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Instale ASP.NET 4.0 con el siguiente comando.  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. Asegúrese de que ha realizado el procedimiento de instalación única [para los ejemplos](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)de Windows Communication Foundation .  
  
3. Para compilar la solución, siga las instrucciones de Creación de [ejemplos](../../../../docs/framework/wcf/samples/building-the-samples.md)de Windows Communication Foundation .  
  
4. Para ejecutar el ejemplo en una configuración de uno o entre equipos, siga las instrucciones de Ejecución de [los ejemplos](../../../../docs/framework/wcf/samples/running-the-samples.md)de Windows Communication Foundation .  
  
5. Ejecute primero Service.exe, a continuación, ejecute Client.exe e inspeccione ambas ventanas de la consola para ver el resultado.  
