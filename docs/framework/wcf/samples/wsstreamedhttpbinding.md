---
title: WSStreamedHttpBinding
ms.date: 03/30/2017
ms.assetid: 97ce4d3d-ca6f-45fa-b33b-2429bb84e65b
ms.openlocfilehash: 663b7921e4e8a66d9b905404bad00f613e2f04cc
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144661"
---
# <a name="wsstreamedhttpbinding"></a><span data-ttu-id="84dff-102">WSStreamedHttpBinding</span><span class="sxs-lookup"><span data-stu-id="84dff-102">WSStreamedHttpBinding</span></span>

<span data-ttu-id="84dff-103">El ejemplo muestra cómo crear un enlace diseñado para admitir escenarios de transmisión por secuencias cuando se usa el transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="84dff-103">The sample demonstrates how to create a binding that is designed to support streaming scenarios when the HTTP transport is used.</span></span>

> [!NOTE]
> <span data-ttu-id="84dff-104">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="84dff-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="84dff-105">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="84dff-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="84dff-106">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="84dff-106">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="84dff-107">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="84dff-107">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="84dff-108">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="84dff-108">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Binding\WSStreamedHttpBinding`

 <span data-ttu-id="84dff-109">Los pasos para crear y configurar un nuevo enlace estándar son como sigue.</span><span class="sxs-lookup"><span data-stu-id="84dff-109">The steps to create and configure a new standard binding are as follows.</span></span>

1. <span data-ttu-id="84dff-110">Crear un nuevo enlace estándar</span><span class="sxs-lookup"><span data-stu-id="84dff-110">Create a new standard binding</span></span>

    <span data-ttu-id="84dff-111">Los enlaces estándar en Windows Communication Foundation (WCF), como basicHttpBinding y netTcpBinding, configuran los transportes subyacentes y la pila de canales para requisitos específicos.</span><span class="sxs-lookup"><span data-stu-id="84dff-111">The standard bindings in Windows Communication Foundation (WCF) such as basicHttpBinding, and netTcpBinding configure the underlying transports and channel stack for specific requirements.</span></span> <span data-ttu-id="84dff-112">En este ejemplo, `WSStreamedHttpBinding` configura la pila del canal para permitir el vertido.</span><span class="sxs-lookup"><span data-stu-id="84dff-112">In this sample, `WSStreamedHttpBinding` configures the channel stack to support streaming.</span></span> <span data-ttu-id="84dff-113">De forma predeterminada, la seguridad del WS y la mensajería de confianza no se agregan a la pila del canal porque ambas características no se admiten en el vertido.</span><span class="sxs-lookup"><span data-stu-id="84dff-113">By default, WS-Security and reliable messaging are not added to the channel stack because both features are not supported by streaming.</span></span> <span data-ttu-id="84dff-114">El nuevo enlace se implementa en la clase `WSStreamedHttpBinding` que deriva de <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="84dff-114">The new binding is implemented in the class `WSStreamedHttpBinding` that derives from <xref:System.ServiceModel.Channels.Binding>.</span></span> <span data-ttu-id="84dff-115">El `WSStreamedHttpBinding` contiene los siguientes elementos de enlace: <xref:System.ServiceModel.Channels.HttpTransportBindingElement>, <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>, <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>, y <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="84dff-115">The `WSStreamedHttpBinding` contains the following binding elements: <xref:System.ServiceModel.Channels.HttpTransportBindingElement>, <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>, <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>, and <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>.</span></span> <span data-ttu-id="84dff-116">La clase proporciona un método `CreateBindingElements()` para configurar la pila de enlace resultante, como se muestra en el código muestra siguiente.</span><span class="sxs-lookup"><span data-stu-id="84dff-116">The class provides a `CreateBindingElements()` method to configure the resulting binding stack, as shown in the following sample code.</span></span>

    ```csharp
    public override BindingElementCollection CreateBindingElements()
    {
        // return collection of BindingElements
        BindingElementCollection bindingElements = new BindingElementCollection();

        // the order of binding elements within the collection is important: layered channels are applied in the order included, followed by
        // the message encoder, and finally the transport at the end
        if (flowTransactions)
        {
            bindingElements.Add(transactionFlow);
        }
        bindingElements.Add(textEncoding);

        // add transport (http or https)
        bindingElements.Add(transport);
        return bindingElements.Clone();
    }
    ```

2. <span data-ttu-id="84dff-117">Añadir la compatibilidad de configuración</span><span class="sxs-lookup"><span data-stu-id="84dff-117">Add configuration support</span></span>

    <span data-ttu-id="84dff-118">Para exponer el transporte a través de la configuración, el ejemplo implementa dos clases más, `WSStreamedHttpBindingConfigurationElement` y `WSStreamedHttpBindingSection`.</span><span class="sxs-lookup"><span data-stu-id="84dff-118">To expose the transport through configuration the sample implements two more classes—`WSStreamedHttpBindingConfigurationElement` and `WSStreamedHttpBindingSection`.</span></span> <span data-ttu-id="84dff-119">La clase `WSStreamedHttpBindingSection` es un <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602> que expone `WSStreamedHttpBinding` al sistema de configuración de WCF.</span><span class="sxs-lookup"><span data-stu-id="84dff-119">The class `WSStreamedHttpBindingSection` is a <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602> that exposes `WSStreamedHttpBinding` to the WCF configuration system.</span></span> <span data-ttu-id="84dff-120">El volumen de la implementación se delega a `WSStreamedHttpBindingConfigurationElement`, lo cual deriva de <xref:System.ServiceModel.Configuration.StandardBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="84dff-120">The bulk of the implementation is delegated to `WSStreamedHttpBindingConfigurationElement`, which derives from <xref:System.ServiceModel.Configuration.StandardBindingElement>.</span></span> <span data-ttu-id="84dff-121">La clase `WSStreamedHttpBindingConfigurationElement` tiene propiedades que corresponden a las propiedades de `WSStreamedHttpBinding`y funciones para asignar cada elemento de configuración a un enlace.</span><span class="sxs-lookup"><span data-stu-id="84dff-121">The class `WSStreamedHttpBindingConfigurationElement` has properties that correspond to the properties of `WSStreamedHttpBinding`, and functions to map each configuration element to a binding.</span></span>

    <span data-ttu-id="84dff-122">Registre este controlador con el sistema de configuración, agregando la siguiente sección al archivo de configuración pertinente.</span><span class="sxs-lookup"><span data-stu-id="84dff-122">Register the handler with the configuration system, by adding the following section to the service's configuration file.</span></span>

    ```xml
    <configuration>
      <system.serviceModel>
        <extensions>
          <bindingExtensions>
            <add name="wsStreamedHttpBinding" type="Microsoft.ServiceModel.Samples.WSStreamedHttpBindingCollectionElement, WSStreamedHttpBinding, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null" />
          </bindingExtensions>
        </extensions>
      </system.serviceModel>
    </configuration>
    ```

    <span data-ttu-id="84dff-123">A continuación, se puede hacer referencia al controlador desde la sección de configuración de serviceModel.</span><span class="sxs-lookup"><span data-stu-id="84dff-123">The handler can then be referenced from the serviceModel configuration section.</span></span>

    ```xml
    <configuration>
      <system.serviceModel>
        <client>
          <endpoint
                    address="https://localhost/servicemodelsamples/service.svc"
                    bindingConfiguration="Binding"
                    binding="wsStreamedHttpBinding"
                    contract="Microsoft.ServiceModel.Samples.IStreamedEchoService"/>
        </client>
      </system.serviceModel>
    </configuration>
    ```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="84dff-124">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="84dff-124">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="84dff-125">Instale ASP.NET 4,0 con el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="84dff-125">Install ASP.NET 4.0 using the following command.</span></span>

    ```console
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable
    ```

2. <span data-ttu-id="84dff-126">Asegúrese de que ha realizado los pasos enumerados en [el procedimiento de instalación único para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="84dff-126">Ensure that you have performed the steps listed in [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

3. <span data-ttu-id="84dff-127">Asegúrese de que ha realizado las [instrucciones de instalación del certificado de servidor de Internet Information Services (IIS)](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).</span><span class="sxs-lookup"><span data-stu-id="84dff-127">Ensure that you have performed the [Internet Information Services (IIS) Server Certificate Installation Instructions](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).</span></span>

4. <span data-ttu-id="84dff-128">Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="84dff-128">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

5. <span data-ttu-id="84dff-129">Para ejecutar el ejemplo en una configuración entre equipos, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="84dff-129">To run the sample in a cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

6. <span data-ttu-id="84dff-130">Cuando se muestre la ventana de cliente, escriba "Sample.txt."</span><span class="sxs-lookup"><span data-stu-id="84dff-130">When the client window displays, type "Sample.txt".</span></span> <span data-ttu-id="84dff-131">Debería encontrar una "Copy of Sample.txt" en su directorio.</span><span class="sxs-lookup"><span data-stu-id="84dff-131">You should find a "Copy of Sample.txt" in your directory.</span></span>

## <a name="the-wsstreamedhttpbinding-sample-service"></a><span data-ttu-id="84dff-132">Servicio de muestra WSStreamedHttpBinding </span><span class="sxs-lookup"><span data-stu-id="84dff-132">The WSStreamedHttpBinding Sample Service</span></span>

<span data-ttu-id="84dff-133">El servicio del ejemplo que utiliza `WSStreamedHttpBinding` se encuentra en el subdirectorio del servicio.</span><span class="sxs-lookup"><span data-stu-id="84dff-133">The sample service that uses `WSStreamedHttpBinding` is located in the service subdirectory.</span></span> <span data-ttu-id="84dff-134">La implementación de `OperationContract` utiliza `MemoryStream` para recuperar primero todos los datos de la secuencia de entrada antes de devolver `MemoryStream`.</span><span class="sxs-lookup"><span data-stu-id="84dff-134">The implementation of `OperationContract` uses a `MemoryStream` to first retrieve all data from the incoming stream before returning the `MemoryStream`.</span></span> <span data-ttu-id="84dff-135">El servicio de muestra está hospedado en Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="84dff-135">The sample service is hosted by Internet Information Services (IIS).</span></span>

```csharp
[ServiceContract]
public interface IStreamedEchoService
{
    [OperationContract]
    Stream Echo(Stream data);
}

public class StreamedEchoService : IStreamedEchoService
{
    public Stream Echo(Stream data)
    {
        MemoryStream dataStorage = new MemoryStream();
        byte[] byteArray = new byte[8192];
        int bytesRead = data.Read(byteArray, 0, 8192);
        while (bytesRead > 0)
        {
            dataStorage.Write(byteArray, 0, bytesRead);
            bytesRead = data.Read(byteArray, 0, 8192);
        }
        data.Close();
        dataStorage.Seek(0, SeekOrigin.Begin);

        return dataStorage;
    }
}
```

## <a name="the-wsstreamedhttpbinding-sample-client"></a><span data-ttu-id="84dff-136">Cliente de muestra WSStreamedHttpBinding </span><span class="sxs-lookup"><span data-stu-id="84dff-136">The WSStreamedHttpBinding Sample Client</span></span>

<span data-ttu-id="84dff-137">El cliente que se utiliza para interactuar con el servicio mediante `WSStreamedHttpBinding` se encuentra en el subdirectorio del cliente.</span><span class="sxs-lookup"><span data-stu-id="84dff-137">The client that is used to interact with the service using `WSStreamedHttpBinding` is located in the client subdirectory.</span></span> <span data-ttu-id="84dff-138">Dado que el certificado utilizado en este ejemplo es un certificado de prueba creado con Makecert. exe, se muestra una alerta de seguridad al intentar obtener acceso a una dirección HTTPS en el explorador como `https://localhost/servicemodelsamples/service.svc` .</span><span class="sxs-lookup"><span data-stu-id="84dff-138">Because the certificate used in this sample is a test certificate created with Makecert.exe, a security alert displays when you attempt to access an HTTPS address in your browser such as `https://localhost/servicemodelsamples/service.svc`.</span></span> <span data-ttu-id="84dff-139">Para permitir que el cliente WCF funcione con un certificado de prueba en contexto, se ha agregado código adicional al cliente para suprimir la alerta de seguridad.</span><span class="sxs-lookup"><span data-stu-id="84dff-139">To allow the WCF client to work with a test certificate in place, some additional code has been added to the client to suppress the security alert.</span></span> <span data-ttu-id="84dff-140">El código y la clase que lo acompaña no son necesarios cuando se usan certificados de producción.</span><span class="sxs-lookup"><span data-stu-id="84dff-140">The code and the accompanying class are not required when using production certificates.</span></span>

```csharp
// WARNING: This code is only required for test certificates such as those created by makecert. It is
// not recommended for production code.
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");
```
