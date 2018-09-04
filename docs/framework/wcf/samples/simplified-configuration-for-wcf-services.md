---
title: Configuración simplificada de los servicios de WCF
ms.date: 03/30/2017
ms.assetid: 1e39ec25-18a3-4fdc-b6a3-9dfafbd60112
ms.openlocfilehash: ebdf7ab62676bb0c8ac99a5335a3047fcdd5a9b3
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43500718"
---
# <a name="simplified-configuration-for-wcf-services"></a><span data-ttu-id="6b971-102">Configuración simplificada de los servicios de WCF</span><span class="sxs-lookup"><span data-stu-id="6b971-102">Simplified Configuration for WCF Services</span></span>
<span data-ttu-id="6b971-103">Este ejemplo muestra cómo implementar y configurar un servicio típico y el cliente con Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="6b971-103">This sample demonstrates how to implement and configure a typical service and client using Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="6b971-104">Este ejemplo es la base para obtener todos los otros ejemplos tecnológicos básicos.</span><span class="sxs-lookup"><span data-stu-id="6b971-104">This sample is the basis for all other basic technology samples.</span></span>  
  
 <span data-ttu-id="6b971-105">Este servicio, que expone un extremo para comunicar con el servicio, utiliza la configuración simplificada en [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6b971-105">This service, which exposes an endpoint for communicating with the service, uses the simplified configuration in [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)].</span></span> <span data-ttu-id="6b971-106">Antes de [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)], el extremo se solía definir en un archivo de configuración (Web.config), como se muestra en el siguiente código de configuración de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="6b971-106">Prior to [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)], the endpoint is typically defined in a configuration file (Web.config), as shown in the following example configuration code.</span></span>  
  
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
  
 <span data-ttu-id="6b971-107">En [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)], el elemento `<service>` es opcional.</span><span class="sxs-lookup"><span data-stu-id="6b971-107">In [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)], the `<service>` element is optional.</span></span> <span data-ttu-id="6b971-108">Cuando un servicio no define ningún punto de conexión, se agregan al servicio un punto de conexión para cada dirección base y el contrato implementado.</span><span class="sxs-lookup"><span data-stu-id="6b971-108">When a service does not define any endpoints, an endpoint for each base address and contract implemented are added to the service.</span></span> <span data-ttu-id="6b971-109">La dirección base se anexa al nombre del contrato para determinar el extremo y el esquema de direcciones determina el enlace.</span><span class="sxs-lookup"><span data-stu-id="6b971-109">The base address is appended to the contract name to determine the endpoint and the binding is determined by the address scheme.</span></span> <span data-ttu-id="6b971-110">El siguiente ejemplo de código muestra un archivo de configuración simplificado.</span><span class="sxs-lookup"><span data-stu-id="6b971-110">The following code example demonstrates a simplified configuration file.</span></span> <span data-ttu-id="6b971-111">Como se ha configurado, puede tener acceso al servicio en http://localhost/servicemodelsamples/service.svc por un cliente en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="6b971-111">As configured, the service can be accessed at http://localhost/servicemodelsamples/service.svc by a client on the same computer.</span></span> <span data-ttu-id="6b971-112">Para que los clientes en equipos remotos tengan acceso al servicio, se debe especificar un nombre de dominio completo en lugar del host local.</span><span class="sxs-lookup"><span data-stu-id="6b971-112">For clients on remote computers to access the service, a fully-qualified domain name must be specified instead of localhost.</span></span> <span data-ttu-id="6b971-113">El servicio no expone ningún metadato de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6b971-113">The service does not expose metadata by default.</span></span> <span data-ttu-id="6b971-114">Como tal, el servicio activa el comportamiento <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.</span><span class="sxs-lookup"><span data-stu-id="6b971-114">As such, the service turns on the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> behavior.</span></span>  
  
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
  
### <a name="to-use-this-sample"></a><span data-ttu-id="6b971-115">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="6b971-115">To use this sample</span></span>  
  
1.  <span data-ttu-id="6b971-116">Asegúrese de que ha realizado la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6b971-116">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="6b971-117">Para compilar la solución, siga las instrucciones de [compilar los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6b971-117">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="6b971-118">Ejecute el ejemplo siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6b971-118">Run the sample by following these steps:</span></span>  
  
    1.  <span data-ttu-id="6b971-119">Haga clic en el **servicio** del proyecto y seleccione **establecer como proyecto de inicio**, a continuación, presione **CTRL+F5**.</span><span class="sxs-lookup"><span data-stu-id="6b971-119">Right click the **Service** project and select **Set as StartUp project**, then press **Ctrl+F5**.</span></span>  
  
    2.  <span data-ttu-id="6b971-120">Espere a que el resultado de la consola confirme que el servicio está activo y en ejecución.</span><span class="sxs-lookup"><span data-stu-id="6b971-120">Wait for the console output confirming that the service is up and running.</span></span>  
  
    3.  <span data-ttu-id="6b971-121">Haga clic en el **cliente** del proyecto y seleccione **establecer como proyecto de inicio**, a continuación, presione **CTRL+F5**.</span><span class="sxs-lookup"><span data-stu-id="6b971-121">Right click the **Client** project and select **Set as StartUp project**, then press **Ctrl+F5**.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6b971-122">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="6b971-122">The samples may already be installed on your computer.</span></span> <span data-ttu-id="6b971-123">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="6b971-123">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="6b971-124">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="6b971-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6b971-125">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="6b971-125">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigSimplificationIn40`  
  
## <a name="see-also"></a><span data-ttu-id="6b971-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b971-126">See Also</span></span>  
 [<span data-ttu-id="6b971-127">Ejemplos de administración de AppFabric</span><span class="sxs-lookup"><span data-stu-id="6b971-127">AppFabric Management Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193960)  
 [<span data-ttu-id="6b971-128">Configuración simplificada</span><span class="sxs-lookup"><span data-stu-id="6b971-128">Simplified Configuration</span></span>](../../../../docs/framework/wcf/simplified-configuration.md)
