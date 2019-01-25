---
title: IHostCrst (Interfaz)
ms.date: 03/30/2017
api_name:
- IHostCrst
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst
helpviewer_keywords:
- IHostCrst interface [.NET Framework hosting]
ms.assetid: ac298ebd-0815-47e4-a823-30b31baab903
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 34a911668db09b255282833cec3e6272b315373b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54618664"
---
# <a name="ihostcrst-interface"></a><span data-ttu-id="f2197-102">IHostCrst (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f2197-102">IHostCrst Interface</span></span>
<span data-ttu-id="f2197-103">Actúa como la representación del host de una sección crítica para el subprocesamiento.</span><span class="sxs-lookup"><span data-stu-id="f2197-103">Serves as the host's representation of a critical section for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f2197-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="f2197-104">Methods</span></span>  
  
|<span data-ttu-id="f2197-105">Método</span><span class="sxs-lookup"><span data-stu-id="f2197-105">Method</span></span>|<span data-ttu-id="f2197-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f2197-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f2197-107">Enter (método)</span><span class="sxs-lookup"><span data-stu-id="f2197-107">Enter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-enter-method.md)|<span data-ttu-id="f2197-108">Entra en la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="f2197-108">Enters the critical section.</span></span>|  
|[<span data-ttu-id="f2197-109">Leave (método)</span><span class="sxs-lookup"><span data-stu-id="f2197-109">Leave Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-leave-method.md)|<span data-ttu-id="f2197-110">Deja la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="f2197-110">Leaves the critical section.</span></span>|  
|[<span data-ttu-id="f2197-111">SetSpinCount (método)</span><span class="sxs-lookup"><span data-stu-id="f2197-111">SetSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-setspincount-method.md)|<span data-ttu-id="f2197-112">Establece el recuento circular para la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="f2197-112">Sets the spin count for the critical section.</span></span>|  
|[<span data-ttu-id="f2197-113">TryEnter (método)</span><span class="sxs-lookup"><span data-stu-id="f2197-113">TryEnter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-tryenter-method.md)|<span data-ttu-id="f2197-114">Intenta escribir una sección crítica y los informes correctamente o no inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="f2197-114">Attempts to enter the critical section, and reports success or failure immediately.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2197-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f2197-115">Remarks</span></span>  
 <span data-ttu-id="f2197-116">`IHostCrst` permite que common language runtime (CLR) para comunicarse directamente con la representación del host de una sección crítica, en lugar de usar las funciones de Win32 como `EnterCriticalSection` o `LeaveCriticalSection`.</span><span class="sxs-lookup"><span data-stu-id="f2197-116">`IHostCrst` allows the common language runtime (CLR) to communicate directly with the host's representation of a critical section, rather than using Win32 functions such as `EnterCriticalSection` or `LeaveCriticalSection`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2197-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f2197-117">Requirements</span></span>  
 <span data-ttu-id="f2197-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2197-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2197-119">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f2197-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f2197-120">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f2197-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f2197-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2197-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2197-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2197-122">See also</span></span>
- [<span data-ttu-id="f2197-123">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f2197-123">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="f2197-124">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f2197-124">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="f2197-125">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="f2197-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
