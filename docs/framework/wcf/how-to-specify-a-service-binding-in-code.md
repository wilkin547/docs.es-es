---
title: Procedimiento para especificar un enlace de servicio en el código
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 67ab5dd8-79c1-4e62-aa75-828ea918a53a
ms.openlocfilehash: 7cf54754661182dca1e91c75b158d9b0a34a1f5e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236486"
---
# <a name="how-to-specify-a-service-binding-in-code"></a><span data-ttu-id="b249d-102">Procedimiento para especificar un enlace de servicio en el código</span><span class="sxs-lookup"><span data-stu-id="b249d-102">How to: Specify a Service Binding in Code</span></span>

<span data-ttu-id="b249d-103">En este ejemplo, se define un contrato de `ICalculator` para un servicio de la calculadora, el servicio se implementa en la clase `CalculatorService` y a continuación, su extremo se define mediante código, donde se especifica que el servicio debe utilizar la clase <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="b249d-103">In this example, an `ICalculator` contract is defined for a calculator service, the service is implemented in the `CalculatorService` class, and then its endpoint is defined in code, where it is specified that the service must use the <xref:System.ServiceModel.BasicHttpBinding> class.</span></span>  
  
 <span data-ttu-id="b249d-104">Normalmente es el mejor procedimiento para especificar el enlace y la información de dirección de forma declarativa en configuración en lugar de hacerlo de forma imperativa en código.</span><span class="sxs-lookup"><span data-stu-id="b249d-104">It is usually the best practice to specify the binding and address information declaratively in configuration rather than imperatively in code.</span></span> <span data-ttu-id="b249d-105">Normalmente, no resulta muy práctico definir los puntos de conexión en el código ya que los enlaces y las direcciones de un servicio implementado son, por lo general, diferentes de los utilizados durante el desarrollo del servicio.</span><span class="sxs-lookup"><span data-stu-id="b249d-105">Defining endpoints in code is usually not practical because the bindings and addresses for a deployed service are typically different from those used while the service is being developed.</span></span> <span data-ttu-id="b249d-106">Más generalmente, manteniendo el enlace y la información de dirección fuera del código permite cambiarlos sin tener que recompilar o implementar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b249d-106">More generally, keeping the binding and addressing information out of the code allows them to change without having to recompile or redeploy the application.</span></span>  
  
 <span data-ttu-id="b249d-107">Para obtener una descripción de cómo configurar este servicio mediante elementos de configuración en lugar de código, consulte [Cómo: especificar un enlace de servicio en la configuración](how-to-specify-a-service-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="b249d-107">For a description of how to configure this service using configuration elements instead of code, see [How to: Specify a Service Binding in Configuration](how-to-specify-a-service-binding-in-configuration.md).</span></span>  
  
### <a name="to-specify-in-code-to-use-the-basichttpbinding-for-the-service"></a><span data-ttu-id="b249d-108">Para especificar mediante código que se use BasicHttpBinding para el servicio</span><span class="sxs-lookup"><span data-stu-id="b249d-108">To specify in code to use the BasicHttpBinding for the service</span></span>  
  
1. <span data-ttu-id="b249d-109">Defina un contrato de servicios para el tipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="b249d-109">Define a service contract for the type of service.</span></span>  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#1)]
     [!code-vb[C_HowTo_CodeServiceBinding#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#1)]  
  
2. <span data-ttu-id="b249d-110">Implemente el contrato de servicios en una clase de servicio.</span><span class="sxs-lookup"><span data-stu-id="b249d-110">Implement the service contract in a service class.</span></span>  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#2)]
     [!code-vb[C_HowTo_CodeServiceBinding#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#2)]  
  
3. <span data-ttu-id="b249d-111">En la aplicación de alojamiento, cree la dirección base que han de utilizar el servicio y el enlace con el servicio.</span><span class="sxs-lookup"><span data-stu-id="b249d-111">In the hosting application, create the base address for the service and the binding to use with the service.</span></span>  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#3)]
     [!code-vb[C_HowTo_CodeServiceBinding#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#3)]  
  
4. <span data-ttu-id="b249d-112">Cree el host para el servicio, agregue el extremo y, a continuación, abra el host.</span><span class="sxs-lookup"><span data-stu-id="b249d-112">Create the host for the service, add the endpoint, and then open the host.</span></span>  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#4)]
     [!code-vb[C_HowTo_CodeServiceBinding#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#4)]  
  
### <a name="to-modify-the-default-values-of-the-binding-properties"></a><span data-ttu-id="b249d-113">Para modificar los valores predeterminados de las propiedades de enlace</span><span class="sxs-lookup"><span data-stu-id="b249d-113">To modify the default values of the binding properties</span></span>  
  
1. <span data-ttu-id="b249d-114">Para modificar uno de los valores predeterminados de propiedades de la clase <xref:System.ServiceModel.BasicHttpBinding>, establezca el valor de propiedad del enlace en el nuevo valor antes de crear el host.</span><span class="sxs-lookup"><span data-stu-id="b249d-114">To modify one of the default property values of the <xref:System.ServiceModel.BasicHttpBinding> class, set the property value on the binding to the new value before creating the host.</span></span> <span data-ttu-id="b249d-115">Por ejemplo, para cambiar los valores predeterminados de tiempos de espera de apertura y cierre de 1 a 2 minutos, utilice lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="b249d-115">For example, to change the default open and close timeout values of 1 minute to 2 minutes, use the following.</span></span>  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#5](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#5)]
     [!code-vb[C_HowTo_CodeServiceBinding#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="b249d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="b249d-116">See also</span></span>

- [<span data-ttu-id="b249d-117">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="b249d-117">Using Bindings to Configure Services and Clients</span></span>](using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="b249d-118">Especificación de una dirección de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="b249d-118">Specifying an Endpoint Address</span></span>](specifying-an-endpoint-address.md)
