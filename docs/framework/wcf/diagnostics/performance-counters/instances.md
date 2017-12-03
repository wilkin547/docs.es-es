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
ms.openlocfilehash: 87423c3de551cb9fbf8c5a7756e2f0f999129a3b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="instances"></a><span data-ttu-id="d7dd8-102">Instancias</span><span class="sxs-lookup"><span data-stu-id="d7dd8-102">Instances</span></span>
<span data-ttu-id="d7dd8-103">Nombre del contador: instancias.</span><span class="sxs-lookup"><span data-stu-id="d7dd8-103">Counter Name: Instances.</span></span>  
  
## <a name="description"></a><span data-ttu-id="d7dd8-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="d7dd8-104">Description</span></span>  
 <span data-ttu-id="d7dd8-105">Número de contextos de instancias que el servicio contiene actualmente.</span><span class="sxs-lookup"><span data-stu-id="d7dd8-105">Number of instance contexts that the service currently contains.</span></span>  
  
 <span data-ttu-id="d7dd8-106">La mayoría del tiempo, el número de contextos de instancias es idéntico al número de instancias.</span><span class="sxs-lookup"><span data-stu-id="d7dd8-106">Most of the time, the number of instance contexts is identical to the number of instances.</span></span> <span data-ttu-id="d7dd8-107">Sin embargo, los escenarios siguientes son la excepción a esta regla.</span><span class="sxs-lookup"><span data-stu-id="d7dd8-107">However, the following scenarios are exception to this rule.</span></span>  
  
-   <span data-ttu-id="d7dd8-108">Un método del servicio llama el método <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> explícitamente.</span><span class="sxs-lookup"><span data-stu-id="d7dd8-108">A service method calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> method explicitly.</span></span>  
  
-   <span data-ttu-id="d7dd8-109">Un <xref:System.ServiceModel.ReleaseInstanceMode> se aplica a una instancia <xref:System.ServiceModel.OperationBehaviorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="d7dd8-109">A <xref:System.ServiceModel.ReleaseInstanceMode> is applied to an <xref:System.ServiceModel.OperationBehaviorAttribute> instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7dd8-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="d7dd8-110">See Also</span></span>  
 <xref:System.ServiceModel.OperationBehaviorAttribute>
