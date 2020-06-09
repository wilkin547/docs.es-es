---
title: Interceptador de mensajes personalizados
ms.date: 03/30/2017
ms.assetid: 73f20972-53f8-475a-8bfe-c133bfa225b0
ms.openlocfilehash: b9a517d0f8ada3680d49cd5ab0b13fa9e4d85402
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600067"
---
# <a name="custom-message-interceptor"></a><span data-ttu-id="0db9e-102">Interceptador de mensajes personalizados</span><span class="sxs-lookup"><span data-stu-id="0db9e-102">Custom Message Interceptor</span></span>
<span data-ttu-id="0db9e-103">Este ejemplo muestra el uso del modelo de extensibilidad del canal.</span><span class="sxs-lookup"><span data-stu-id="0db9e-103">This sample demonstrates the use of the channel extensibility model.</span></span> <span data-ttu-id="0db9e-104">En particular, muestra cómo implementar un elemento de enlace personalizado que crea generadores de canales y agentes de escucha de canales para interceptar todos los mensajes entrantes y salientes en un punto concreto en la pila de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0db9e-104">In particular, it shows how to implement a custom binding element that creates channel factories and channel listeners to intercept all incoming and outgoing messages at a particular point in the run-time stack.</span></span> <span data-ttu-id="0db9e-105">El ejemplo también incluye un cliente y un servidor que muestran el uso de estos generadores personalizados.</span><span class="sxs-lookup"><span data-stu-id="0db9e-105">The sample also includes a client and server that demonstrate the use of these custom factories.</span></span>  
  
 <span data-ttu-id="0db9e-106">En este ejemplo, el cliente y el servicio son programas de consola (.exe).</span><span class="sxs-lookup"><span data-stu-id="0db9e-106">In this sample, both the client and the service are console programs (.exe).</span></span> <span data-ttu-id="0db9e-107">El cliente y el servicio hacen uso de una biblioteca común (.dll) que contiene el elemento de enlace personalizado y sus objetos en tiempo de ejecución asociados.</span><span class="sxs-lookup"><span data-stu-id="0db9e-107">The client and service both make use of a common library (.dll) that contains the custom binding element and its associated run-time objects.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0db9e-108">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="0db9e-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="0db9e-109">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="0db9e-109">The samples may already be installed on your machine.</span></span> <span data-ttu-id="0db9e-110">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="0db9e-110">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="0db9e-111">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="0db9e-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0db9e-112">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="0db9e-112">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\MessageInterceptor`  
  
 <span data-ttu-id="0db9e-113">El ejemplo describe el procedimiento recomendado para crear un canal superpuesto personalizado en Windows Communication Foundation (WCF), mediante el marco del canal y los siguientes procedimientos recomendados de WCF.</span><span class="sxs-lookup"><span data-stu-id="0db9e-113">The sample describes the recommended procedure for creating a custom layered channel in Windows Communication Foundation (WCF), by using the channel framework and following WCF best practices.</span></span> <span data-ttu-id="0db9e-114">Los pasos para crear un canal superpuesto personalizado son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="0db9e-114">The steps to create a custom layered channel are as follows:</span></span>  
  
1. <span data-ttu-id="0db9e-115">Decida cuál de las formas del canal admitirá el generador de canales y el agente de escucha del canal.</span><span class="sxs-lookup"><span data-stu-id="0db9e-115">Decide which of the channel shapes your channel factory and channel listener will support.</span></span>  
  
2. <span data-ttu-id="0db9e-116">Cree un generador de canales y un agente de escucha del canal que admita las formas del canal.</span><span class="sxs-lookup"><span data-stu-id="0db9e-116">Create a channel factory and a channel listener that support your channel shapes.</span></span>  
  
3. <span data-ttu-id="0db9e-117">Agregue un elemento de enlace que añada el canal superpuesto personalizado a una pila de canales.</span><span class="sxs-lookup"><span data-stu-id="0db9e-117">Add a binding element that adds the custom layered channel to a channel stack.</span></span>  
  
4. <span data-ttu-id="0db9e-118">Agregue una sección de extensión de elemento de enlace para exponer el nuevo elemento de enlace al sistema de configuración.</span><span class="sxs-lookup"><span data-stu-id="0db9e-118">Add a binding element extension section to expose the new binding element to the configuration system.</span></span>  
  
## <a name="channel-shapes"></a><span data-ttu-id="0db9e-119">Formas del canal</span><span class="sxs-lookup"><span data-stu-id="0db9e-119">Channel Shapes</span></span>  
 <span data-ttu-id="0db9e-120">El primer paso para escribir un canal superpuesto personalizado es decidir qué formas son necesarias para el canal.</span><span class="sxs-lookup"><span data-stu-id="0db9e-120">The first step in writing a custom layered channel is to decide which shapes are required for the channel.</span></span> <span data-ttu-id="0db9e-121">Para nuestro inspector de mensajes, admitimos cualquier forma que admita el nivel debajo de nosotros (por ejemplo, si la capa debajo de nosotros puede compilar <xref:System.ServiceModel.Channels.IOutputChannel> y <xref:System.ServiceModel.Channels.IDuplexSessionChannel>, también exponemos <xref:System.ServiceModel.Channels.IOutputChannel> y <xref:System.ServiceModel.Channels.IDuplexSessionChannel>).</span><span class="sxs-lookup"><span data-stu-id="0db9e-121">For our message inspector, we support any shape that the layer below us supports (for example, if the layer below us can build <xref:System.ServiceModel.Channels.IOutputChannel> and <xref:System.ServiceModel.Channels.IDuplexSessionChannel>, then we also expose <xref:System.ServiceModel.Channels.IOutputChannel> and <xref:System.ServiceModel.Channels.IDuplexSessionChannel>).</span></span>  
  
## <a name="channel-factory-and-listener-factory"></a><span data-ttu-id="0db9e-122">Generador de canales y de agentes de escucha</span><span class="sxs-lookup"><span data-stu-id="0db9e-122">Channel Factory and Listener Factory</span></span>  
 <span data-ttu-id="0db9e-123">El paso siguiente para escribir un canal superpuesto personalizado es crear una implementación de <xref:System.ServiceModel.Channels.IChannelFactory> para los canales de cliente y de <xref:System.ServiceModel.Channels.IChannelListener> para los canales de servicio.</span><span class="sxs-lookup"><span data-stu-id="0db9e-123">The next step in writing a custom layered channel is to create an implementation of <xref:System.ServiceModel.Channels.IChannelFactory> for client channels and of <xref:System.ServiceModel.Channels.IChannelListener> for service channels.</span></span>  
  
 <span data-ttu-id="0db9e-124">Estas clases escogen un generador y un agente de escucha internos y delegan todas las llamadas excepto `OnCreateChannel` y `OnAcceptChannel` al generador y agente de escucha internos.</span><span class="sxs-lookup"><span data-stu-id="0db9e-124">These classes take an inner factory and listener, and delegate all but the `OnCreateChannel` and `OnAcceptChannel` calls to the inner factory and listener.</span></span>  
  
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
  
## <a name="adding-a-binding-element"></a><span data-ttu-id="0db9e-125">Adición de un elemento de enlace</span><span class="sxs-lookup"><span data-stu-id="0db9e-125">Adding a Binding Element</span></span>  
 <span data-ttu-id="0db9e-126">El ejemplo define un elemento de enlace personalizado: `InterceptingBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="0db9e-126">The sample defines a custom binding element: `InterceptingBindingElement`.</span></span> <span data-ttu-id="0db9e-127">`InterceptingBindingElement`toma un `ChannelMessageInterceptor` como una entrada y lo utiliza `ChannelMessageInterceptor` para manipular los mensajes que lo atraviesan.</span><span class="sxs-lookup"><span data-stu-id="0db9e-127">`InterceptingBindingElement` takes a `ChannelMessageInterceptor` as an input, and uses this `ChannelMessageInterceptor` to manipulate messages that pass through it.</span></span> <span data-ttu-id="0db9e-128">Ésta es la única clase que debe ser pública.</span><span class="sxs-lookup"><span data-stu-id="0db9e-128">This is the only class that must be public.</span></span> <span data-ttu-id="0db9e-129">El generador, agente de escucha y canales pueden ser implementaciones internas de las interfaces en tiempo de ejecución públicas.</span><span class="sxs-lookup"><span data-stu-id="0db9e-129">The factory, listener, and channels can all be internal implementations of the public run-time interfaces.</span></span>  
  
```csharp
public class InterceptingBindingElement : BindingElement
{
}
```  
  
## <a name="adding-configuration-support"></a><span data-ttu-id="0db9e-130">Agregación de la compatibilidad de configuración</span><span class="sxs-lookup"><span data-stu-id="0db9e-130">Adding Configuration Support</span></span>  
 <span data-ttu-id="0db9e-131">Para integrar con la configuración de enlace, la biblioteca define un controlador de la sección de configuración como una sección de extensión de elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="0db9e-131">To integrate with binding configuration, the library defines a configuration section handler as a binding element extension section.</span></span> <span data-ttu-id="0db9e-132">Los archivos de configuración del servidor y el cliente deben registrar la extensión del elemento de enlace con el sistema de configuración.</span><span class="sxs-lookup"><span data-stu-id="0db9e-132">The client and server configuration files must register the binding element extension with the configuration system.</span></span> <span data-ttu-id="0db9e-133">Los implementadores que desean exponer su elemento de enlace al sistema de configuración pueden derivar de esta clase.</span><span class="sxs-lookup"><span data-stu-id="0db9e-133">Implementers that want to expose their binding element to the configuration system can derive from this class.</span></span>  
  
```csharp
public abstract class InterceptingElement : BindingElementExtensionElement
{
    //...
}
```  
  
## <a name="adding-policy"></a><span data-ttu-id="0db9e-134">Adición de directivas</span><span class="sxs-lookup"><span data-stu-id="0db9e-134">Adding Policy</span></span>  
 <span data-ttu-id="0db9e-135">Para integrar con nuestro sistema de directivas, `InterceptingBindingElement` implementa IPolicyExportExtension para señalar que deberíamos participar en la generación de directivas.</span><span class="sxs-lookup"><span data-stu-id="0db9e-135">To integrate with our policy system, `InterceptingBindingElement` implements IPolicyExportExtension to signal that we should participate in generating policy.</span></span> <span data-ttu-id="0db9e-136">Para permitir importar la directiva en un cliente generado, el usuario puede registrar una clase derivada de `InterceptingBindingElementImporter` e invalidar `CreateMessageInterceptor`() para generar su clase `ChannelMessageInterceptor` habilitada por la directiva.</span><span class="sxs-lookup"><span data-stu-id="0db9e-136">To support importing policy on a generated client, the user can register a derived class of `InterceptingBindingElementImporter` and override `CreateMessageInterceptor`() to generate their policy-enabled `ChannelMessageInterceptor` class.</span></span>  
  
## <a name="example-droppable-message-inspector"></a><span data-ttu-id="0db9e-137">Ejemplo: inspector de mensajes que pueden quitarse</span><span class="sxs-lookup"><span data-stu-id="0db9e-137">Example: Droppable Message Inspector</span></span>  
 <span data-ttu-id="0db9e-138">En este ejemplo se incluye una implementación de ejemplo de `ChannelMessageInspector` que quita mensajes.</span><span class="sxs-lookup"><span data-stu-id="0db9e-138">Included in the sample is an example implementation of `ChannelMessageInspector` which drops messages.</span></span>  
  
```csharp
class DroppingServerElement : InterceptingElement  
{  
    protected override ChannelMessageInterceptor CreateMessageInterceptor()  
    {  
        return new DroppingServerInterceptor();  
    }  
}  
```  
  
 <span data-ttu-id="0db9e-139">Puede tener acceso a ella desde la configuración de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="0db9e-139">You can access it from configuration as follows:</span></span>  
  
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
  
 <span data-ttu-id="0db9e-140">El cliente y servidor usan esta sección de configuración que se acaba de crear para insertar los generadores personalizados en el nivel más bajo de sus pilas de canales en el tiempo de ejecución (por encima del nivel de transporte).</span><span class="sxs-lookup"><span data-stu-id="0db9e-140">The client and server both use this newly created configuration section to insert the custom factories into the lowest-level of their run-time channel stacks (above the transport level).</span></span>  
  
```xml  
<customBinding>  
  <binding name="sampleBinding">  
    <droppingInterceptor/>  
    <httpTransport/>  
  </binding>  
</customBinding>  
```  
  
 <span data-ttu-id="0db9e-141">El cliente utiliza la biblioteca `MessageInterceptor` para agregar un encabezado personalizado a mensajes con número par.</span><span class="sxs-lookup"><span data-stu-id="0db9e-141">The client uses the `MessageInterceptor` library to add a custom header to even numbered messages.</span></span> <span data-ttu-id="0db9e-142">Por otra parte, el servicio utiliza la biblioteca `MessageInterceptor` para colocar cualquier mensaje que no tenga este encabezado especial.</span><span class="sxs-lookup"><span data-stu-id="0db9e-142">The service on the other hand uses `MessageInterceptor` library to drop any messages that do not have this special header.</span></span>  
  
 <span data-ttu-id="0db9e-143">Debería ver el siguiente resultado del cliente después de ejecutar primero el servicio y después el cliente.</span><span class="sxs-lookup"><span data-stu-id="0db9e-143">You should see the following client output after running the service and then the client.</span></span>  
  
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
  
 <span data-ttu-id="0db9e-144">El cliente informa sobre 10 velocidades de viento diferentes para el servicio, pero solo marca la mitad con el encabezado especial.</span><span class="sxs-lookup"><span data-stu-id="0db9e-144">The client reports 10 different wind speeds to the service, but only tags half of them with the special header.</span></span>  
  
 <span data-ttu-id="0db9e-145">En el servicio, debería ver el resultado siguiente:</span><span class="sxs-lookup"><span data-stu-id="0db9e-145">On the service, you should see the following output:</span></span>  
  
```console  
Press ENTER to exit.  
Dangerous wind detected! Reported speed (90) is greater than 64 kph.  
Dangerous wind detected! Reported speed (70) is greater than 64 kph.  
5 wind speed reports have been received.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="0db9e-146">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="0db9e-146">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="0db9e-147">Instale ASP.NET 4,0 con el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="0db9e-147">Install ASP.NET 4.0 using the following command.</span></span>  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. <span data-ttu-id="0db9e-148">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0db9e-148">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3. <span data-ttu-id="0db9e-149">Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0db9e-149">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="0db9e-150">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0db9e-150">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
5. <span data-ttu-id="0db9e-151">Ejecute primero Service.exe, a continuación, ejecute Client.exe e inspeccione ambas ventanas de la consola para ver el resultado.</span><span class="sxs-lookup"><span data-stu-id="0db9e-151">Run Service.exe first then run Client.exe and watch both console windows for output.</span></span>  
