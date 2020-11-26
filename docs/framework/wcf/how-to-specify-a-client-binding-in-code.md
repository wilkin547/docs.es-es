---
title: Procedimiento para especificar un enlace de cliente en el código
description: Obtenga información sobre cómo especificar el enlace de un cliente WCF de forma imperativa en el código. El cliente tiene acceso a un servicio en este ejemplo.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6bee5da4-adf7-42e6-8f78-63a9e5c6dbad
ms.openlocfilehash: f9a56c631d841fe60923c05a19bdec9db989ac60
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236577"
---
# <a name="how-to-specify-a-client-binding-in-code"></a><span data-ttu-id="dacbf-104">Procedimiento para especificar un enlace de cliente en el código</span><span class="sxs-lookup"><span data-stu-id="dacbf-104">How to: Specify a Client Binding in Code</span></span>

<span data-ttu-id="dacbf-105">En este ejemplo, se crea un cliente para utilizar un servicio de la calculadora y el enlace para ese cliente se especifica en código de manera imperativa.</span><span class="sxs-lookup"><span data-stu-id="dacbf-105">In this example, a client is created to use a calculator service and the binding for that client is specified imperatively in code.</span></span> <span data-ttu-id="dacbf-106">El cliente obtiene acceso al `CalculatorService`, que implementa la interfaz `ICalculator`, y el servicio y el cliente utilizan la clase <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="dacbf-106">The client accesses the `CalculatorService`, which implements the `ICalculator` interface, and both the service and the client use the <xref:System.ServiceModel.BasicHttpBinding> class.</span></span>  
  
 <span data-ttu-id="dacbf-107">Este procedimiento asume que el servicio de la calculadora se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="dacbf-107">This procedure assumes that the calculator service is running.</span></span> <span data-ttu-id="dacbf-108">Para obtener información sobre cómo crear el servicio, vea [Cómo: especificar un enlace de servicio en la configuración](how-to-specify-a-service-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="dacbf-108">For information about building the service, see [How to: Specify a Service Binding in Configuration](how-to-specify-a-service-binding-in-configuration.md).</span></span> <span data-ttu-id="dacbf-109">También usa la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)Windows Communication Foundation (WCF) proporciona para generar automáticamente los componentes de cliente.</span><span class="sxs-lookup"><span data-stu-id="dacbf-109">It also uses the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)Windows Communication Foundation (WCF) provides to automatically generate the client components.</span></span> <span data-ttu-id="dacbf-110">La herramienta genera el código de cliente para tener acceso al servicio.</span><span class="sxs-lookup"><span data-stu-id="dacbf-110">The tool generates the client code for accessing the service.</span></span>  
  
 <span data-ttu-id="dacbf-111">El cliente se crea en dos partes.</span><span class="sxs-lookup"><span data-stu-id="dacbf-111">The client is built in two parts.</span></span> <span data-ttu-id="dacbf-112">Svcutil.exe genera la `ClientCalculator` que implementa la interfaz `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="dacbf-112">Svcutil.exe generates the `ClientCalculator` that implements the `ICalculator` interface.</span></span> <span data-ttu-id="dacbf-113">Esta aplicación de cliente se construye mediante la creación de una instancia de `ClientCalculator` y especificando, a continuación, el enlace y la dirección del servicio mediante código.</span><span class="sxs-lookup"><span data-stu-id="dacbf-113">This client application is then constructed by constructing an instance of `ClientCalculator` and then specifying the binding and the address for the service in code.</span></span>  
  
 <span data-ttu-id="dacbf-114">Para la copia de origen de este ejemplo, consulte el ejemplo [BasicBinding](./samples/basicbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="dacbf-114">For the source copy of this example, see the [BasicBinding](./samples/basicbinding.md) sample.</span></span>  
  
### <a name="to-specify-a-custom-binding-in-code"></a><span data-ttu-id="dacbf-115">Para especificar un enlace personalizado mediante código</span><span class="sxs-lookup"><span data-stu-id="dacbf-115">To specify a custom binding in code</span></span>  
  
1. <span data-ttu-id="dacbf-116">Utilice Svcutil.exe desde la línea de comandos para generar el código a partir de los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="dacbf-116">Use Svcutil.exe from the command line to generate code from service metadata.</span></span>  
  
    ```console  
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
    ```  
  
2. <span data-ttu-id="dacbf-117">El cliente que se genera contiene la interfaz `ICalculator` que define el contrato de servicios que la implementación del cliente debe cumplir.</span><span class="sxs-lookup"><span data-stu-id="dacbf-117">The client that is generated contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>  
  
     [!code-csharp[C_HowTo_CodeClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeclientbinding/cs/client.cs#1)]
     [!code-vb[C_HowTo_CodeClientBinding#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeclientbinding/vb/client.vb#1)]  
  
3. <span data-ttu-id="dacbf-118">El cliente generado también contiene la implementación de `ClientCalculator`.</span><span class="sxs-lookup"><span data-stu-id="dacbf-118">The generated client also contains the implementation of the `ClientCalculator`.</span></span>  
  
     [!code-csharp[C_HowTo_CodeClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeclientbinding/cs/client.cs#2)]
     [!code-vb[C_HowTo_CodeClientBinding#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeclientbinding/vb/client.vb#2)]  
  
4. <span data-ttu-id="dacbf-119">Cree una instancia de `ClientCalculator` que utiliza la clase <xref:System.ServiceModel.BasicHttpBinding> en una aplicación cliente y, a continuación, llame a las operaciones del servicio en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="dacbf-119">Create an instance of the `ClientCalculator` that uses the <xref:System.ServiceModel.BasicHttpBinding> class in a client application, and then call the service operations at the specified address.</span></span>  
  
     [!code-csharp[C_HowTo_CodeClientBinding#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeclientbinding/cs/client.cs#3)]
     [!code-vb[C_HowTo_CodeClientBinding#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeclientbinding/vb/client.vb#3)]  
  
5. <span data-ttu-id="dacbf-120">Compile y ejecute el cliente.</span><span class="sxs-lookup"><span data-stu-id="dacbf-120">Compile and run the client.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dacbf-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="dacbf-121">See also</span></span>

- [<span data-ttu-id="dacbf-122">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="dacbf-122">Using Bindings to Configure Services and Clients</span></span>](using-bindings-to-configure-services-and-clients.md)
