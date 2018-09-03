---
title: Configuración de un cliente básico de Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- WCF clients [WCF], configuring
ms.assetid: d067b86d-afb0-47bf-94f6-45180a3d8d78
ms.openlocfilehash: 2866cbd5862bf55286fc771823488cf913863de2
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2018
ms.locfileid: "43466576"
---
# <a name="how-to-configure-a-basic-windows-communication-foundation-client"></a><span data-ttu-id="9d8ac-102">Configuración de un cliente básico de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="9d8ac-102">How to: Configure a Basic Windows Communication Foundation Client</span></span>
<span data-ttu-id="9d8ac-103">Esta es la quinta de las seis tareas necesarias para crear una aplicación básica de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="9d8ac-103">This is the fifth of six tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="9d8ac-104">Para obtener información general de las seis tareas, vea el tema [Tutorial de introducción](../../../docs/framework/wcf/getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="9d8ac-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>  
  
 <span data-ttu-id="9d8ac-105">Este tema describe el archivo de configuración de cliente que se ha generado mediante la funcionalidad Agregar referencia de servicio de [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] o [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="9d8ac-105">This topic discusses the client configuration file that was generated using the Add Service Reference functionality of [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] or the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="9d8ac-106">La configuración del cliente consiste en especificar el punto de conexión que utiliza el cliente para obtener acceso al servicio.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-106">Configuring the client consists of specifying the endpoint that the client uses to access the service.</span></span> <span data-ttu-id="9d8ac-107">Un extremo tiene una dirección, un enlace y un contrato y cada uno de estos elementos debe especificarse en el proceso de configuración del cliente.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-107">An endpoint has an address, a binding and a contract, and each of these must be specified in the process of configuring the client.</span></span>  
  
### <a name="to-configure-a-windows-communication-foundation-client"></a><span data-ttu-id="9d8ac-108">Configuración de un cliente de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="9d8ac-108">To configure a Windows Communication Foundation client</span></span>  
  
1.  <span data-ttu-id="9d8ac-109">Abra el archivo de configuración generado (App.config) del proyecto GettingStartedClient.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-109">Open the generated configuration file (App.config) from the GettingStartedClient project.</span></span> <span data-ttu-id="9d8ac-110">El siguiente ejemplo es una vista del archivo de configuración generado.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-110">The following example is a view of the generated configuration file.</span></span> <span data-ttu-id="9d8ac-111">En el [ \<system.serviceModel >](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) sección, busque la [ \<punto de conexión >](https://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) elemento.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-111">Under the [\<system.serviceModel>](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) section, find the [\<endpoint>](https://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) element.</span></span>  
  
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
  
     <span data-ttu-id="9d8ac-112">En este ejemplo configura el punto de conexión que el cliente utiliza para tener acceso al servicio que se encuentra en la siguiente dirección: http://localhost:8000/ServiceModelSamples/Service/CalculatorService</span><span class="sxs-lookup"><span data-stu-id="9d8ac-112">This example configures the endpoint that the client uses to access the service that is located at the following address: http://localhost:8000/ServiceModelSamples/Service/CalculatorService</span></span>  
  
     <span data-ttu-id="9d8ac-113">El elemento de extremo especifica que el contrato de servicio de `ServiceReference1.ICalculator` se usa para la comunicación entre el cliente y el servicio de WCF.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-113">The endpoint element specifies that the `ServiceReference1.ICalculator` service contract is used for communication between the WCF client and service.</span></span> <span data-ttu-id="9d8ac-114">El canal de WCF se configura con el <xref:System.ServiceModel.WSHttpBinding> proporcionado por el sistema.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-114">The WCF channel is configured with the system-provided <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="9d8ac-115">Este contrato se generó mediante Agregar referencia de servicio en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-115">This contract was generated by using Add Service Reference in Visual Studio.</span></span> <span data-ttu-id="9d8ac-116">Es básicamente una copia del contrato que se definió en el proyecto GettingStartedLib.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-116">It is essentially a copy of the contract that was defined in the GettingStartedLib project.</span></span> <span data-ttu-id="9d8ac-117">El enlace <xref:System.ServiceModel.WSHttpBinding> especifica HTTP como el transporte, la seguridad interoperable y otros detalles de configuración.</span><span class="sxs-lookup"><span data-stu-id="9d8ac-117">The <xref:System.ServiceModel.WSHttpBinding> binding specifies HTTP as the transport, interoperable security, and other configuration details.</span></span>  
  
2.  <span data-ttu-id="9d8ac-118">Para obtener más información sobre cómo usar el cliente generado con esta configuración, consulte [Cómo: usar un cliente](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="9d8ac-118">For more information about how to use the generated client with this configuration, see [How to: Use a Client](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d8ac-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d8ac-119">See Also</span></span>  
 [<span data-ttu-id="9d8ac-120">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="9d8ac-120">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="9d8ac-121">Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="9d8ac-121">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [<span data-ttu-id="9d8ac-122">Cómo crear un cliente</span><span class="sxs-lookup"><span data-stu-id="9d8ac-122">How to: Create a Client</span></span>](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [<span data-ttu-id="9d8ac-123">Introducción</span><span class="sxs-lookup"><span data-stu-id="9d8ac-123">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [<span data-ttu-id="9d8ac-124">Probar internamente</span><span class="sxs-lookup"><span data-stu-id="9d8ac-124">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)
