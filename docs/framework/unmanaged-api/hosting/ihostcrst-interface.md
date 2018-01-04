---
title: IHostCrst (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostCrst
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostCrst
helpviewer_keywords: IHostCrst interface [.NET Framework hosting]
ms.assetid: ac298ebd-0815-47e4-a823-30b31baab903
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3a9ed2b390ad741d90f9179ef5101d328d3b639d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihostcrst-interface"></a><span data-ttu-id="948df-102">IHostCrst (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="948df-102">IHostCrst Interface</span></span>
<span data-ttu-id="948df-103">Actúa como la representación del host de una sección crítica para el subprocesamiento.</span><span class="sxs-lookup"><span data-stu-id="948df-103">Serves as the host's representation of a critical section for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="948df-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="948df-104">Methods</span></span>  
  
|<span data-ttu-id="948df-105">Método</span><span class="sxs-lookup"><span data-stu-id="948df-105">Method</span></span>|<span data-ttu-id="948df-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="948df-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="948df-107">Enter (método)</span><span class="sxs-lookup"><span data-stu-id="948df-107">Enter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-enter-method.md)|<span data-ttu-id="948df-108">Entra en la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="948df-108">Enters the critical section.</span></span>|  
|[<span data-ttu-id="948df-109">Leave (método)</span><span class="sxs-lookup"><span data-stu-id="948df-109">Leave Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-leave-method.md)|<span data-ttu-id="948df-110">Deja la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="948df-110">Leaves the critical section.</span></span>|  
|[<span data-ttu-id="948df-111">SetSpinCount (método)</span><span class="sxs-lookup"><span data-stu-id="948df-111">SetSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-setspincount-method.md)|<span data-ttu-id="948df-112">Establece el recuento circular para la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="948df-112">Sets the spin count for the critical section.</span></span>|  
|[<span data-ttu-id="948df-113">TryEnter (método)</span><span class="sxs-lookup"><span data-stu-id="948df-113">TryEnter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-tryenter-method.md)|<span data-ttu-id="948df-114">Intenta escribir la sección crítica y el éxito de informes o el error inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="948df-114">Attempts to enter the critical section, and reports success or failure immediately.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="948df-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="948df-115">Remarks</span></span>  
 <span data-ttu-id="948df-116">`IHostCrst`permite que common language runtime (CLR) para comunicarse directamente con la representación del host de una sección crítica, en lugar de usar las funciones de Win32 como `EnterCriticalSection` o `LeaveCriticalSection`.</span><span class="sxs-lookup"><span data-stu-id="948df-116">`IHostCrst` allows the common language runtime (CLR) to communicate directly with the host's representation of a critical section, rather than using Win32 functions such as `EnterCriticalSection` or `LeaveCriticalSection`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="948df-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="948df-117">Requirements</span></span>  
 <span data-ttu-id="948df-118">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="948df-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="948df-119">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="948df-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="948df-120">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="948df-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="948df-121">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="948df-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="948df-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="948df-122">See Also</span></span>  
 [<span data-ttu-id="948df-123">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="948df-123">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="948df-124">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="948df-124">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="948df-125">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="948df-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
