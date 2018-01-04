---
title: "punto de conexión: Errores de llamadas"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 271e6284-9c4b-465f-b619-069e1555a5e4
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 33cedf5dc29e9cabc6fc3b7df8ff355605a112dc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="endpoint-calls-faulted"></a><span data-ttu-id="b4c3c-102">punto de conexión: Errores de llamadas</span><span class="sxs-lookup"><span data-stu-id="b4c3c-102">Endpoint: Calls Faulted</span></span>
<span data-ttu-id="b4c3c-103">Nombre de contador: Llamadas con errores.</span><span class="sxs-lookup"><span data-stu-id="b4c3c-103">Counter Name: Calls Faulted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b4c3c-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="b4c3c-104">Description</span></span>  
 <span data-ttu-id="b4c3c-105">Número de llamadas a este punto de conexión que han devuelto errores.</span><span class="sxs-lookup"><span data-stu-id="b4c3c-105">Number of calls to this endpoint that have returned faults.</span></span> <span data-ttu-id="b4c3c-106">En las aplicaciones [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], los métodos de servicio comunican la información sobre errores de procesamiento mediante mensajes de error SOAP.</span><span class="sxs-lookup"><span data-stu-id="b4c3c-106">In [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="b4c3c-107">Los errores SOAP son tipos de mensaje que se incluyen en los metadatos de una operación del servicio y, por consiguiente, crean un contrato de error que los clientes pueden utilizar para que su ejecución sea más sólida o interactiva.</span><span class="sxs-lookup"><span data-stu-id="b4c3c-107">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="b4c3c-108">Dado que los errores SOAP se muestran a los clientes en formato XML, son sumamente interoperativos.</span><span class="sxs-lookup"><span data-stu-id="b4c3c-108">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4c3c-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4c3c-109">See Also</span></span>  
 [<span data-ttu-id="b4c3c-110">Especificación y gestión de errores en contratos y servicios</span><span class="sxs-lookup"><span data-stu-id="b4c3c-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
