---
title: Procedimiento para crear un punto de conexión de servicio mediante código
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3fbb22fa-2930-48b8-b437-def1de87c6a0
ms.openlocfilehash: 25ea843df7871d730926fe7b9aac9f21d58e263e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598936"
---
# <a name="how-to-create-a-service-endpoint-in-code"></a><span data-ttu-id="da721-102">Procedimiento para crear un punto de conexión de servicio mediante código</span><span class="sxs-lookup"><span data-stu-id="da721-102">How to: Create a Service Endpoint in Code</span></span>
<span data-ttu-id="da721-103">En este ejemplo, se define un contrato de `ICalculator` para un servicio de la calculadora, el servicio se implementa en la clase `CalculatorService` y a continuación, su extremo se define mediante código, donde se especifica que el servicio debe utilizar la clase <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="da721-103">In this example, an `ICalculator` contract is defined for a calculator service, the service is implemented in the `CalculatorService` class, and then its endpoint is defined in code, where it is specified that the service must use the <xref:System.ServiceModel.BasicHttpBinding> class.</span></span>  
  
 <span data-ttu-id="da721-104">Normalmente es el mejor procedimiento para especificar el enlace y la información de dirección de forma declarativa en configuración en lugar de hacerlo de forma imperativa en código.</span><span class="sxs-lookup"><span data-stu-id="da721-104">It is usually the best practice to specify the binding and address information declaratively in configuration rather than imperatively in code.</span></span> <span data-ttu-id="da721-105">Normalmente, no resulta muy práctico definir los puntos de conexión en el código ya que los enlaces y las direcciones de un servicio implementado son, por lo general, diferentes de los utilizados durante el desarrollo del servicio.</span><span class="sxs-lookup"><span data-stu-id="da721-105">Defining endpoints in code is usually not practical because the bindings and addresses for a deployed service are typically different from those used while the service is being developed.</span></span> <span data-ttu-id="da721-106">Más generalmente, manteniendo el enlace y la información de dirección fuera del código permite cambiarlos sin tener que recompilar o implementar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="da721-106">More generally, keeping the binding and addressing information out of the code allows them to change without having to recompile or redeploy the application.</span></span>  
  
#### <a name="to-create-a-service-endpoint-in-code"></a><span data-ttu-id="da721-107">Creación de un extremo de servicio mediante código</span><span class="sxs-lookup"><span data-stu-id="da721-107">To create a service endpoint in code</span></span>  
  
1. <span data-ttu-id="da721-108">Cree la interfaz que define el contrato de servicios.</span><span class="sxs-lookup"><span data-stu-id="da721-108">Create the interface that defines the service contract.</span></span>  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#1)]
     [!code-vb[c_HowTo_CodeServiceBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#1)]  
  
2. <span data-ttu-id="da721-109">Implemente el contrato de servicios definido en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="da721-109">Implement the service contract defined in step 1.</span></span>  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#2)]
     [!code-vb[c_HowTo_CodeServiceBinding#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#2)]  
  
3. <span data-ttu-id="da721-110">En la aplicación de alojamiento, cree la dirección base que han de utilizar el servicio y el enlace con el servicio.</span><span class="sxs-lookup"><span data-stu-id="da721-110">In the hosting application, create the base address for the service and the binding to be used with the service.</span></span>  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#3)]
     [!code-vb[c_HowTo_CodeServiceBinding#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#3)]  
  
4. <span data-ttu-id="da721-111">Cree el host y llame al método <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%29?displayProperty=nameWithType> o una de las otras sobrecargas para agregar el extremo de servicio del host.</span><span class="sxs-lookup"><span data-stu-id="da721-111">Create the host and call <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%29?displayProperty=nameWithType> or one of the other overloads to add the service endpoint for the host.</span></span>  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#6)]
     [!code-vb[c_HowTo_CodeServiceBinding#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#6)]  
  
     <span data-ttu-id="da721-112">Para especificar el enlace en el código, pero para usar los puntos de conexión predeterminados proporcionados por el tiempo de ejecución, pase la dirección base en el constructor al crear el <xref:System.ServiceModel.ServiceHost> , y no llame a <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="da721-112">To specify the binding in code but to use the default endpoints provided by the runtime, pass the base address into the constructor when creating the <xref:System.ServiceModel.ServiceHost>, and do not call <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A?displayProperty=nameWithType>.</span></span>  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#7)]
     [!code-vb[c_HowTo_CodeServiceBinding#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#7)]  
  
     <span data-ttu-id="da721-113">Para obtener más información sobre los puntos de conexión predeterminados, vea [configuración simplificada](../simplified-configuration.md) y [configuración simplificada para servicios WCF](../samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="da721-113">For more information about default endpoints, see [Simplified Configuration](../simplified-configuration.md) and [Simplified Configuration for WCF Services](../samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da721-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="da721-114">See also</span></span>

- [<span data-ttu-id="da721-115">Procedimiento para especificar un enlace de servicio en el código</span><span class="sxs-lookup"><span data-stu-id="da721-115">How to: Specify a Service Binding in Code</span></span>](../how-to-specify-a-service-binding-in-code.md)
