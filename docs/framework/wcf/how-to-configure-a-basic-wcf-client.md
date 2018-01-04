---
title: "Configuración de un cliente básico de Windows Communication Foundation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF clients [WCF], configuring
ms.assetid: d067b86d-afb0-47bf-94f6-45180a3d8d78
caps.latest.revision: "47"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 377a67edb37ada5c9e1b022d50a4718b5740afd8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-configure-a-basic-windows-communication-foundation-client"></a><span data-ttu-id="e2885-102">Configuración de un cliente básico de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="e2885-102">How to: Configure a Basic Windows Communication Foundation Client</span></span>
<span data-ttu-id="e2885-103">Es la quinta de las seis tareas necesarias para crear una aplicación básica de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2885-103">This is the fifth of six tasks required to create a basic [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] application.</span></span> <span data-ttu-id="e2885-104">Para obtener información general de las seis de las tareas, consulte la [Tutorial de introducción](../../../docs/framework/wcf/getting-started-tutorial.md) tema.</span><span class="sxs-lookup"><span data-stu-id="e2885-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>  
  
 <span data-ttu-id="e2885-105">Este archivo de configuración de cliente que se ha generado mediante la funcionalidad Agregar referencia de servicio de disuccess de tema [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] o [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="e2885-105">This topic disuccess the client configuration file that was generated using the Add Service Reference functionality of [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] or the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="e2885-106">La configuración del cliente consiste en especificar el punto de conexión que utiliza el cliente para obtener acceso al servicio.</span><span class="sxs-lookup"><span data-stu-id="e2885-106">Configuring the client consists of specifying the endpoint that the client uses to access the service.</span></span> <span data-ttu-id="e2885-107">Un extremo tiene una dirección, un enlace y un contrato y cada uno de estos elementos debe especificarse en el proceso de configuración del cliente.</span><span class="sxs-lookup"><span data-stu-id="e2885-107">An endpoint has an address, a binding and a contract, and each of these must be specified in the process of configuring the client.</span></span>  
  
### <a name="to-configure-a-windows-communication-foundation-client"></a><span data-ttu-id="e2885-108">Configuración de un cliente de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="e2885-108">To configure a Windows Communication Foundation client</span></span>  
  
1.  <span data-ttu-id="e2885-109">Abra el archivo de configuración generado (App.config) del proyecto GettingStartedClient.</span><span class="sxs-lookup"><span data-stu-id="e2885-109">Open the generated configuration file (App.config) from the GettingStartedClient project.</span></span> <span data-ttu-id="e2885-110">El siguiente ejemplo es una vista del archivo de configuración generado.</span><span class="sxs-lookup"><span data-stu-id="e2885-110">The following example is a view of the generated configuration file.</span></span> <span data-ttu-id="e2885-111">En el [ \<system.serviceModel >](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) sección, busque la [ \<extremo >](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017) elemento.</span><span class="sxs-lookup"><span data-stu-id="e2885-111">Under the [\<system.serviceModel>](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) section, find the [\<endpoint>](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017) element.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
        <startup>   
          <!-- specifies the version of WCF to use-->  
            <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5,Profile=Client" />  
        </startup>  
        <system.serviceModel>  
            <bindings>  
                <!-- Uses wsHttpBinding-->  
                <wsHttpBinding>  
                    <binding name="WSHttpBinding_ICalculator" />  
                </wsHttpBinding>  
            </bindings>  
            <client>  
                <!-- specifies the endpoint to use when calling the service -->  
                <endpoint address="http://localhost:8000/ServiceModelSamples/Service/CalculatorService"  
                    binding="wsHttpBinding" bindingConfiguration="WSHttpBinding_ICalculator"  
                    contract="ServiceReference1.ICalculator" name="WSHttpBinding_ICalculator">  
                    <identity>  
                        <userPrincipalName value="migree@redmond.corp.microsoft.com" />  
                    </identity>  
                </endpoint>  
            </client>  
        </system.serviceModel>  
    </configuration>   
    ```  
  
     <span data-ttu-id="e2885-112">Este ejemplo configura el punto de conexión que usa el cliente para tener acceso al servicio que se ubica en la siguiente dirección: http://localhost:8000/ServiceModelSamples/Service/CalculatorService</span><span class="sxs-lookup"><span data-stu-id="e2885-112">This example configures the endpoint that the client uses to access the service that is located at the following address: http://localhost:8000/ServiceModelSamples/Service/CalculatorService</span></span>  
  
     <span data-ttu-id="e2885-113">El elemento de extremo especifica que el contrato de servicio de `ServiceReference1.ICalculator` se usa para la comunicación entre el cliente y el servicio de WCF.</span><span class="sxs-lookup"><span data-stu-id="e2885-113">The endpoint element specifies that the `ServiceReference1.ICalculator` service contract is used for communication between the WCF client and service.</span></span> <span data-ttu-id="e2885-114">Se configura el canal WCF con los proporcionados por el sistema <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`>.</span><span class="sxs-lookup"><span data-stu-id="e2885-114">The WCF channel is configured with the system-provided <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`>.</span></span> <span data-ttu-id="e2885-115">Este contrato se generó mediante Agregar referencia de servicio en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e2885-115">This contract was generated by using Add Service Reference in Visual Studio.</span></span> <span data-ttu-id="e2885-116">Es básicamente una copia del contrato que se definió en el proyecto GettingStartedLib.</span><span class="sxs-lookup"><span data-stu-id="e2885-116">It is essentially a copy of the contract that was defined in the GettingStartedLib project.</span></span> <span data-ttu-id="e2885-117">El <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> enlace especifica HTTP como el transporte, seguridad interoperable y otros detalles de configuración.</span><span class="sxs-lookup"><span data-stu-id="e2885-117">The <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> binding specifies HTTP as the transport, interoperable security, and other configuration details.</span></span>  
  
2.  [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="e2885-118">cómo usar el cliente generado con esta configuración, consulte [Cómo: usar un cliente](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="e2885-118"> how to use the generated client with this configuration, see [How to: Use a Client](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2885-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2885-119">See Also</span></span>  
 [<span data-ttu-id="e2885-120">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="e2885-120">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="e2885-121">Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="e2885-121">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [<span data-ttu-id="e2885-122">Cómo crear un cliente</span><span class="sxs-lookup"><span data-stu-id="e2885-122">How to: Create a Client</span></span>](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [<span data-ttu-id="e2885-123">Introducción</span><span class="sxs-lookup"><span data-stu-id="e2885-123">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [<span data-ttu-id="e2885-124">Probar internamente</span><span class="sxs-lookup"><span data-stu-id="e2885-124">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)
