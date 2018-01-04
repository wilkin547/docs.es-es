---
title: Instancias
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7ed0c4a6f13ddcafdb3a9a773be9cd3f017474ec
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="instances"></a><span data-ttu-id="95776-102">Instancias</span><span class="sxs-lookup"><span data-stu-id="95776-102">Instances</span></span>
<span data-ttu-id="95776-103">Nombre del contador: instancias.</span><span class="sxs-lookup"><span data-stu-id="95776-103">Counter Name: Instances.</span></span>  
  
## <a name="description"></a><span data-ttu-id="95776-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="95776-104">Description</span></span>  
 <span data-ttu-id="95776-105">Número de contextos de instancias que el servicio contiene actualmente.</span><span class="sxs-lookup"><span data-stu-id="95776-105">Number of instance contexts that the service currently contains.</span></span>  
  
 <span data-ttu-id="95776-106">La mayoría del tiempo, el número de contextos de instancias es idéntico al número de instancias.</span><span class="sxs-lookup"><span data-stu-id="95776-106">Most of the time, the number of instance contexts is identical to the number of instances.</span></span> <span data-ttu-id="95776-107">Sin embargo, los escenarios siguientes son la excepción a esta regla.</span><span class="sxs-lookup"><span data-stu-id="95776-107">However, the following scenarios are exception to this rule.</span></span>  
  
-   <span data-ttu-id="95776-108">Un método del servicio llama el método <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> explícitamente.</span><span class="sxs-lookup"><span data-stu-id="95776-108">A service method calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> method explicitly.</span></span>  
  
-   <span data-ttu-id="95776-109">Un <xref:System.ServiceModel.ReleaseInstanceMode> se aplica a una instancia <xref:System.ServiceModel.OperationBehaviorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="95776-109">A <xref:System.ServiceModel.ReleaseInstanceMode> is applied to an <xref:System.ServiceModel.OperationBehaviorAttribute> instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95776-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="95776-110">See Also</span></span>  
 <xref:System.ServiceModel.OperationBehaviorAttribute>
