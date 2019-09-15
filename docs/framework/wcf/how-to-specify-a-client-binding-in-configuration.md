---
title: Procedimiento para especificar un enlace de cliente en la configuración
ms.date: 03/30/2017
ms.assetid: 4a7c79aa-50ee-4991-891e-adc0599323a7
ms.openlocfilehash: 0757dac4cdcffc7c3550432a71fe45b587327660
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "70990215"
---
# <a name="how-to-specify-a-client-binding-in-configuration"></a><span data-ttu-id="4d9ab-102">Procedimiento para especificar un enlace de cliente en la configuración</span><span class="sxs-lookup"><span data-stu-id="4d9ab-102">How to: Specify a Client Binding in Configuration</span></span>
<span data-ttu-id="4d9ab-103">En este ejemplo, se crea una aplicación de consola de cliente para utilizar un servicio de calculadora y el enlace para ese cliente se especifica de manera declarativa en la configuración.</span><span class="sxs-lookup"><span data-stu-id="4d9ab-103">In this example, a client console application is created to use a calculator service, and the binding for that client is specified declaratively in configuration.</span></span> <span data-ttu-id="4d9ab-104">El cliente obtiene acceso al `CalculatorService`, que implementa la interfaz `ICalculator`, y el servicio y el cliente utilizan la clase <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="4d9ab-104">The client accesses the `CalculatorService`, which implements the `ICalculator` interface, and both the service and the client use the <xref:System.ServiceModel.BasicHttpBinding> class.</span></span>  
  
 <span data-ttu-id="4d9ab-105">El procedimiento descrito asume que el servicio de calculadora se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="4d9ab-105">The procedure outlined assumes that the calculator service is running.</span></span> <span data-ttu-id="4d9ab-106">Para obtener información acerca de cómo crear el servicio, [consulte Cómo: Especifique un enlace de servicio en](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)la configuración.</span><span class="sxs-lookup"><span data-stu-id="4d9ab-106">For information about how to build the service, see [How to: Specify a Service Binding in Configuration](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span></span> <span data-ttu-id="4d9ab-107">También usa la [herramienta de utilidad de metadatos de ServiceModel (SvcUtil. exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) que Windows Communication Foundation (WCF) proporciona para generar automáticamente los componentes de cliente.</span><span class="sxs-lookup"><span data-stu-id="4d9ab-107">It also uses the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) that Windows Communication Foundation (WCF) provides to automatically generate the client components.</span></span> <span data-ttu-id="4d9ab-108">La herramienta genera el código de cliente y la configuración para obtener acceso al servicio.</span><span class="sxs-lookup"><span data-stu-id="4d9ab-108">The tool generates the client code and configuration for accessing the service.</span></span>  
  
 <span data-ttu-id="4d9ab-109">El cliente se crea en dos partes.</span><span class="sxs-lookup"><span data-stu-id="4d9ab-109">The client is built in two parts.</span></span> <span data-ttu-id="4d9ab-110">Svcutil.exe genera la `ClientCalculator` que implementa la interfaz `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="4d9ab-110">Svcutil.exe generates the `ClientCalculator` that implements the `ICalculator` interface.</span></span> <span data-ttu-id="4d9ab-111">Esta aplicación de cliente se construye a continuación mediante la creación de una instancia de `ClientCalculator`.</span><span class="sxs-lookup"><span data-stu-id="4d9ab-111">This client application is then constructed by constructing an instance of `ClientCalculator`.</span></span>  
  
 <span data-ttu-id="4d9ab-112">Normalmente es el mejor procedimiento para especificar el enlace y la información de dirección de forma declarativa en configuración en lugar de hacerlo de forma imperativa en código.</span><span class="sxs-lookup"><span data-stu-id="4d9ab-112">It is usually the best practice to specify the binding and address information declaratively in configuration rather than imperatively in code.</span></span> <span data-ttu-id="4d9ab-113">Normalmente, no resulta muy práctico definir los puntos de conexión en el código ya que los enlaces y las direcciones de un servicio implementado son, por lo general, diferentes de los utilizados durante el desarrollo del servicio.</span><span class="sxs-lookup"><span data-stu-id="4d9ab-113">Defining endpoints in code is usually not practical because the bindings and addresses for a deployed service are typically different from those used while the service is being developed.</span></span> <span data-ttu-id="4d9ab-114">Más generalmente, manteniendo el enlace y la información de dirección fuera del código permite cambiarlos sin tener que recompilar o implementar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4d9ab-114">More generally, keeping the binding and addressing information out of the code allows them to change without having to recompile or redeploy the application.</span></span>  
  
 <span data-ttu-id="4d9ab-115">Puede realizar todos los pasos de configuración siguientes mediante la [herramienta editor de configuración (SvcConfigEditor. exe)](../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span><span class="sxs-lookup"><span data-stu-id="4d9ab-115">You can perform all of the following configuration steps by using the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
 <span data-ttu-id="4d9ab-116">Para la copia de origen de este ejemplo, consulte el ejemplo [BasicBinding](../../../docs/framework/wcf/samples/basicbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="4d9ab-116">For the source copy of this example, see the [BasicBinding](../../../docs/framework/wcf/samples/basicbinding.md) sample.</span></span>  
  
### <a name="specifying-a-client-binding-in-configuration"></a><span data-ttu-id="4d9ab-117">Especificación de un enlace de cliente mediante configuración</span><span class="sxs-lookup"><span data-stu-id="4d9ab-117">Specifying a client binding in configuration</span></span>  
  
1. <span data-ttu-id="4d9ab-118">Utilice Svcutil.exe desde la línea de comandos para generar el código a partir de los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="4d9ab-118">Use Svcutil.exe from the command line to generate code from service metadata.</span></span>  
  
    ```console  
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>   
    ```  
  
2. <span data-ttu-id="4d9ab-119">El cliente que se genera contiene la interfaz `ICalculator` que define el contrato de servicios que la implementación del cliente debe cumplir.</span><span class="sxs-lookup"><span data-stu-id="4d9ab-119">The client that is generated contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/generatedclient.cs#1)]
     [!code-csharp[C_HowTo_ConfigureClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/source.cs#1)]  
  
3. <span data-ttu-id="4d9ab-120">El cliente generado también contiene la implementación de `ClientCalculator`.</span><span class="sxs-lookup"><span data-stu-id="4d9ab-120">The generated client also contains the implementation of the `ClientCalculator`.</span></span>  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/generatedclient.cs#2)]
     [!code-csharp[C_HowTo_ConfigureClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/source.cs#2)]  
  
4. <span data-ttu-id="4d9ab-121">Svcutil.exe también genera la configuración para el cliente que utiliza la clase <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="4d9ab-121">Svcutil.exe also generates the configuration for the client that uses the <xref:System.ServiceModel.BasicHttpBinding> class.</span></span> <span data-ttu-id="4d9ab-122">Al usar Visual Studio, asigne al archivo el nombre app. config. Observe que la información de enlace y dirección no se especifican en ninguna parte de la implementación del servicio.</span><span class="sxs-lookup"><span data-stu-id="4d9ab-122">When using Visual Studio, name this file App.config. Note that the address and binding information are not specified anywhere inside the implementation of the service.</span></span> <span data-ttu-id="4d9ab-123">Además, el código tiene que escribirse para recuperar esa información del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="4d9ab-123">Also, code does not have to be written to retrieve that information from the configuration file.</span></span>  
  
     [!code-xml[C_HowTo_ConfigureClientBinding#100](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/common/client.exe.config#100)]   
            
5. <span data-ttu-id="4d9ab-124">Cree una instancia de `ClientCalculator` en una aplicación y, a continuación, llame a las operaciones del servicio.</span><span class="sxs-lookup"><span data-stu-id="4d9ab-124">Create an instance of the `ClientCalculator` in an application, and then call the service operations.</span></span>  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/client.cs#3)]  
  
6. <span data-ttu-id="4d9ab-125">Compile y ejecute el cliente.</span><span class="sxs-lookup"><span data-stu-id="4d9ab-125">Compile and run the client.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d9ab-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d9ab-126">See also</span></span>

- [<span data-ttu-id="4d9ab-127">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="4d9ab-127">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
