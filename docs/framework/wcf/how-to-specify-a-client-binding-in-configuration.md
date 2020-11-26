---
title: Procedimiento para especificar un enlace de cliente en la configuración
description: Obtenga información sobre cómo especificar el enlace para un cliente WCF mediante declaración en un archivo de configuración. El cliente tiene acceso a un servicio en este ejemplo.
ms.date: 03/30/2017
ms.assetid: 4a7c79aa-50ee-4991-891e-adc0599323a7
ms.openlocfilehash: e8a552211b28c1323b2afd595c5b060db6b2824a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236512"
---
# <a name="how-to-specify-a-client-binding-in-configuration"></a><span data-ttu-id="325ac-104">Procedimiento para especificar un enlace de cliente en la configuración</span><span class="sxs-lookup"><span data-stu-id="325ac-104">How to: Specify a Client Binding in Configuration</span></span>

<span data-ttu-id="325ac-105">En este ejemplo, se crea una aplicación de consola de cliente para utilizar un servicio de calculadora y el enlace para ese cliente se especifica de manera declarativa en la configuración.</span><span class="sxs-lookup"><span data-stu-id="325ac-105">In this example, a client console application is created to use a calculator service, and the binding for that client is specified declaratively in configuration.</span></span> <span data-ttu-id="325ac-106">El cliente obtiene acceso al `CalculatorService`, que implementa la interfaz `ICalculator`, y el servicio y el cliente utilizan la clase <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="325ac-106">The client accesses the `CalculatorService`, which implements the `ICalculator` interface, and both the service and the client use the <xref:System.ServiceModel.BasicHttpBinding> class.</span></span>  
  
 <span data-ttu-id="325ac-107">El procedimiento descrito asume que el servicio de calculadora se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="325ac-107">The procedure outlined assumes that the calculator service is running.</span></span> <span data-ttu-id="325ac-108">Para obtener información sobre cómo crear el servicio, vea [Cómo: especificar un enlace de servicio en la configuración](how-to-specify-a-service-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="325ac-108">For information about how to build the service, see [How to: Specify a Service Binding in Configuration](how-to-specify-a-service-binding-in-configuration.md).</span></span> <span data-ttu-id="325ac-109">También usa la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) que Windows Communication Foundation (WCF) proporciona para generar automáticamente los componentes de cliente.</span><span class="sxs-lookup"><span data-stu-id="325ac-109">It also uses the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) that Windows Communication Foundation (WCF) provides to automatically generate the client components.</span></span> <span data-ttu-id="325ac-110">La herramienta genera el código de cliente y la configuración para obtener acceso al servicio.</span><span class="sxs-lookup"><span data-stu-id="325ac-110">The tool generates the client code and configuration for accessing the service.</span></span>  
  
 <span data-ttu-id="325ac-111">El cliente se crea en dos partes.</span><span class="sxs-lookup"><span data-stu-id="325ac-111">The client is built in two parts.</span></span> <span data-ttu-id="325ac-112">Svcutil.exe genera la `ClientCalculator` que implementa la interfaz `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="325ac-112">Svcutil.exe generates the `ClientCalculator` that implements the `ICalculator` interface.</span></span> <span data-ttu-id="325ac-113">Esta aplicación de cliente se construye a continuación mediante la creación de una instancia de `ClientCalculator`.</span><span class="sxs-lookup"><span data-stu-id="325ac-113">This client application is then constructed by constructing an instance of `ClientCalculator`.</span></span>  
  
 <span data-ttu-id="325ac-114">Normalmente es el mejor procedimiento para especificar el enlace y la información de dirección de forma declarativa en configuración en lugar de hacerlo de forma imperativa en código.</span><span class="sxs-lookup"><span data-stu-id="325ac-114">It is usually the best practice to specify the binding and address information declaratively in configuration rather than imperatively in code.</span></span> <span data-ttu-id="325ac-115">Normalmente, no resulta muy práctico definir los puntos de conexión en el código ya que los enlaces y las direcciones de un servicio implementado son, por lo general, diferentes de los utilizados durante el desarrollo del servicio.</span><span class="sxs-lookup"><span data-stu-id="325ac-115">Defining endpoints in code is usually not practical because the bindings and addresses for a deployed service are typically different from those used while the service is being developed.</span></span> <span data-ttu-id="325ac-116">Más generalmente, manteniendo el enlace y la información de dirección fuera del código permite cambiarlos sin tener que recompilar o implementar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="325ac-116">More generally, keeping the binding and addressing information out of the code allows them to change without having to recompile or redeploy the application.</span></span>  
  
 <span data-ttu-id="325ac-117">Puede realizar todos los pasos de configuración siguientes mediante la [herramienta editor de configuración (SvcConfigEditor.exe)](configuration-editor-tool-svcconfigeditor-exe.md).</span><span class="sxs-lookup"><span data-stu-id="325ac-117">You can perform all of the following configuration steps by using the [Configuration Editor Tool (SvcConfigEditor.exe)](configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
 <span data-ttu-id="325ac-118">Para la copia de origen de este ejemplo, consulte el ejemplo [BasicBinding](./samples/basicbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="325ac-118">For the source copy of this example, see the [BasicBinding](./samples/basicbinding.md) sample.</span></span>  
  
### <a name="specifying-a-client-binding-in-configuration"></a><span data-ttu-id="325ac-119">Especificación de un enlace de cliente mediante configuración</span><span class="sxs-lookup"><span data-stu-id="325ac-119">Specifying a client binding in configuration</span></span>  
  
1. <span data-ttu-id="325ac-120">Utilice Svcutil.exe desde la línea de comandos para generar el código a partir de los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="325ac-120">Use Svcutil.exe from the command line to generate code from service metadata.</span></span>  
  
    ```console  
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
    ```  
  
2. <span data-ttu-id="325ac-121">El cliente que se genera contiene la interfaz `ICalculator` que define el contrato de servicios que la implementación del cliente debe cumplir.</span><span class="sxs-lookup"><span data-stu-id="325ac-121">The client that is generated contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/generatedclient.cs#1)]
     [!code-csharp[C_HowTo_ConfigureClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/source.cs#1)]  
  
3. <span data-ttu-id="325ac-122">El cliente generado también contiene la implementación de `ClientCalculator`.</span><span class="sxs-lookup"><span data-stu-id="325ac-122">The generated client also contains the implementation of the `ClientCalculator`.</span></span>  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/generatedclient.cs#2)]
     [!code-csharp[C_HowTo_ConfigureClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/source.cs#2)]  
  
4. <span data-ttu-id="325ac-123">Svcutil.exe también genera la configuración para el cliente que utiliza la clase <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="325ac-123">Svcutil.exe also generates the configuration for the client that uses the <xref:System.ServiceModel.BasicHttpBinding> class.</span></span> <span data-ttu-id="325ac-124">Al usar Visual Studio, asigne a este archivo el nombre App.config. Tenga en cuenta que la dirección y la información de enlace no se especifican en ningún lugar dentro de la implementación del servicio.</span><span class="sxs-lookup"><span data-stu-id="325ac-124">When using Visual Studio, name this file App.config. Note that the address and binding information are not specified anywhere inside the implementation of the service.</span></span> <span data-ttu-id="325ac-125">Además, el código tiene que escribirse para recuperar esa información del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="325ac-125">Also, code does not have to be written to retrieve that information from the configuration file.</span></span>  
  
     [!code-xml[C_HowTo_ConfigureClientBinding#100](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/common/client.exe.config#100)]

5. <span data-ttu-id="325ac-126">Cree una instancia de `ClientCalculator` en una aplicación y, a continuación, llame a las operaciones del servicio.</span><span class="sxs-lookup"><span data-stu-id="325ac-126">Create an instance of the `ClientCalculator` in an application, and then call the service operations.</span></span>  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/client.cs#3)]  
  
6. <span data-ttu-id="325ac-127">Compile y ejecute el cliente.</span><span class="sxs-lookup"><span data-stu-id="325ac-127">Compile and run the client.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="325ac-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="325ac-128">See also</span></span>

- [<span data-ttu-id="325ac-129">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="325ac-129">Using Bindings to Configure Services and Clients</span></span>](using-bindings-to-configure-services-and-clients.md)
