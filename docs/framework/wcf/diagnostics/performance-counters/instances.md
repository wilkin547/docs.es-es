---
title: Instancias
ms.date: 03/30/2017
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
ms.openlocfilehash: f4bf639e626945c7e753ac352dfecc7a79541bfd
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266082"
---
# <a name="instances"></a><span data-ttu-id="f0d0e-102">Instancias</span><span class="sxs-lookup"><span data-stu-id="f0d0e-102">Instances</span></span>

<span data-ttu-id="f0d0e-103">Nombre del contador: instancias.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-103">Counter Name: Instances.</span></span>  
  
## <a name="description"></a><span data-ttu-id="f0d0e-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="f0d0e-104">Description</span></span>  

 <span data-ttu-id="f0d0e-105">Número de contextos de instancias que el servicio contiene actualmente.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-105">Number of instance contexts that the service currently contains.</span></span>  
  
 <span data-ttu-id="f0d0e-106">La mayoría del tiempo, el número de contextos de instancias es idéntico al número de instancias.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-106">Most of the time, the number of instance contexts is identical to the number of instances.</span></span> <span data-ttu-id="f0d0e-107">Sin embargo, los escenarios siguientes son la excepción a esta regla.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-107">However, the following scenarios are exception to this rule.</span></span>  
  
- <span data-ttu-id="f0d0e-108">Un método del servicio llama el método <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> explícitamente.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-108">A service method calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> method explicitly.</span></span>  
  
- <span data-ttu-id="f0d0e-109">Un <xref:System.ServiceModel.ReleaseInstanceMode> se aplica a una instancia <xref:System.ServiceModel.OperationBehaviorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="f0d0e-109">A <xref:System.ServiceModel.ReleaseInstanceMode> is applied to an <xref:System.ServiceModel.OperationBehaviorAttribute> instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0d0e-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0d0e-110">See also</span></span>

- <xref:System.ServiceModel.OperationBehaviorAttribute>
