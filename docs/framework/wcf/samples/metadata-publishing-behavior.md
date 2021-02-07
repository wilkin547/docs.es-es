---
description: 'Más información sobre: comportamiento de publicación de metadatos'
title: Comportamiento de publicación de metadatos
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, metadata publishing sample
- Metadata Publishing Behaviors Sample [Windows Communication Foundation]
ms.assetid: 78c13633-d026-4814-910e-1c801cffdac7
ms.openlocfilehash: 13e52e5f2a8d301eac3100cbf2350cc5a089aa34
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99752247"
---
# <a name="metadata-publishing-behavior"></a><span data-ttu-id="87ea9-103">Comportamiento de publicación de metadatos</span><span class="sxs-lookup"><span data-stu-id="87ea9-103">Metadata Publishing Behavior</span></span>

<span data-ttu-id="87ea9-104">El ejemplo de comportamiento de publicación de metadatos muestra cómo controlar las características de publicación de metadatos de un servicio.</span><span class="sxs-lookup"><span data-stu-id="87ea9-104">The Metadata Publishing Behavior sample demonstrates how to control the metadata publishing features of a service.</span></span> <span data-ttu-id="87ea9-105">Para evitar la revelación involuntaria de metadatos de servicio potencialmente confidenciales, la configuración predeterminada de los servicios Windows Communication Foundation (WCF) deshabilita la publicación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="87ea9-105">To prevent unintentional disclosure of potentially sensitive service metadata, the default configuration for Windows Communication Foundation (WCF) services disables metadata publishing.</span></span> <span data-ttu-id="87ea9-106">Este comportamiento es seguro de forma predeterminada, pero también quiere decir que no puede usar una herramienta de importación de metadatos (como Svcutil.exe) Para compilar el código de cliente necesario para llamar al servicio a menos que el comportamiento de publicación de metadatos del servicio se habilite de manera explícita en la configuración.</span><span class="sxs-lookup"><span data-stu-id="87ea9-106">This behavior is secure by default, but also means that you cannot use a metadata import tool (such as Svcutil.exe) to generate the client code required to call the service unless the service’s metadata publishing behavior is explicitly enabled in configuration.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="87ea9-107">Para mostrar más claridad, este ejemplo muestra cómo crear un punto de conexión de publicación de metadatos no se seguros.</span><span class="sxs-lookup"><span data-stu-id="87ea9-107">For clarity, this sample demonstrates how to create an unsecured metadata publishing endpoint.</span></span> <span data-ttu-id="87ea9-108">Tales extremos pueden estar disponibles para los consumidores anónimos no autenticados y se debe tener cuidado antes de implementar tales extremos para garantizar que la revelación pública de un metadato del servicio sea la adecuada.</span><span class="sxs-lookup"><span data-stu-id="87ea9-108">Such endpoints are potentially available to anonymous unauthenticated consumers and care must be taken before deploying such endpoints to ensure that publicly disclosing a service’s metadata is appropriate.</span></span> <span data-ttu-id="87ea9-109">Vea el ejemplo de [extremo de metadatos seguro personalizado](custom-secure-metadata-endpoint.md) para obtener un ejemplo que protege un punto de conexión de metadatos.</span><span class="sxs-lookup"><span data-stu-id="87ea9-109">See the [Custom Secure Metadata Endpoint](custom-secure-metadata-endpoint.md) sample for a sample that secures a metadata endpoint.</span></span>  
  
 <span data-ttu-id="87ea9-110">El ejemplo se basa en el [Introducción](getting-started-sample.md), que implementa el `ICalculator` contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="87ea9-110">The sample is based on the [Getting Started](getting-started-sample.md), which implements the `ICalculator` service contract.</span></span> <span data-ttu-id="87ea9-111">En este ejemplo, el cliente es una aplicación de consola (.exe) y los Servicios de Internet Information Server (IIS) hospedan el servicio.</span><span class="sxs-lookup"><span data-stu-id="87ea9-111">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="87ea9-112">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="87ea9-112">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="87ea9-113">Para que un servicio exponga los metadatos, se debe configurar <xref:System.ServiceModel.Description.ServiceMetadataBehavior> en el servicio.</span><span class="sxs-lookup"><span data-stu-id="87ea9-113">For a service to expose metadata, the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> must be configured on the service.</span></span> <span data-ttu-id="87ea9-114">Cuando este comportamiento está presente, puede publicar los metadatos configurando un extremo para exponer el contrato <xref:System.ServiceModel.Description.IMetadataExchange> como una implementación de un protocolo WS-MetadataExchange (MEX).</span><span class="sxs-lookup"><span data-stu-id="87ea9-114">When this behavior is present, you can publish metadata by configuring an endpoint to expose the <xref:System.ServiceModel.Description.IMetadataExchange> contract as an implementation of a WS-MetadataExchange (MEX) protocol.</span></span> <span data-ttu-id="87ea9-115">Para su comodidad, se ha proporcionado al contrato el nombre de configuración abreviado de "IMetadataExchange."</span><span class="sxs-lookup"><span data-stu-id="87ea9-115">As a convenience, this contract has been given the abbreviated configuration name of "IMetadataExchange".</span></span> <span data-ttu-id="87ea9-116">Este ejemplo utiliza `mexHttpBinding`, que es un enlace estándar de conveniencia que es equivalente a `wsHttpBinding` con el modo de seguridad establecido en `None`.</span><span class="sxs-lookup"><span data-stu-id="87ea9-116">This sample uses the `mexHttpBinding`, which is a convenience standard binding that is equivalent to the `wsHttpBinding` with the security mode set to `None`.</span></span> <span data-ttu-id="87ea9-117">Se utiliza una dirección relativa de "Mex" en el punto de conexión, que cuando se resuelve con la dirección base de los servicios, da como resultado una dirección de extremo de `http://localhost/servicemodelsamples/service.svc/mex` .</span><span class="sxs-lookup"><span data-stu-id="87ea9-117">A relative address of "mex" is used in the endpoint, which when resolved against the services base address results in an endpoint address of `http://localhost/servicemodelsamples/service.svc/mex`.</span></span> <span data-ttu-id="87ea9-118">A continuación, se muestra la configuración del comportamiento:</span><span class="sxs-lookup"><span data-stu-id="87ea9-118">The following shows the behavior configuration:</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <!-- The serviceMetadata behavior publishes metadata through   
           the IMetadataExchange contract. When this behavior is   
           present, you can expose this contract through an endpoint   
           as shown below. Setting httpGetEnabled to true publishes   
           the service's WSDL at the <baseaddress>?wsdl, for example,  
           http://localhost/servicemodelsamples/service.svc?wsdl -->  
      <serviceMetadata httpGetEnabled="True"/>  
      <serviceDebug includeExceptionDetailInFaults="False" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="87ea9-119">A continuación, se muestra el punto de conexión de MEX.</span><span class="sxs-lookup"><span data-stu-id="87ea9-119">The following shows the MEX endpoint.</span></span>  
  
```xml  
<!-- the MEX endpoint is exposed at   
     http://localhost/servicemodelsamples/service.svc/mex   
     To expose the IMetadataExchange contract, you   
     must enable the serviceMetadata behavior as demonstrated                           
     previously. -->  
<endpoint address="mex"  
          binding="mexHttpBinding"  
          contract="IMetadataExchange" />  
```  
  
 <span data-ttu-id="87ea9-120">Este ejemplo establece la propiedad <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> en `true`, que también expone los metadatos del servicio mediante HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="87ea9-120">This sample sets the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> property to `true`, which also exposes the service's metadata using HTTP GET.</span></span> <span data-ttu-id="87ea9-121">Para habilitar un punto de conexión de metadatos HTTP GET, el servicio debe tener una dirección base HTTP.</span><span class="sxs-lookup"><span data-stu-id="87ea9-121">To enable an HTTP GET metadata endpoint, the service must have an HTTP base address.</span></span> <span data-ttu-id="87ea9-122">Se utiliza `?wsdl` de la cadena de consulta en la dirección base del servicio para tener acceso a los metadatos.</span><span class="sxs-lookup"><span data-stu-id="87ea9-122">The query string `?wsdl` is used on the base address of the service to access the metadata.</span></span> <span data-ttu-id="87ea9-123">Por ejemplo, para ver el WSDL del servicio en un explorador Web, usaría la dirección `http://localhost/servicemodelsamples/service.svc?wsdl` .</span><span class="sxs-lookup"><span data-stu-id="87ea9-123">For example, to see the WSDL for the service in a Web browser you would use the address `http://localhost/servicemodelsamples/service.svc?wsdl`.</span></span> <span data-ttu-id="87ea9-124">De manera alternativa, puede usar este comportamiento para exponer metadatos sobre HTTPS estableciendo <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="87ea9-124">Alternatively, you can use this behavior to expose metadata over HTTPS by setting <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> to `true`.</span></span> <span data-ttu-id="87ea9-125">Esto requiere una dirección base HTTPS.</span><span class="sxs-lookup"><span data-stu-id="87ea9-125">This requires an HTTPS base address.</span></span>  
  
 <span data-ttu-id="87ea9-126">Para tener acceso al punto de conexión MEX del servicio, use la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="87ea9-126">To access the service's MEX endpoint use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
 `svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /out:generatedClient.cs`  
  
 <span data-ttu-id="87ea9-127">Esto genera un cliente basado en los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="87ea9-127">This generates a client based on the service's metadata.</span></span>  
  
 <span data-ttu-id="87ea9-128">Para tener acceso a los metadatos del servicio mediante HTTP GET, apunte el explorador a `http://localhost/servicemodelsamples/service.svc?wsdl` .</span><span class="sxs-lookup"><span data-stu-id="87ea9-128">To access the service's metadata using HTTP GET, point your browser to `http://localhost/servicemodelsamples/service.svc?wsdl`.</span></span>  
  
 <span data-ttu-id="87ea9-129">Si quita este comportamiento e intenta abrir el servicio, obtendrá una excepción.</span><span class="sxs-lookup"><span data-stu-id="87ea9-129">If you remove this behavior and try to open the service you get an exception.</span></span> <span data-ttu-id="87ea9-130">Este error se produce porque sin el comportamiento, el extremo configurado con el contrato `IMetadataExchange` no tiene ninguna implementación.</span><span class="sxs-lookup"><span data-stu-id="87ea9-130">This error occurs because without the behavior, the endpoint configured with the `IMetadataExchange` contract has no implementation.</span></span>  
  
 <span data-ttu-id="87ea9-131">Si establece `HttpGetEnabled` en `false`, ve la página de ayuda de CalculatorService en lugar de ver los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="87ea9-131">If you set `HttpGetEnabled` to `false`, you see the CalculatorService help page instead of seeing the service's metadata.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="87ea9-132">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="87ea9-132">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="87ea9-133">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="87ea9-133">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="87ea9-134">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="87ea9-134">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="87ea9-135">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="87ea9-135">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="87ea9-136">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="87ea9-136">The samples may already be installed on your machine.</span></span> <span data-ttu-id="87ea9-137">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="87ea9-137">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="87ea9-138">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="87ea9-138">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="87ea9-139">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="87ea9-139">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Metadata`  
