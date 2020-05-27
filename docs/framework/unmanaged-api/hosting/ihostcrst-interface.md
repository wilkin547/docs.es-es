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
ms.openlocfilehash: e8cb1486ccea11ba6edcf7bbb781a9bf210b496d
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804899"
---
# <a name="ihostcrst-interface"></a><span data-ttu-id="0d5c6-102">IHostCrst (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0d5c6-102">IHostCrst Interface</span></span>
<span data-ttu-id="0d5c6-103">Actúa como la representación del host de una sección crítica para el subprocesamiento.</span><span class="sxs-lookup"><span data-stu-id="0d5c6-103">Serves as the host's representation of a critical section for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0d5c6-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="0d5c6-104">Methods</span></span>  
  
|<span data-ttu-id="0d5c6-105">Método</span><span class="sxs-lookup"><span data-stu-id="0d5c6-105">Method</span></span>|<span data-ttu-id="0d5c6-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="0d5c6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0d5c6-107">Método Enter</span><span class="sxs-lookup"><span data-stu-id="0d5c6-107">Enter Method</span></span>](ihostcrst-enter-method.md)|<span data-ttu-id="0d5c6-108">Entra en la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="0d5c6-108">Enters the critical section.</span></span>|  
|[<span data-ttu-id="0d5c6-109">Método Leave</span><span class="sxs-lookup"><span data-stu-id="0d5c6-109">Leave Method</span></span>](ihostcrst-leave-method.md)|<span data-ttu-id="0d5c6-110">Deja la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="0d5c6-110">Leaves the critical section.</span></span>|  
|[<span data-ttu-id="0d5c6-111">Método SetSpinCount</span><span class="sxs-lookup"><span data-stu-id="0d5c6-111">SetSpinCount Method</span></span>](ihostcrst-setspincount-method.md)|<span data-ttu-id="0d5c6-112">Establece el número de giros de la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="0d5c6-112">Sets the spin count for the critical section.</span></span>|  
|[<span data-ttu-id="0d5c6-113">TryEnter</span><span class="sxs-lookup"><span data-stu-id="0d5c6-113">TryEnter Method</span></span>](ihostcrst-tryenter-method.md)|<span data-ttu-id="0d5c6-114">Intenta entrar en la sección crítica e informa de éxito o error inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="0d5c6-114">Attempts to enter the critical section, and reports success or failure immediately.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d5c6-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0d5c6-115">Remarks</span></span>  
 <span data-ttu-id="0d5c6-116">`IHostCrst`permite que el Common Language Runtime (CLR) se comunique directamente con la representación del host de una sección crítica, en lugar de usar funciones de Win32 como `EnterCriticalSection` o `LeaveCriticalSection` .</span><span class="sxs-lookup"><span data-stu-id="0d5c6-116">`IHostCrst` allows the common language runtime (CLR) to communicate directly with the host's representation of a critical section, rather than using Win32 functions such as `EnterCriticalSection` or `LeaveCriticalSection`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d5c6-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0d5c6-117">Requirements</span></span>  
 <span data-ttu-id="0d5c6-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d5c6-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d5c6-119">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0d5c6-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0d5c6-120">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0d5c6-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0d5c6-121">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d5c6-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d5c6-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0d5c6-122">See also</span></span>

- [<span data-ttu-id="0d5c6-123">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0d5c6-123">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="0d5c6-124">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0d5c6-124">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="0d5c6-125">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="0d5c6-125">Hosting Interfaces</span></span>](hosting-interfaces.md)
