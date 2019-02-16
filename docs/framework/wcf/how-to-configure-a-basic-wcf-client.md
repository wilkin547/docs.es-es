---
title: Filtrar Configurar a un cliente básico de Windows Communication Foundation
ms.date: 09/14/2018
helpviewer_keywords:
- WCF clients [WCF], configuring
ms.assetid: d067b86d-afb0-47bf-94f6-45180a3d8d78
ms.openlocfilehash: 18acec48b2af78877f99335da38ccb0ae8942824
ms.sourcegitcommit: 0069cb3de8eed4e92b2195d29e5769a76111acdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/16/2019
ms.locfileid: "56332330"
---
# <a name="how-to-configure-a-basic-windows-communication-foundation-client"></a><span data-ttu-id="e2e26-102">Filtrar Configurar a un cliente básico de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="e2e26-102">How to: Configure a Basic Windows Communication Foundation Client</span></span>

<span data-ttu-id="e2e26-103">Esta es la quinta de las seis tareas necesarias para crear una aplicación básica de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="e2e26-103">This is the fifth of six tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="e2e26-104">Para obtener información general de las seis tareas, vea el tema [Tutorial de introducción](../../../docs/framework/wcf/getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="e2e26-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>

<span data-ttu-id="e2e26-105">Este tema describe el archivo de configuración de cliente que se ha generado mediante la **Add Service Reference** funcionalidad de Visual Studio o el [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="e2e26-105">This topic discusses the client configuration file that was generated using the **Add Service Reference** functionality of Visual Studio or the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="e2e26-106">La configuración del cliente consiste en especificar el extremo que utiliza el cliente para obtener acceso al servicio.</span><span class="sxs-lookup"><span data-stu-id="e2e26-106">Configuring the client consists of specifying the endpoint that the client uses to access the service.</span></span> <span data-ttu-id="e2e26-107">Un punto de conexión tiene una dirección, un enlace y un contrato, y cada uno de ellos debe especificarse en el proceso de configuración del cliente.</span><span class="sxs-lookup"><span data-stu-id="e2e26-107">An endpoint has an address, a binding, and a contract, and each of these must be specified in the process of configuring the client.</span></span>

## <a name="configure-a-windows-communication-foundation-client"></a><span data-ttu-id="e2e26-108">Configurar a un cliente de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="e2e26-108">Configure a Windows Communication Foundation client</span></span>

<span data-ttu-id="e2e26-109">Abra el archivo de configuración generado (App.config) del proyecto GettingStartedClient.</span><span class="sxs-lookup"><span data-stu-id="e2e26-109">Open the generated configuration file (App.config) from the GettingStartedClient project.</span></span> <span data-ttu-id="e2e26-110">El siguiente ejemplo es una vista del archivo de configuración generado.</span><span class="sxs-lookup"><span data-stu-id="e2e26-110">The following example is a view of the generated configuration file.</span></span> <span data-ttu-id="e2e26-111">En el [ \<system.serviceModel >](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) sección, busque la [ \<punto de conexión >](../configure-apps/file-schema/wcf/endpoint-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="e2e26-111">Under the [\<system.serviceModel>](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) section, find the [\<endpoint>](../configure-apps/file-schema/wcf/endpoint-element.md) element.</span></span>

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

<span data-ttu-id="e2e26-112">Este ejemplo configura el punto de conexión que el cliente utiliza para tener acceso al servicio que se encuentra en la siguiente dirección: `http://localhost:8000/ServiceModelSamples/Service/CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="e2e26-112">This example configures the endpoint that the client uses to access the service that is located at the following address: `http://localhost:8000/ServiceModelSamples/Service/CalculatorService`.</span></span>

<span data-ttu-id="e2e26-113">El elemento de punto de conexión especifica que el contrato de servicio de `ServiceReference1.ICalculator` se usa para la comunicación entre el cliente y el servicio de WCF.</span><span class="sxs-lookup"><span data-stu-id="e2e26-113">The endpoint element specifies that the `ServiceReference1.ICalculator` service contract is used for communication between the WCF client and service.</span></span> <span data-ttu-id="e2e26-114">El canal de WCF se configura con el <xref:System.ServiceModel.WSHttpBinding> proporcionado por el sistema.</span><span class="sxs-lookup"><span data-stu-id="e2e26-114">The WCF channel is configured with the system-provided <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="e2e26-115">Este contrato se generó mediante el uso de **Add Service Reference** en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e2e26-115">This contract was generated by using **Add Service Reference** in Visual Studio.</span></span> <span data-ttu-id="e2e26-116">Es básicamente una copia del contrato que se definió en el proyecto GettingStartedLib.</span><span class="sxs-lookup"><span data-stu-id="e2e26-116">It is essentially a copy of the contract that was defined in the GettingStartedLib project.</span></span> <span data-ttu-id="e2e26-117">El enlace <xref:System.ServiceModel.WSHttpBinding> especifica HTTP como el transporte, la seguridad interoperable y otros detalles de configuración.</span><span class="sxs-lookup"><span data-stu-id="e2e26-117">The <xref:System.ServiceModel.WSHttpBinding> binding specifies HTTP as the transport, interoperable security, and other configuration details.</span></span>

<span data-ttu-id="e2e26-118">Para obtener más información sobre cómo usar el cliente generado con esta configuración, vea [Cómo: Usar un cliente](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="e2e26-118">For more information about how to use the generated client with this configuration, see [How to: Use a Client](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="e2e26-119">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="e2e26-119">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e2e26-120">Cómo: Usar a un cliente de WCF</span><span class="sxs-lookup"><span data-stu-id="e2e26-120">How to: Use a WCF client</span></span>](../../../docs/framework/wcf/how-to-use-a-wcf-client.md)

## <a name="see-also"></a><span data-ttu-id="e2e26-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2e26-121">See also</span></span>

- [<span data-ttu-id="e2e26-122">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="e2e26-122">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="e2e26-123">Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="e2e26-123">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="e2e26-124">Cómo: Crear un cliente</span><span class="sxs-lookup"><span data-stu-id="e2e26-124">How to: Create a Client</span></span>](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)
- [<span data-ttu-id="e2e26-125">Introducción</span><span class="sxs-lookup"><span data-stu-id="e2e26-125">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)
- [<span data-ttu-id="e2e26-126">Probar internamente</span><span class="sxs-lookup"><span data-stu-id="e2e26-126">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)