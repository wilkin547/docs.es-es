---
title: 'Cómo: Especificar un enlace de cliente en el código'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6bee5da4-adf7-42e6-8f78-63a9e5c6dbad
ms.openlocfilehash: 9be571d7be020aef546fdd7ec7cb7519a48ea350
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184058"
---
# <a name="how-to-specify-a-client-binding-in-code"></a><span data-ttu-id="45bbe-102">Cómo: Especificar un enlace de cliente en el código</span><span class="sxs-lookup"><span data-stu-id="45bbe-102">How to: Specify a Client Binding in Code</span></span>
<span data-ttu-id="45bbe-103">En este ejemplo, se crea un cliente para utilizar un servicio de la calculadora y el enlace para ese cliente se especifica en código de manera imperativa.</span><span class="sxs-lookup"><span data-stu-id="45bbe-103">In this example, a client is created to use a calculator service and the binding for that client is specified imperatively in code.</span></span> <span data-ttu-id="45bbe-104">El cliente obtiene acceso al `CalculatorService`, que implementa la interfaz `ICalculator`, y el servicio y el cliente utilizan la clase <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="45bbe-104">The client accesses the `CalculatorService`, which implements the `ICalculator` interface, and both the service and the client use the <xref:System.ServiceModel.BasicHttpBinding> class.</span></span>  
  
 <span data-ttu-id="45bbe-105">Este procedimiento asume que el servicio de la calculadora se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="45bbe-105">This procedure assumes that the calculator service is running.</span></span> <span data-ttu-id="45bbe-106">Para obtener información acerca de cómo compilar el servicio, vea [Cómo: especificar un enlace](how-to-specify-a-service-binding-in-configuration.md)de servicio en la configuración .</span><span class="sxs-lookup"><span data-stu-id="45bbe-106">For information about building the service, see [How to: Specify a Service Binding in Configuration](how-to-specify-a-service-binding-in-configuration.md).</span></span> <span data-ttu-id="45bbe-107">También usa la herramienta de utilidad de metadatos de [ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)Windows Communication Foundation (WCF) proporciona para generar automáticamente los componentes de cliente.</span><span class="sxs-lookup"><span data-stu-id="45bbe-107">It also uses the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)Windows Communication Foundation (WCF) provides to automatically generate the client components.</span></span> <span data-ttu-id="45bbe-108">La herramienta genera el código de cliente para tener acceso al servicio.</span><span class="sxs-lookup"><span data-stu-id="45bbe-108">The tool generates the client code for accessing the service.</span></span>  
  
 <span data-ttu-id="45bbe-109">El cliente se crea en dos partes.</span><span class="sxs-lookup"><span data-stu-id="45bbe-109">The client is built in two parts.</span></span> <span data-ttu-id="45bbe-110">Svcutil.exe genera la `ClientCalculator` que implementa la interfaz `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="45bbe-110">Svcutil.exe generates the `ClientCalculator` that implements the `ICalculator` interface.</span></span> <span data-ttu-id="45bbe-111">Esta aplicación de cliente se construye mediante la creación de una instancia de `ClientCalculator` y especificando, a continuación, el enlace y la dirección del servicio mediante código.</span><span class="sxs-lookup"><span data-stu-id="45bbe-111">This client application is then constructed by constructing an instance of `ClientCalculator` and then specifying the binding and the address for the service in code.</span></span>  
  
 <span data-ttu-id="45bbe-112">Para obtener la copia de origen de este ejemplo, vea el [BasicBinding](./samples/basicbinding.md) ejemplo.</span><span class="sxs-lookup"><span data-stu-id="45bbe-112">For the source copy of this example, see the [BasicBinding](./samples/basicbinding.md) sample.</span></span>  
  
### <a name="to-specify-a-custom-binding-in-code"></a><span data-ttu-id="45bbe-113">Para especificar un enlace personalizado mediante código</span><span class="sxs-lookup"><span data-stu-id="45bbe-113">To specify a custom binding in code</span></span>  
  
1. <span data-ttu-id="45bbe-114">Utilice Svcutil.exe desde la línea de comandos para generar el código a partir de los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="45bbe-114">Use Svcutil.exe from the command line to generate code from service metadata.</span></span>  
  
    ```console  
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
    ```  
  
2. <span data-ttu-id="45bbe-115">El cliente que se genera contiene la interfaz `ICalculator` que define el contrato de servicios que la implementación del cliente debe cumplir.</span><span class="sxs-lookup"><span data-stu-id="45bbe-115">The client that is generated contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>  
  
     [!code-csharp[C_HowTo_CodeClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeclientbinding/cs/client.cs#1)]
     [!code-vb[C_HowTo_CodeClientBinding#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeclientbinding/vb/client.vb#1)]  
  
3. <span data-ttu-id="45bbe-116">El cliente generado también contiene la implementación de `ClientCalculator`.</span><span class="sxs-lookup"><span data-stu-id="45bbe-116">The generated client also contains the implementation of the `ClientCalculator`.</span></span>  
  
     [!code-csharp[C_HowTo_CodeClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeclientbinding/cs/client.cs#2)]
     [!code-vb[C_HowTo_CodeClientBinding#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeclientbinding/vb/client.vb#2)]  
  
4. <span data-ttu-id="45bbe-117">Cree una instancia de `ClientCalculator` que utiliza la clase <xref:System.ServiceModel.BasicHttpBinding> en una aplicación cliente y, a continuación, llame a las operaciones del servicio en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="45bbe-117">Create an instance of the `ClientCalculator` that uses the <xref:System.ServiceModel.BasicHttpBinding> class in a client application, and then call the service operations at the specified address.</span></span>  
  
     [!code-csharp[C_HowTo_CodeClientBinding#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeclientbinding/cs/client.cs#3)]
     [!code-vb[C_HowTo_CodeClientBinding#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeclientbinding/vb/client.vb#3)]  
  
5. <span data-ttu-id="45bbe-118">Compile y ejecute el cliente.</span><span class="sxs-lookup"><span data-stu-id="45bbe-118">Compile and run the client.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45bbe-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="45bbe-119">See also</span></span>

- [<span data-ttu-id="45bbe-120">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="45bbe-120">Using Bindings to Configure Services and Clients</span></span>](using-bindings-to-configure-services-and-clients.md)
