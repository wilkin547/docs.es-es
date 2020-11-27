---
title: Configuración simplificada de los servicios de WCF
description: Aprenda a implementar y configurar un servicio y un cliente típicos con WCF. El servicio se comunica con un punto de conexión especificado en un archivo de configuración.
ms.date: 03/30/2017
ms.assetid: 1e39ec25-18a3-4fdc-b6a3-9dfafbd60112
ms.openlocfilehash: 087618d603ea1c7df75ab5383f6c95b781dca847
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96290028"
---
# <a name="simplified-configuration-for-wcf-services"></a><span data-ttu-id="4c0c3-104">Configuración simplificada de los servicios de WCF</span><span class="sxs-lookup"><span data-stu-id="4c0c3-104">Simplified Configuration for WCF Services</span></span>

<span data-ttu-id="4c0c3-105">Este ejemplo muestra cómo implementar y configurar un servicio y un cliente típicos con Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="4c0c3-105">This sample demonstrates how to implement and configure a typical service and client using Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="4c0c3-106">Este ejemplo es la base para obtener todos los otros ejemplos tecnológicos básicos.</span><span class="sxs-lookup"><span data-stu-id="4c0c3-106">This sample is the basis for all other basic technology samples.</span></span>  
  
 <span data-ttu-id="4c0c3-107">Este servicio, que expone un punto de conexión para comunicarse con el servicio, utiliza la configuración simplificada en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="4c0c3-107">This service, which exposes an endpoint for communicating with the service, uses the simplified configuration in .NET Framework 4.</span></span> <span data-ttu-id="4c0c3-108">Antes de .NET Framework 4, el punto de conexión se define normalmente en un archivo de configuración (Web.config), como se muestra en el siguiente código de configuración de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4c0c3-108">Prior to .NET Framework 4, the endpoint is typically defined in a configuration file (Web.config), as shown in the following example configuration code.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright ©) Microsoft Corporation.  All Rights Reserved. -->  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service name="Microsoft.Samples.GettingStarted.CalculatorService"  
               behaviorConfiguration="CalculatorServiceBehavior">  
        <endpoint address="" binding="basicHttpBinding" contract="ICalculator"/>  
        <endpoint address="mex" binding="mexHttpBinding" contract="IMetadataExchange"/>  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="4c0c3-109">En .NET Framework 4, el `<service>` elemento es opcional.</span><span class="sxs-lookup"><span data-stu-id="4c0c3-109">In .NET Framework 4, the `<service>` element is optional.</span></span> <span data-ttu-id="4c0c3-110">Cuando un servicio no define ningún punto de conexión, se agregan al servicio un punto de conexión para cada dirección base y el contrato implementado.</span><span class="sxs-lookup"><span data-stu-id="4c0c3-110">When a service does not define any endpoints, an endpoint for each base address and contract implemented are added to the service.</span></span> <span data-ttu-id="4c0c3-111">La dirección base se anexa al nombre del contrato para determinar el punto de conexión y el esquema de direcciones determina el enlace.</span><span class="sxs-lookup"><span data-stu-id="4c0c3-111">The base address is appended to the contract name to determine the endpoint and the binding is determined by the address scheme.</span></span> <span data-ttu-id="4c0c3-112">El siguiente ejemplo de código muestra un archivo de configuración simplificado.</span><span class="sxs-lookup"><span data-stu-id="4c0c3-112">The following code example demonstrates a simplified configuration file.</span></span> <span data-ttu-id="4c0c3-113">Tal y como se ha configurado, un cliente puede tener acceso al servicio `http://localhost/servicemodelsamples/service.svc` en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="4c0c3-113">As configured, the service can be accessed at `http://localhost/servicemodelsamples/service.svc` by a client on the same computer.</span></span> <span data-ttu-id="4c0c3-114">Para que los clientes en equipos remotos tengan acceso al servicio, se debe especificar un nombre de dominio completo en lugar del host local.</span><span class="sxs-lookup"><span data-stu-id="4c0c3-114">For clients on remote computers to access the service, a fully-qualified domain name must be specified instead of localhost.</span></span> <span data-ttu-id="4c0c3-115">El servicio no expone ningún metadato de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4c0c3-115">The service does not expose metadata by default.</span></span> <span data-ttu-id="4c0c3-116">Como tal, el servicio activa el comportamiento <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.</span><span class="sxs-lookup"><span data-stu-id="4c0c3-116">As such, the service turns on the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> behavior.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright © Microsoft Corporation.  All Rights Reserved. -->  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
### <a name="to-use-this-sample"></a><span data-ttu-id="4c0c3-117">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="4c0c3-117">To use this sample</span></span>  
  
1. <span data-ttu-id="4c0c3-118">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="4c0c3-118">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="4c0c3-119">Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="4c0c3-119">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="4c0c3-120">Ejecute el ejemplo siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="4c0c3-120">Run the sample by following these steps:</span></span>  
  
    1. <span data-ttu-id="4c0c3-121">Haga clic con el botón derecho en el proyecto de **servicio** y seleccione **establecer como proyecto de inicio** y presione **Ctrl + F5**.</span><span class="sxs-lookup"><span data-stu-id="4c0c3-121">Right click the **Service** project and select **Set as StartUp project**, then press **Ctrl+F5**.</span></span>  
  
    2. <span data-ttu-id="4c0c3-122">Espere a que el resultado de la consola confirme que el servicio está activo y en ejecución.</span><span class="sxs-lookup"><span data-stu-id="4c0c3-122">Wait for the console output confirming that the service is up and running.</span></span>  
  
    3. <span data-ttu-id="4c0c3-123">Haga clic con el botón derecho en el proyecto de **cliente** y seleccione **establecer como proyecto de inicio** y presione **Ctrl + F5**.</span><span class="sxs-lookup"><span data-stu-id="4c0c3-123">Right click the **Client** project and select **Set as StartUp project**, then press **Ctrl+F5**.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="4c0c3-124">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="4c0c3-124">The samples may already be installed on your computer.</span></span> <span data-ttu-id="4c0c3-125">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="4c0c3-125">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="4c0c3-126">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="4c0c3-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4c0c3-127">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="4c0c3-127">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigSimplificationIn40`  
  
## <a name="see-also"></a><span data-ttu-id="4c0c3-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c0c3-128">See also</span></span>

- <span data-ttu-id="4c0c3-129">[Ejemplos de administración de AppFabric](/previous-versions/appfabric/ff383405(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="4c0c3-129">[AppFabric Management Samples](/previous-versions/appfabric/ff383405(v=azure.10))</span></span>
- [<span data-ttu-id="4c0c3-130">Configuración simplificada</span><span class="sxs-lookup"><span data-stu-id="4c0c3-130">Simplified Configuration</span></span>](../simplified-configuration.md)
