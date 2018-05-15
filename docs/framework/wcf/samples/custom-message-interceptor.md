---
title: Interceptador de mensajes personalizados
ms.date: 03/30/2017
ms.assetid: 73f20972-53f8-475a-8bfe-c133bfa225b0
ms.openlocfilehash: a59b2075473e2ca4c8cb8751fd6cb733f282238b
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="custom-message-interceptor"></a><span data-ttu-id="85ca1-102">Interceptador de mensajes personalizados</span><span class="sxs-lookup"><span data-stu-id="85ca1-102">Custom Message Interceptor</span></span>
<span data-ttu-id="85ca1-103">Este ejemplo muestra el uso del modelo de extensibilidad del canal.</span><span class="sxs-lookup"><span data-stu-id="85ca1-103">This sample demonstrates the use of the channel extensibility model.</span></span> <span data-ttu-id="85ca1-104">En particular, muestra cómo implementar un elemento de enlace personalizado que crea generadores de canales y agentes de escucha de canales para interceptar todos los mensajes entrantes y salientes en un punto concreto en la pila de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="85ca1-104">In particular, it shows how to implement a custom binding element that creates channel factories and channel listeners to intercept all incoming and outgoing messages at a particular point in the run-time stack.</span></span> <span data-ttu-id="85ca1-105">El ejemplo también incluye un cliente y un servidor que muestran el uso de estos generadores personalizados.</span><span class="sxs-lookup"><span data-stu-id="85ca1-105">The sample also includes a client and server that demonstrate the use of these custom factories.</span></span>  
  
 <span data-ttu-id="85ca1-106">En este ejemplo, el cliente y el servicio son programas de consola (.exe).</span><span class="sxs-lookup"><span data-stu-id="85ca1-106">In this sample, both the client and the service are console programs (.exe).</span></span> <span data-ttu-id="85ca1-107">El cliente y el servicio hacen uso de una biblioteca común (.dll) que contiene el elemento de enlace personalizado y sus objetos en tiempo de ejecución asociados.</span><span class="sxs-lookup"><span data-stu-id="85ca1-107">The client and service both make use of a common library (.dll) that contains the custom binding element and its associated run-time objects.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="85ca1-108">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="85ca1-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="85ca1-109">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="85ca1-109">The samples may already be installed on your machine.</span></span> <span data-ttu-id="85ca1-110">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="85ca1-110">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="85ca1-111">Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="85ca1-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="85ca1-112">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="85ca1-112">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\MessageInterceptor`  
  
 <span data-ttu-id="85ca1-113">El ejemplo describe el procedimiento recomendado para crear un canal superpuesto personalizado en Windows Communication Foundation (WCF), utilizando el marco del canal y los siguientes procedimientos recomendados de WCF.</span><span class="sxs-lookup"><span data-stu-id="85ca1-113">The sample describes the recommended procedure for creating a custom layered channel in Windows Communication Foundation (WCF), by using the channel framework and following WCF best practices.</span></span> <span data-ttu-id="85ca1-114">Los pasos para crear un canal superpuesto personalizado son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="85ca1-114">The steps to create a custom layered channel are as follows:</span></span>  
  
1.  <span data-ttu-id="85ca1-115">Decida cuál de las formas del canal admitirá el generador de canales y el agente de escucha del canal.</span><span class="sxs-lookup"><span data-stu-id="85ca1-115">Decide which of the channel shapes your channel factory and channel listener will support.</span></span>  
  
2.  <span data-ttu-id="85ca1-116">Cree un generador de canales y un agente de escucha del canal que admita las formas del canal.</span><span class="sxs-lookup"><span data-stu-id="85ca1-116">Create a channel factory and a channel listener that support your channel shapes.</span></span>  
  
3.  <span data-ttu-id="85ca1-117">Agregue un elemento de enlace que añada el canal superpuesto personalizado a una pila de canales.</span><span class="sxs-lookup"><span data-stu-id="85ca1-117">Add a binding element that adds the custom layered channel to a channel stack.</span></span>  
  
4.  <span data-ttu-id="85ca1-118">Agregue una sección de extensión de elemento de enlace para exponer el nuevo elemento de enlace al sistema de configuración.</span><span class="sxs-lookup"><span data-stu-id="85ca1-118">Add a binding element extension section to expose the new binding element to the configuration system.</span></span>  
  
## <a name="channel-shapes"></a><span data-ttu-id="85ca1-119">Formas del canal</span><span class="sxs-lookup"><span data-stu-id="85ca1-119">Channel Shapes</span></span>  
 <span data-ttu-id="85ca1-120">El primer paso para escribir un canal superpuesto personalizado es decidir qué formas son necesarias para el canal.</span><span class="sxs-lookup"><span data-stu-id="85ca1-120">The first step in writing a custom layered channel is to decide which shapes are required for the channel.</span></span> <span data-ttu-id="85ca1-121">Para nuestro inspector de mensajes, admitimos cualquier forma que admita el nivel debajo de nosotros (por ejemplo, si la capa debajo de nosotros puede compilar <xref:System.ServiceModel.Channels.IOutputChannel> y <xref:System.ServiceModel.Channels.IDuplexSessionChannel>, también exponemos <xref:System.ServiceModel.Channels.IOutputChannel> y <xref:System.ServiceModel.Channels.IDuplexSessionChannel>).</span><span class="sxs-lookup"><span data-stu-id="85ca1-121">For our message inspector, we support any shape that the layer below us supports (for example, if the layer below us can build <xref:System.ServiceModel.Channels.IOutputChannel> and <xref:System.ServiceModel.Channels.IDuplexSessionChannel>, then we also expose <xref:System.ServiceModel.Channels.IOutputChannel> and <xref:System.ServiceModel.Channels.IDuplexSessionChannel>).</span></span>  
  
## <a name="channel-factory-and-listener-factory"></a><span data-ttu-id="85ca1-122">Generador de canales y de agentes de escucha</span><span class="sxs-lookup"><span data-stu-id="85ca1-122">Channel Factory and Listener Factory</span></span>  
 <span data-ttu-id="85ca1-123">El paso siguiente para escribir un canal superpuesto personalizado es crear una implementación de <xref:System.ServiceModel.Channels.IChannelFactory> para los canales de cliente y de <xref:System.ServiceModel.Channels.IChannelListener> para los canales de servicio.</span><span class="sxs-lookup"><span data-stu-id="85ca1-123">The next step in writing a custom layered channel is to create an implementation of <xref:System.ServiceModel.Channels.IChannelFactory> for client channels and of <xref:System.ServiceModel.Channels.IChannelListener> for service channels.</span></span>  
  
 <span data-ttu-id="85ca1-124">Estas clases escogen un generador y un agente de escucha internos y delegan todas las llamadas excepto `OnCreateChannel` y `OnAcceptChannel` al generador y agente de escucha internos.</span><span class="sxs-lookup"><span data-stu-id="85ca1-124">These classes take an inner factory and listener, and delegate all but the `OnCreateChannel` and `OnAcceptChannel` calls to the inner factory and listener.</span></span>  
  
```  
class InterceptingChannelFactory<TChannel> : ChannelFactoryBase<TChannel>  
{ ... }  
class InterceptingChannelListener<TChannel> : ListenerFactoryBase<TChannel>  
{ ... }  
```  
  
## <a name="adding-a-binding-element"></a><span data-ttu-id="85ca1-125">Adición de un elemento de enlace</span><span class="sxs-lookup"><span data-stu-id="85ca1-125">Adding a Binding Element</span></span>  
 <span data-ttu-id="85ca1-126">El ejemplo define un elemento de enlace personalizado: `InterceptingBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="85ca1-126">The sample defines a custom binding element: `InterceptingBindingElement`.</span></span> <span data-ttu-id="85ca1-127">`InterceptingBindingElement` toma una `ChannelMessageInterceptor` como entrada y usa este `ChannelMessageInterceptor` para manipular los mensajes que pasan a través de él.</span><span class="sxs-lookup"><span data-stu-id="85ca1-127">`InterceptingBindingElement` takes a `ChannelMessageInterceptor` as an input, and uses this `ChannelMessageInterceptor` to manipulate messages that pass through it.</span></span> <span data-ttu-id="85ca1-128">Ésta es la única clase que debe ser pública.</span><span class="sxs-lookup"><span data-stu-id="85ca1-128">This is the only class that must be public.</span></span> <span data-ttu-id="85ca1-129">El generador, agente de escucha y canales pueden ser implementaciones internas de las interfaces en tiempo de ejecución públicas.</span><span class="sxs-lookup"><span data-stu-id="85ca1-129">The factory, listener, and channels can all be internal implementations of the public run-time interfaces.</span></span>  
  
```  
public class InterceptingBindingElement : BindingElement  
```  
  
## <a name="adding-configuration-support"></a><span data-ttu-id="85ca1-130">Agregación de la compatibilidad de configuración</span><span class="sxs-lookup"><span data-stu-id="85ca1-130">Adding Configuration Support</span></span>  
 <span data-ttu-id="85ca1-131">Para integrar con la configuración de enlace, la biblioteca define un controlador de la sección de configuración como una sección de extensión de elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="85ca1-131">To integrate with binding configuration, the library defines a configuration section handler as a binding element extension section.</span></span> <span data-ttu-id="85ca1-132">Los archivos de configuración del servidor y el cliente deben registrar la extensión del elemento de enlace con el sistema de configuración.</span><span class="sxs-lookup"><span data-stu-id="85ca1-132">The client and server configuration files must register the binding element extension with the configuration system.</span></span> <span data-ttu-id="85ca1-133">Los implementadores que desean exponer su elemento de enlace al sistema de configuración pueden derivar de esta clase.</span><span class="sxs-lookup"><span data-stu-id="85ca1-133">Implementers that want to expose their binding element to the configuration system can derive from this class.</span></span>  
  
```  
public abstract class InterceptingElement : BindingElementExtensionElement { ... }  
```  
  
## <a name="adding-policy"></a><span data-ttu-id="85ca1-134">Adición de directivas</span><span class="sxs-lookup"><span data-stu-id="85ca1-134">Adding Policy</span></span>  
 <span data-ttu-id="85ca1-135">Para integrar con nuestro sistema de directivas, `InterceptingBindingElement` implementa IPolicyExportExtension para señalar que deberíamos participar en la generación de directivas.</span><span class="sxs-lookup"><span data-stu-id="85ca1-135">To integrate with our policy system, `InterceptingBindingElement` implements IPolicyExportExtension to signal that we should participate in generating policy.</span></span> <span data-ttu-id="85ca1-136">Para permitir importar la directiva en un cliente generado, el usuario puede registrar una clase derivada de `InterceptingBindingElementImporter` e invalidar `CreateMessageInterceptor`() para generar su clase `ChannelMessageInterceptor` habilitada por la directiva.</span><span class="sxs-lookup"><span data-stu-id="85ca1-136">To support importing policy on a generated client, the user can register a derived class of `InterceptingBindingElementImporter` and override `CreateMessageInterceptor`() to generate their policy-enabled `ChannelMessageInterceptor` class.</span></span>  
  
## <a name="example-droppable-message-inspector"></a><span data-ttu-id="85ca1-137">Ejemplo: inspector de mensajes que pueden quitarse</span><span class="sxs-lookup"><span data-stu-id="85ca1-137">Example: Droppable Message Inspector</span></span>  
 <span data-ttu-id="85ca1-138">En este ejemplo se incluye una implementación de ejemplo de `ChannelMessageInspector` que quita mensajes.</span><span class="sxs-lookup"><span data-stu-id="85ca1-138">Included in the sample is an example implementation of `ChannelMessageInspector` which drops messages.</span></span>  
  
```  
class DroppingServerElement : InterceptingElement  
{  
    protected override ChannelMessageInterceptor CreateMessageInterceptor()  
    {  
        return new DroppingServerInterceptor();  
    }  
}  
```  
  
 <span data-ttu-id="85ca1-139">Puede tener acceso a ella desde la configuración de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="85ca1-139">You can access it from configuration as follows:</span></span>  
  
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
  
 <span data-ttu-id="85ca1-140">El cliente y servidor usan esta sección de configuración que se acaba de crear para insertar los generadores personalizados en el nivel más bajo de sus pilas de canales en el tiempo de ejecución (por encima del nivel de transporte).</span><span class="sxs-lookup"><span data-stu-id="85ca1-140">The client and server both use this newly created configuration section to insert the custom factories into the lowest-level of their run-time channel stacks (above the transport level).</span></span>  
  
```xml  
<customBinding>  
  <binding name="sampleBinding">  
    <droppingInterceptor/>  
    <httpTransport/>  
  </binding>  
</customBinding>  
```  
  
 <span data-ttu-id="85ca1-141">El cliente utiliza la biblioteca `MessageInterceptor` para agregar un encabezado personalizado a mensajes con número par.</span><span class="sxs-lookup"><span data-stu-id="85ca1-141">The client uses the `MessageInterceptor` library to add a custom header to even numbered messages.</span></span> <span data-ttu-id="85ca1-142">Por otra parte, el servicio utiliza la biblioteca `MessageInterceptor` para quitar cualquier mensaje que no tenga este encabezado especial.</span><span class="sxs-lookup"><span data-stu-id="85ca1-142">The service on the other hand uses `MessageInterceptor` library to drop any messages that do not have this special header.</span></span>  
  
 <span data-ttu-id="85ca1-143">Debería ver el siguiente resultado del cliente después de ejecutar primero el servicio y después el cliente.</span><span class="sxs-lookup"><span data-stu-id="85ca1-143">You should see the following client output after running the service and then the client.</span></span>  
  
```  
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
  
 <span data-ttu-id="85ca1-144">El cliente informa sobre 10 velocidades de viento diferentes para el servicio, pero solo marca la mitad con el encabezado especial.</span><span class="sxs-lookup"><span data-stu-id="85ca1-144">The client reports 10 different wind speeds to the service, but only tags half of them with the special header.</span></span>  
  
 <span data-ttu-id="85ca1-145">En el servicio, debería ver el resultado siguiente:</span><span class="sxs-lookup"><span data-stu-id="85ca1-145">On the service, you should see the following output:</span></span>  
  
```  
Press ENTER to exit.  
Dangerous wind detected! Reported speed (90) is greater than 64 kph.  
Dangerous wind detected! Reported speed (70) is greater than 64 kph.  
5 wind speed reports have been received.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="85ca1-146">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="85ca1-146">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="85ca1-147">Instale [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 mediante el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="85ca1-147">Install [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 using the following command.</span></span>  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  <span data-ttu-id="85ca1-148">Asegúrese de que ha llevado a cabo la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="85ca1-148">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3.  <span data-ttu-id="85ca1-149">Para compilar la solución, siga las instrucciones que aparecen en [compilar los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="85ca1-149">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="85ca1-150">Para ejecutar el ejemplo en una configuración de equipo único o de varios, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="85ca1-150">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
5.  <span data-ttu-id="85ca1-151">Ejecute primero Service.exe, a continuación, ejecute Client.exe e inspeccione ambas ventanas de la consola para ver el resultado.</span><span class="sxs-lookup"><span data-stu-id="85ca1-151">Run Service.exe first then run Client.exe and watch both console windows for output.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85ca1-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="85ca1-152">See Also</span></span>
