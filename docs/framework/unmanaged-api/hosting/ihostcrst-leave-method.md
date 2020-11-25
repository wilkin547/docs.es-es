---
title: IHostCrst::Leave (Método)
ms.date: 03/30/2017
api_name:
- IHostCrst.Leave
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::Leave
helpviewer_keywords:
- IHostCrst::Leave method [.NET Framework hosting]
- Leave method [.NET Framework hosting]
ms.assetid: dfc51d9e-b36d-4dba-9ea1-4f63fa0601ae
topic_type:
- apiref
ms.openlocfilehash: 0752afb42b8c512450b047a5e2e7e1ff34533487
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729582"
---
# <a name="ihostcrstleave-method"></a><span data-ttu-id="19c77-102">IHostCrst::Leave (Método)</span><span class="sxs-lookup"><span data-stu-id="19c77-102">IHostCrst::Leave Method</span></span>

<span data-ttu-id="19c77-103">Deja la sección crítica representada por la instancia actual de [IHostCrst](ihostcrst-interface.md).</span><span class="sxs-lookup"><span data-stu-id="19c77-103">Leaves the critical section that is represented by the current instance of [IHostCrst](ihostcrst-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19c77-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="19c77-104">Syntax</span></span>  
  
```cpp  
HRESULT Leave ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="19c77-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="19c77-105">Return Value</span></span>  
  
|<span data-ttu-id="19c77-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="19c77-106">HRESULT</span></span>|<span data-ttu-id="19c77-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="19c77-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="19c77-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="19c77-108">S_OK</span></span>|<span data-ttu-id="19c77-109">`Leave` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="19c77-109">`Leave` returned successfully.</span></span>|  
|<span data-ttu-id="19c77-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="19c77-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="19c77-111">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="19c77-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="19c77-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="19c77-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="19c77-113">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="19c77-113">The call timed out.</span></span>|  
|<span data-ttu-id="19c77-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="19c77-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="19c77-115">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="19c77-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="19c77-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="19c77-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="19c77-117">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="19c77-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="19c77-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="19c77-118">E_FAIL</span></span>|<span data-ttu-id="19c77-119">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="19c77-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="19c77-120">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="19c77-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="19c77-121">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="19c77-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19c77-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="19c77-122">Remarks</span></span>  

 <span data-ttu-id="19c77-123">`Leave` permite que el CLR se comunique directamente con la implementación de subprocesos del host, en lugar de usar la función de Win32 correspondiente `LeaveCriticalSection` .</span><span class="sxs-lookup"><span data-stu-id="19c77-123">`Leave` allows the CLR to communicate directly with the host's threading implementation, rather than using the corresponding Win32 `LeaveCriticalSection` function.</span></span> <span data-ttu-id="19c77-124">Un subproceso que toma la propiedad de la sección crítica representada por la `IHostCrst` instancia actual debe llamar `Leave` una vez para cada vez que entra en la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="19c77-124">A thread that takes ownership of the critical section represented by the current `IHostCrst` instance must call `Leave` once for each time it enters that critical section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19c77-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="19c77-125">Requirements</span></span>  

 <span data-ttu-id="19c77-126">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19c77-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19c77-127">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="19c77-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="19c77-128">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="19c77-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="19c77-129">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19c77-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19c77-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="19c77-130">See also</span></span>

- [<span data-ttu-id="19c77-131">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="19c77-131">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="19c77-132">IHostCrst (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="19c77-132">IHostCrst Interface</span></span>](ihostcrst-interface.md)
- [<span data-ttu-id="19c77-133">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="19c77-133">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
