---
title: Errores de llamadas
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bb9e8045-6aeb-4b7f-a825-8283c44252a1
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9a28c9937270fd5714801743caa394b64101c9b5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="calls-faulted"></a><span data-ttu-id="e719e-102">Errores de llamadas</span><span class="sxs-lookup"><span data-stu-id="e719e-102">Calls Faulted</span></span>
<span data-ttu-id="e719e-103">Nombre de contador: llamadas con errores</span><span class="sxs-lookup"><span data-stu-id="e719e-103">Counter Name: Calls Faulted</span></span>  
  
## <a name="description"></a><span data-ttu-id="e719e-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="e719e-104">Description</span></span>  
 <span data-ttu-id="e719e-105">Número de llamadas a esta operación que devolvieron errores.</span><span class="sxs-lookup"><span data-stu-id="e719e-105">Number of calls to this operation that returned faults.</span></span> <span data-ttu-id="e719e-106">En las aplicaciones [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], los métodos de servicio comunican la información sobre errores de procesamiento mediante mensajes de error SOAP.</span><span class="sxs-lookup"><span data-stu-id="e719e-106">In [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="e719e-107">Los errores SOAP son tipos de mensaje que se incluyen en los metadatos de una operación del servicio y, por consiguiente, crean un contrato de error que los clientes pueden utilizar para que su ejecución sea más sólida o interactiva.</span><span class="sxs-lookup"><span data-stu-id="e719e-107">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="e719e-108">Dado que los errores SOAP se muestran a los clientes en formato XML, son sumamente interoperativos.</span><span class="sxs-lookup"><span data-stu-id="e719e-108">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e719e-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="e719e-109">See Also</span></span>  
 [<span data-ttu-id="e719e-110">Especificación y gestión de errores en contratos y servicios</span><span class="sxs-lookup"><span data-stu-id="e719e-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
