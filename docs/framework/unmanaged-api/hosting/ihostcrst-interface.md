---
description: 'Más información acerca de: IHostCrst (interfaz)'
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
ms.openlocfilehash: 7945f0087667c1d610a1a2370528b055af74d579
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708884"
---
# <a name="ihostcrst-interface"></a><span data-ttu-id="f0197-103">IHostCrst (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f0197-103">IHostCrst Interface</span></span>

<span data-ttu-id="f0197-104">Actúa como la representación del host de una sección crítica para el subprocesamiento.</span><span class="sxs-lookup"><span data-stu-id="f0197-104">Serves as the host's representation of a critical section for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f0197-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="f0197-105">Methods</span></span>  
  
|<span data-ttu-id="f0197-106">Método</span><span class="sxs-lookup"><span data-stu-id="f0197-106">Method</span></span>|<span data-ttu-id="f0197-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f0197-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f0197-108">Método Enter</span><span class="sxs-lookup"><span data-stu-id="f0197-108">Enter Method</span></span>](ihostcrst-enter-method.md)|<span data-ttu-id="f0197-109">Entra en la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="f0197-109">Enters the critical section.</span></span>|  
|[<span data-ttu-id="f0197-110">Método Leave</span><span class="sxs-lookup"><span data-stu-id="f0197-110">Leave Method</span></span>](ihostcrst-leave-method.md)|<span data-ttu-id="f0197-111">Deja la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="f0197-111">Leaves the critical section.</span></span>|  
|[<span data-ttu-id="f0197-112">Método SetSpinCount</span><span class="sxs-lookup"><span data-stu-id="f0197-112">SetSpinCount Method</span></span>](ihostcrst-setspincount-method.md)|<span data-ttu-id="f0197-113">Establece el número de giros de la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="f0197-113">Sets the spin count for the critical section.</span></span>|  
|[<span data-ttu-id="f0197-114">TryEnter</span><span class="sxs-lookup"><span data-stu-id="f0197-114">TryEnter Method</span></span>](ihostcrst-tryenter-method.md)|<span data-ttu-id="f0197-115">Intenta entrar en la sección crítica e informa de éxito o error inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="f0197-115">Attempts to enter the critical section, and reports success or failure immediately.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0197-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f0197-116">Remarks</span></span>  

 <span data-ttu-id="f0197-117">`IHostCrst` permite que el Common Language Runtime (CLR) se comunique directamente con la representación del host de una sección crítica, en lugar de usar funciones de Win32 como `EnterCriticalSection` o `LeaveCriticalSection` .</span><span class="sxs-lookup"><span data-stu-id="f0197-117">`IHostCrst` allows the common language runtime (CLR) to communicate directly with the host's representation of a critical section, rather than using Win32 functions such as `EnterCriticalSection` or `LeaveCriticalSection`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0197-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f0197-118">Requirements</span></span>  

 <span data-ttu-id="f0197-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0197-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0197-120">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f0197-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f0197-121">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f0197-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f0197-122">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0197-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0197-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0197-123">See also</span></span>

- [<span data-ttu-id="f0197-124">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f0197-124">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="f0197-125">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f0197-125">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="f0197-126">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="f0197-126">Hosting Interfaces</span></span>](hosting-interfaces.md)
