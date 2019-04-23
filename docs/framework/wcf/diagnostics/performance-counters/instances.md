---
title: Instancias
ms.date: 03/30/2017
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
ms.openlocfilehash: 668cfb3026b9ab7259665f5e53873a512b1e2238
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2019
ms.locfileid: "59975590"
---
# <a name="instances"></a><span data-ttu-id="5a89f-102">Instancias</span><span class="sxs-lookup"><span data-stu-id="5a89f-102">Instances</span></span>
<span data-ttu-id="5a89f-103">Nombre del contador: instancias.</span><span class="sxs-lookup"><span data-stu-id="5a89f-103">Counter Name: Instances.</span></span>  
  
## <a name="description"></a><span data-ttu-id="5a89f-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="5a89f-104">Description</span></span>  
 <span data-ttu-id="5a89f-105">Número de contextos de instancias que el servicio contiene actualmente.</span><span class="sxs-lookup"><span data-stu-id="5a89f-105">Number of instance contexts that the service currently contains.</span></span>  
  
 <span data-ttu-id="5a89f-106">La mayoría del tiempo, el número de contextos de instancias es idéntico al número de instancias.</span><span class="sxs-lookup"><span data-stu-id="5a89f-106">Most of the time, the number of instance contexts is identical to the number of instances.</span></span> <span data-ttu-id="5a89f-107">Sin embargo, los escenarios siguientes son la excepción a esta regla.</span><span class="sxs-lookup"><span data-stu-id="5a89f-107">However, the following scenarios are exception to this rule.</span></span>  
  
-   <span data-ttu-id="5a89f-108">Un método del servicio llama el método <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> explícitamente.</span><span class="sxs-lookup"><span data-stu-id="5a89f-108">A service method calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> method explicitly.</span></span>  
  
-   <span data-ttu-id="5a89f-109">Un <xref:System.ServiceModel.ReleaseInstanceMode> se aplica a una instancia <xref:System.ServiceModel.OperationBehaviorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="5a89f-109">A <xref:System.ServiceModel.ReleaseInstanceMode> is applied to an <xref:System.ServiceModel.OperationBehaviorAttribute> instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a89f-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a89f-110">See also</span></span>

- <xref:System.ServiceModel.OperationBehaviorAttribute>
