---
description: 'Más información acerca de: uso de puntos de conexión estándar'
title: Uso de extremos estándar
ms.date: 03/30/2017
ms.assetid: ecd6a62f-9619-4778-a497-6f888087a9ea
ms.openlocfilehash: 804fdd84d3f6ff6f961aed81e8bd14cf8c43063c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99685418"
---
# <a name="usage-of-standard-endpoints"></a><span data-ttu-id="9c287-103">Uso de extremos estándar</span><span class="sxs-lookup"><span data-stu-id="9c287-103">Usage of Standard Endpoints</span></span>

<span data-ttu-id="9c287-104">Este ejemplo muestra cómo utilizar los puntos de conexión estándar en archivos de configuración de servicio.</span><span class="sxs-lookup"><span data-stu-id="9c287-104">This sample demonstrates how to use standard endpoints in service configuration files.</span></span> <span data-ttu-id="9c287-105">Un punto de conexión estándar permite al usuario simplificar las definiciones de punto de conexión utilizando una sola propiedad para describir una dirección, enlace y combinación de contratos con propiedades adicionales asocias.</span><span class="sxs-lookup"><span data-stu-id="9c287-105">A standard endpoint allows the user to simplify endpoint definitions by using a single property to describe an address, binding and contract combination with additional properties associated to it.</span></span> <span data-ttu-id="9c287-106">En este ejemplo se muestra cómo definir e implementar un punto de conexión estándar personalizado y cómo definir propiedades concretas en él.</span><span class="sxs-lookup"><span data-stu-id="9c287-106">This sample demonstrates how to define and implement a custom standard endpoint and how to define specific properties in the endpoint.</span></span>

## <a name="sample-details"></a><span data-ttu-id="9c287-107">Detalles del ejemplo</span><span class="sxs-lookup"><span data-stu-id="9c287-107">Sample Details</span></span>

<span data-ttu-id="9c287-108">Los puntos de conexión de servicio se pueden especificar proporcionando tres parámetros: dirección, enlace y contrato.</span><span class="sxs-lookup"><span data-stu-id="9c287-108">Service endpoints can be specified by supplying three parameters: address, binding and contract.</span></span> <span data-ttu-id="9c287-109">Otros parámetros que se pueden proporcionar son la configuración de comportamiento, los encabezados, el URI de escucha, etc.</span><span class="sxs-lookup"><span data-stu-id="9c287-109">Other parameters that can be supplied include behavior configuration, headers, listen URI, and so on.</span></span> <span data-ttu-id="9c287-110">En algunos casos, con una dirección o con todas, los enlaces y contratos tienen valores que no pueden cambiar.</span><span class="sxs-lookup"><span data-stu-id="9c287-110">In some cases, any or all of addresses, bindings and contracts have values that cannot change.</span></span> <span data-ttu-id="9c287-111">Por esta razón, es posible utilizar puntos de conexión estándar.</span><span class="sxs-lookup"><span data-stu-id="9c287-111">For this reason, it is possible to use standard endpoints.</span></span> <span data-ttu-id="9c287-112">Algunos ejemplos de tales puntos de conexión incluyen los de intercambio de metadatos y los de detección.</span><span class="sxs-lookup"><span data-stu-id="9c287-112">Some examples of such endpoints include metadata exchange endpoints and discovery endpoints.</span></span> <span data-ttu-id="9c287-113">Los extremos estándar también mejoran la capacidad de uso al permitir la configuración de los extremos de servicio sin tener que proporcionar información de naturaleza fija o crear sus propios extremos estándar, por ejemplo proporcionando un conjunto razonable de valores predeterminados y, por tanto, reduciendo el nivel de detalle de los archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="9c287-113">Standard endpoints also improve usability by allowing configuration of service endpoints without having to provide information of a fixed nature or to create their own standard endpoints, for example to improve usability by supplying a reasonable set of default values and thus reducing the verbosity of configuration files.</span></span>

<span data-ttu-id="9c287-114">Este ejemplo está compuesto de dos proyectos: el servicio que define dos extremos estándar y el cliente que comunica con el servicio.</span><span class="sxs-lookup"><span data-stu-id="9c287-114">This sample consists of two projects: the service that defines two standard endpoints and the client that communicates with the service.</span></span> <span data-ttu-id="9c287-115">La manera en que los puntos de conexión estándar se definen para el servicio en el archivo de configuración se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9c287-115">The way the standard endpoints are defined for the service in the configuration file is show in the following example.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.serviceModel>
    <extensions>
      <endpointExtensions>
        <add name="customEndpoint" type="Microsoft.Samples.StandardEndpoints.CustomEndpointCollectionElement, service" />
      </endpointExtensions>
    </extensions>
    <services>
      <service name="Microsoft.Samples.StandardEndpoints.CalculatorService">
        <endpoint address="http://localhost:8000/Samples/Service.svc/customEndpoint" contract="Microsoft.Samples.StandardEndpoints.ICalculator" kind="customEndpoint" />
        <endpoint kind="mexEndpoint" />
      </service>
    </services>
    <behaviors>
      <serviceBehaviors>
        <behavior>
          <serviceMetadata httpGetEnabled="True"/>
        </behavior>
      </serviceBehaviors>
    </behaviors>
    <standardEndpoints>
      <customEndpoint>
        <standardEndpoint property="True" />
      </customEndpoint>
    </standardEndpoints>
  </system.serviceModel>
</configuration>
```

<span data-ttu-id="9c287-116">El primer punto de conexión definido para el servicio es de tipo `customEndpoint`, cuya definición se puede ver en la sección `<standardEndpoints>`, en la que la propiedad `property` recibe el valor `true`.</span><span class="sxs-lookup"><span data-stu-id="9c287-116">The first endpoint defined for the service is of kind `customEndpoint`, whose definition can be seen in the `<standardEndpoints>` section, in which the property `property` is given the value `true`.</span></span> <span data-ttu-id="9c287-117">Este es el caso de un extremo personalizado con una nueva propiedad.</span><span class="sxs-lookup"><span data-stu-id="9c287-117">This is the case of an endpoint customized with a new property.</span></span> <span data-ttu-id="9c287-118">El segundo punto de conexión corresponde a un punto de conexión de metadatos en el que los valores de la dirección, el enlace y el contrato son fijos.</span><span class="sxs-lookup"><span data-stu-id="9c287-118">The second endpoint corresponds to a metadata endpoint, in which the values for address, binding and contract are fixed.</span></span>

<span data-ttu-id="9c287-119">Para definir el elemento de punto de conexión estándar, se debe crear una clase que se derive de `StandardEndpointElement`.</span><span class="sxs-lookup"><span data-stu-id="9c287-119">To define the standard endpoint element, a class that derives from `StandardEndpointElement` must be created.</span></span> <span data-ttu-id="9c287-120">En el caso de este ejemplo, la clase `CustomEndpointElement` se ha definido como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9c287-120">In the case of this sample, the `CustomEndpointElement` class has been defined as shown in the following example.</span></span>

```csharp
public class CustomEndpointElement : StandardEndpointElement
{
    public bool Property
    {
        get { return (bool)base["property"]; }
        set { base["property"] = value; }
    }

    protected override ConfigurationPropertyCollection Properties
    {
        get
        {
            ConfigurationPropertyCollection properties = base.Properties;
            properties.Add(new ConfigurationProperty("property", typeof(bool), false, ConfigurationPropertyOptions.None));
            return properties;
        }
    }

    protected override Type EndpointType
    {
        get { return typeof(CustomEndpoint); }
    }

    protected override ServiceEndpoint CreateServiceEndpoint(ContractDescription contract)
    {
        return new CustomEndpoint();
    }

    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ServiceEndpointElement serviceEndpointElement)
    {
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;
        customEndpoint.Property = this.Property;
    }

    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ChannelEndpointElement channelEndpointElement)
    {
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;
        customEndpoint.Property = this.Property;
    }

    protected override void OnInitializeAndValidate(ServiceEndpointElement serviceEndpointElement)
    {
    }

    protected override void OnInitializeAndValidate(ChannelEndpointElement channelEndpointElement)
    {
    }
}
```

<span data-ttu-id="9c287-121">En la función `CreateServiceEndpoint`, se crea un objeto `CustomEndpoint`.</span><span class="sxs-lookup"><span data-stu-id="9c287-121">In the `CreateServiceEndpoint` function, a `CustomEndpoint` object is created.</span></span> <span data-ttu-id="9c287-122">Su definición se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9c287-122">Its definition is shown in the following example:</span></span>

```csharp
public class CustomEndpoint : ServiceEndpoint
{
    public CustomEndpoint()
        : this(string.Empty)
    {
    }

    public CustomEndpoint(string address)
        : this(address, ContractDescription.GetContract(typeof(ICalculator)))
    {
    }

    public CustomEndpoint(string address, ContractDescription contract)
        : base(contract)
    {
        this.Binding = new BasicHttpBinding();
        this.IsSystemEndpoint = false;
    }

    public bool Property
    {
        get;
        set;
    }
}
```

 <span data-ttu-id="9c287-123">Para realizar la comunicación entre el servicio y el cliente, se crea una referencia del servicio en el cliente para el servicio.</span><span class="sxs-lookup"><span data-stu-id="9c287-123">To perform the communication between service and client, a service reference is created in the client to the service.</span></span> <span data-ttu-id="9c287-124">Cuando el ejemplo se compila y ejecuta, el servicio se ejecuta y el cliente se comunica con él.</span><span class="sxs-lookup"><span data-stu-id="9c287-124">When the sample is built and executed, the service executes and the client communicates with it.</span></span> <span data-ttu-id="9c287-125">Observe que la referencia del servicio debería actualizarse cada vez que hay algún cambio en el servicio.</span><span class="sxs-lookup"><span data-stu-id="9c287-125">Note that the service reference should be updated every time there is some change in the service.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="9c287-126">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="9c287-126">To use this sample</span></span>

1. <span data-ttu-id="9c287-127">Con Visual Studio 2012, abra el archivo StandardEndpoints. sln.</span><span class="sxs-lookup"><span data-stu-id="9c287-127">Using Visual Studio 2012, open the StandardEndpoints.sln file.</span></span>

2. <span data-ttu-id="9c287-128">Habilite varios proyectos para iniciarse.</span><span class="sxs-lookup"><span data-stu-id="9c287-128">Enable multiple projects to start up.</span></span>

    1. <span data-ttu-id="9c287-129">En **Explorador de soluciones**, haga clic con el botón secundario en la solución puntos de conexión estándar y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="9c287-129">In **Solution Explorer**, right-click the Standard Endpoints solution and then select **Properties**.</span></span>

    2. <span data-ttu-id="9c287-130">En **propiedades comunes**, seleccione **proyecto de inicio** y, a continuación, haga clic en **proyectos de inicio múltiples**.</span><span class="sxs-lookup"><span data-stu-id="9c287-130">In **Common Properties**, select **Startup Project**, and then click **Multiple Startup Projects**.</span></span>

    3. <span data-ttu-id="9c287-131">Mueva el proyecto de servicio al principio de la lista, con la **acción** establecida en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="9c287-131">Move the Service project to the beginning of the list, with the **Action** set to **Start**.</span></span>

    4. <span data-ttu-id="9c287-132">Mueva el proyecto de cliente después del proyecto de servicio, también con la **acción** establecida en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="9c287-132">Move the Client project after the Service project, also with the **Action** set to **Start**.</span></span>

         <span data-ttu-id="9c287-133">De esta forma se especifica que el proyecto Cliente se ejecute después del proyecto Servicio.</span><span class="sxs-lookup"><span data-stu-id="9c287-133">This specifies that the Client project is executed after the Service project.</span></span>

3. <span data-ttu-id="9c287-134">Presione F5 para ejecutar la solución.</span><span class="sxs-lookup"><span data-stu-id="9c287-134">To run the solution, press F5.</span></span>

> [!NOTE]
> <span data-ttu-id="9c287-135">Si estos pasos no funcionan, asegúrese de que el entorno se haya configurado correctamente mediante los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="9c287-135">If these steps don't work, then make sure that your environment has been properly set up, using the following steps:</span></span>
>
> 1. <span data-ttu-id="9c287-136">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9c287-136">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>
> 2. <span data-ttu-id="9c287-137">Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9c287-137">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>
> 3. <span data-ttu-id="9c287-138">Para ejecutar el ejemplo en una o varias configuraciones de equipo, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9c287-138">To run the sample in a single or multiple computer configurations, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9c287-139">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="9c287-139">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9c287-140">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="9c287-140">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="9c287-141">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="9c287-141">If this directory doesn't exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9c287-142">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="9c287-142">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\StandardEndpoints`
