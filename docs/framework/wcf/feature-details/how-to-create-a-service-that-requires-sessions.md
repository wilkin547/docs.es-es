---
title: Cómo crear un servicio que requiere sesiones
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8a7613ef-0df9-47c3-b8dc-47f42cb1fd8b
ms.openlocfilehash: 495de5a926cfc0c5aab88337f5f33b991c49e71a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184988"
---
# <a name="how-to-create-a-service-that-requires-sessions"></a><span data-ttu-id="4f866-102">Cómo crear un servicio que requiere sesiones</span><span class="sxs-lookup"><span data-stu-id="4f866-102">How to: Create a Service That Requires Sessions</span></span>
<span data-ttu-id="4f866-103">Las sesiones crean un estado compartido entre dos o más extremos que habilita características útiles como las devoluciones de llamada, la seguridad de saltos múltiples y asociaciones entre clientes e instancias de servicio.</span><span class="sxs-lookup"><span data-stu-id="4f866-103">Sessions create a shared state between two or more endpoints that enables useful features such as callbacks, multi-hop security, and associations between clients and service instances.</span></span> <span data-ttu-id="4f866-104">Para obtener más información acerca de las sesiones en aplicaciones de Windows Communication Foundation (WCF), vea Uso de [sesiones](../../../../docs/framework/wcf/using-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="4f866-104">For more information about sessions in Windows Communication Foundation (WCF) applications, see [Using Sessions](../../../../docs/framework/wcf/using-sessions.md).</span></span>  
  
### <a name="to-specify-that-a-contract-require-its-binding-to-support-sessions"></a><span data-ttu-id="4f866-105">Especificar que un contrato requiere su enlace para admitir sesiones</span><span class="sxs-lookup"><span data-stu-id="4f866-105">To specify that a contract require its binding to support sessions</span></span>  
  
1. <span data-ttu-id="4f866-106">Crear un contrato de servicio que contenga al menos una operación.</span><span class="sxs-lookup"><span data-stu-id="4f866-106">Create a service contract with at least one operation.</span></span> <span data-ttu-id="4f866-107">Para obtener un ejemplo de cómo crear un contrato de servicio, vea [Cómo: definir un contrato](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)de servicio .</span><span class="sxs-lookup"><span data-stu-id="4f866-107">For an example of how to create a service contract, see [How to: Define a Service Contract](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span></span>  
  
2. <span data-ttu-id="4f866-108">Modifique el <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType> que declara el contrato estableciendo la propiedad <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> en:</span><span class="sxs-lookup"><span data-stu-id="4f866-108">Modify the <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType> that declares the contract by setting the <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> property to either:</span></span>  
  
    - <span data-ttu-id="4f866-109"><xref:System.ServiceModel.SessionMode.Required?displayProperty=nameWithType> si este contrato se debe ejecutar dentro de una sesión.</span><span class="sxs-lookup"><span data-stu-id="4f866-109"><xref:System.ServiceModel.SessionMode.Required?displayProperty=nameWithType> if this contract must be run within a session.</span></span>  
  
    - <span data-ttu-id="4f866-110"><xref:System.ServiceModel.SessionMode.Allowed?displayProperty=nameWithType> si este contrato puede ejecutarse dentro de una sesión.</span><span class="sxs-lookup"><span data-stu-id="4f866-110"><xref:System.ServiceModel.SessionMode.Allowed?displayProperty=nameWithType> if this contract can be run within a session.</span></span>  
  
    - <span data-ttu-id="4f866-111"><xref:System.ServiceModel.SessionMode.NotAllowed?displayProperty=nameWithType> si este contrato no se debe ejecutar dentro de una sesión.</span><span class="sxs-lookup"><span data-stu-id="4f866-111"><xref:System.ServiceModel.SessionMode.NotAllowed?displayProperty=nameWithType> if this contract must not be run within a session.</span></span>  
  
3. <span data-ttu-id="4f866-112">Configure su extremo de servicio para que use un enlace que admita sesiones.</span><span class="sxs-lookup"><span data-stu-id="4f866-112">Configure your service endpoint to use a binding that supports sessions.</span></span> <span data-ttu-id="4f866-113">El siguiente ejemplo de configuración muestra el uso de <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>, que admite una sesión WS`-`ReliableMessaging.</span><span class="sxs-lookup"><span data-stu-id="4f866-113">The following configuration example shows the use of the <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>, which supports a WS`-`ReliableMessaging session.</span></span>  
  
     [!code-xml[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]
  
## <a name="example"></a><span data-ttu-id="4f866-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4f866-114">Example</span></span>  
 <span data-ttu-id="4f866-115">El siguiente código de ejemplo muestra cómo especificar un requisito de sesión del nivel de contrato y utilizar un archivo de configuración para admitir ese requisito con el enlace <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4f866-115">The following example code shows how to specify a contract-level session requirement and use a configuration file to support that requirement with the <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType> binding.</span></span>  
  
 [!code-csharp[SCA.Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/services.cs#1)]
 [!code-vb[SCA.Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/sca.session/vb/services.vb#1)]
 [!code-xml[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]
  
## <a name="see-also"></a><span data-ttu-id="4f866-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4f866-116">See also</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.SessionMode?displayProperty=nameWithType>
