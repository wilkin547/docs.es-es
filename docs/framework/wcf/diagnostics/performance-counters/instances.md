---
description: 'Más información acerca de: instancias'
title: Instancias
ms.date: 03/30/2017
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
ms.openlocfilehash: 9cd602164816a419b481ff600a7537593d4f500e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99655271"
---
# <a name="instances"></a><span data-ttu-id="ea25a-103">Instancias</span><span class="sxs-lookup"><span data-stu-id="ea25a-103">Instances</span></span>

<span data-ttu-id="ea25a-104">Nombre del contador: instancias.</span><span class="sxs-lookup"><span data-stu-id="ea25a-104">Counter Name: Instances.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ea25a-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="ea25a-105">Description</span></span>  

 <span data-ttu-id="ea25a-106">Número de contextos de instancias que el servicio contiene actualmente.</span><span class="sxs-lookup"><span data-stu-id="ea25a-106">Number of instance contexts that the service currently contains.</span></span>  
  
 <span data-ttu-id="ea25a-107">La mayoría del tiempo, el número de contextos de instancias es idéntico al número de instancias.</span><span class="sxs-lookup"><span data-stu-id="ea25a-107">Most of the time, the number of instance contexts is identical to the number of instances.</span></span> <span data-ttu-id="ea25a-108">Sin embargo, los escenarios siguientes son la excepción a esta regla.</span><span class="sxs-lookup"><span data-stu-id="ea25a-108">However, the following scenarios are exception to this rule.</span></span>  
  
- <span data-ttu-id="ea25a-109">Un método del servicio llama el método <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> explícitamente.</span><span class="sxs-lookup"><span data-stu-id="ea25a-109">A service method calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> method explicitly.</span></span>  
  
- <span data-ttu-id="ea25a-110">Un <xref:System.ServiceModel.ReleaseInstanceMode> se aplica a una instancia <xref:System.ServiceModel.OperationBehaviorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ea25a-110">A <xref:System.ServiceModel.ReleaseInstanceMode> is applied to an <xref:System.ServiceModel.OperationBehaviorAttribute> instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea25a-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea25a-111">See also</span></span>

- <xref:System.ServiceModel.OperationBehaviorAttribute>
