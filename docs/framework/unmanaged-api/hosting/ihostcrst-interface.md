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
ms.openlocfilehash: 939f100e8ee386642a29c33827a8339caf0467b9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59193192"
---
# <a name="ihostcrst-interface"></a><span data-ttu-id="b9eeb-102">IHostCrst (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b9eeb-102">IHostCrst Interface</span></span>
<span data-ttu-id="b9eeb-103">Actúa como la representación del host de una sección crítica para el subprocesamiento.</span><span class="sxs-lookup"><span data-stu-id="b9eeb-103">Serves as the host's representation of a critical section for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b9eeb-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="b9eeb-104">Methods</span></span>  
  
|<span data-ttu-id="b9eeb-105">Método</span><span class="sxs-lookup"><span data-stu-id="b9eeb-105">Method</span></span>|<span data-ttu-id="b9eeb-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="b9eeb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b9eeb-107">Método Enter</span><span class="sxs-lookup"><span data-stu-id="b9eeb-107">Enter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-enter-method.md)|<span data-ttu-id="b9eeb-108">Entra en la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="b9eeb-108">Enters the critical section.</span></span>|  
|[<span data-ttu-id="b9eeb-109">Método Leave</span><span class="sxs-lookup"><span data-stu-id="b9eeb-109">Leave Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-leave-method.md)|<span data-ttu-id="b9eeb-110">Deja la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="b9eeb-110">Leaves the critical section.</span></span>|  
|[<span data-ttu-id="b9eeb-111">Método SetSpinCount</span><span class="sxs-lookup"><span data-stu-id="b9eeb-111">SetSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-setspincount-method.md)|<span data-ttu-id="b9eeb-112">Establece el recuento circular para la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="b9eeb-112">Sets the spin count for the critical section.</span></span>|  
|[<span data-ttu-id="b9eeb-113">TryEnter</span><span class="sxs-lookup"><span data-stu-id="b9eeb-113">TryEnter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-tryenter-method.md)|<span data-ttu-id="b9eeb-114">Intenta escribir una sección crítica y los informes correctamente o no inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="b9eeb-114">Attempts to enter the critical section, and reports success or failure immediately.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9eeb-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b9eeb-115">Remarks</span></span>  
 `IHostCrst` <span data-ttu-id="b9eeb-116">permite que common language runtime (CLR) para comunicarse directamente con la representación del host de una sección crítica, en lugar de usar las funciones de Win32 como `EnterCriticalSection` o `LeaveCriticalSection`.</span><span class="sxs-lookup"><span data-stu-id="b9eeb-116">allows the common language runtime (CLR) to communicate directly with the host's representation of a critical section, rather than using Win32 functions such as `EnterCriticalSection` or `LeaveCriticalSection`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9eeb-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b9eeb-117">Requirements</span></span>  
 <span data-ttu-id="b9eeb-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9eeb-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9eeb-119">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b9eeb-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b9eeb-120">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b9eeb-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="b9eeb-121">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b9eeb-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b9eeb-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9eeb-122">See also</span></span>

- [<span data-ttu-id="b9eeb-123">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b9eeb-123">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="b9eeb-124">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b9eeb-124">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="b9eeb-125">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="b9eeb-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
