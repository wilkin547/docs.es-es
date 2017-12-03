---
title: "Cómo crear un servicio que requiere sesiones"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 8a7613ef-0df9-47c3-b8dc-47f42cb1fd8b
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8f9cff53b598d4e477488bcb5b5e87be62e78bb9
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-service-that-requires-sessions"></a><span data-ttu-id="c8d12-102">Cómo crear un servicio que requiere sesiones</span><span class="sxs-lookup"><span data-stu-id="c8d12-102">How to: Create a Service That Requires Sessions</span></span>
<span data-ttu-id="c8d12-103">Las sesiones crean un estado compartido entre dos o más puntos de conexión que habilita características útiles como las devoluciones de llamada, la seguridad de saltos múltiples y asociaciones entre clientes e instancias de servicio.</span><span class="sxs-lookup"><span data-stu-id="c8d12-103">Sessions create a shared state between two or more endpoints that enables useful features such as callbacks, multi-hop security, and associations between clients and service instances.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="c8d12-104">las sesiones de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] las aplicaciones, vea [mediante sesiones](../../../../docs/framework/wcf/using-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="c8d12-104"> sessions in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] applications, see [Using Sessions](../../../../docs/framework/wcf/using-sessions.md).</span></span>  
  
### <a name="to-specify-that-a-contract-require-its-binding-to-support-sessions"></a><span data-ttu-id="c8d12-105">Especificar que un contrato requiere su enlace para admitir sesiones</span><span class="sxs-lookup"><span data-stu-id="c8d12-105">To specify that a contract require its binding to support sessions</span></span>  
  
1.  <span data-ttu-id="c8d12-106">Crear un contrato de servicio que contenga al menos una operación.</span><span class="sxs-lookup"><span data-stu-id="c8d12-106">Create a service contract with at least one operation.</span></span> <span data-ttu-id="c8d12-107">Para obtener un ejemplo de cómo crear un contrato de servicio, consulte [Cómo: definir un contrato de servicio](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span><span class="sxs-lookup"><span data-stu-id="c8d12-107">For an example of how to create a service contract, see [How to: Define a Service Contract](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span></span>  
  
2.  <span data-ttu-id="c8d12-108">Modifique el <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType> que declara el contrato estableciendo la propiedad <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> en:</span><span class="sxs-lookup"><span data-stu-id="c8d12-108">Modify the <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType> that declares the contract by setting the <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> property to either:</span></span>  
  
    -   <span data-ttu-id="c8d12-109"><xref:System.ServiceModel.SessionMode.Required?displayProperty=nameWithType> si este contrato se debe ejecutar dentro de una sesión.</span><span class="sxs-lookup"><span data-stu-id="c8d12-109"><xref:System.ServiceModel.SessionMode.Required?displayProperty=nameWithType> if this contract must be run within a session.</span></span>  
  
    -   <span data-ttu-id="c8d12-110"><xref:System.ServiceModel.SessionMode.Allowed?displayProperty=nameWithType> si este contrato puede ejecutarse dentro de una sesión.</span><span class="sxs-lookup"><span data-stu-id="c8d12-110"><xref:System.ServiceModel.SessionMode.Allowed?displayProperty=nameWithType> if this contract can be run within a session.</span></span>  
  
    -   <span data-ttu-id="c8d12-111"><xref:System.ServiceModel.SessionMode.NotAllowed?displayProperty=nameWithType> si este contrato no se debe ejecutar dentro de una sesión.</span><span class="sxs-lookup"><span data-stu-id="c8d12-111"><xref:System.ServiceModel.SessionMode.NotAllowed?displayProperty=nameWithType> if this contract must not be run within a session.</span></span>  
  
3.  <span data-ttu-id="c8d12-112">Configure su extremo de servicio para que use un enlace que admita sesiones.</span><span class="sxs-lookup"><span data-stu-id="c8d12-112">Configure your service endpoint to use a binding that supports sessions.</span></span> <span data-ttu-id="c8d12-113">El siguiente ejemplo de configuración muestra el uso de <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>, que admite una sesión WS`-`ReliableMessaging.</span><span class="sxs-lookup"><span data-stu-id="c8d12-113">The following configuration example shows the use of the <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>, which supports a WS`-`ReliableMessaging session.</span></span>  
  
     [!code-xml[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]   
  
## <a name="example"></a><span data-ttu-id="c8d12-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c8d12-114">Example</span></span>  
 <span data-ttu-id="c8d12-115">El siguiente código de ejemplo muestra cómo especificar un requisito de sesión del nivel de contrato y utilizar un archivo de configuración para admitir ese requisito con el enlace <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c8d12-115">The following example code shows how to specify a contract-level session requirement and use a configuration file to support that requirement with the <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType> binding.</span></span>  
  
 [!code-csharp[SCA.Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/services.cs#1)] 
 [!code-vb[SCA.Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/sca.session/vb/services.vb#1)]      
 [!code-xml[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]     
  
## <a name="see-also"></a><span data-ttu-id="c8d12-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8d12-116">See Also</span></span>  
 <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>  
 <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType>  
 <xref:System.ServiceModel.SessionMode?displayProperty=nameWithType>
