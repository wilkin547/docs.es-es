---
description: 'Más información sobre: IHostCrst:: Leave (método)'
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
ms.openlocfilehash: b00e62c7b2683ab6024a7c9b8de4645ceb59fb02
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708845"
---
# <a name="ihostcrstleave-method"></a><span data-ttu-id="c6843-103">IHostCrst::Leave (Método)</span><span class="sxs-lookup"><span data-stu-id="c6843-103">IHostCrst::Leave Method</span></span>

<span data-ttu-id="c6843-104">Deja la sección crítica representada por la instancia actual de [IHostCrst](ihostcrst-interface.md).</span><span class="sxs-lookup"><span data-stu-id="c6843-104">Leaves the critical section that is represented by the current instance of [IHostCrst](ihostcrst-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6843-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c6843-105">Syntax</span></span>  
  
```cpp  
HRESULT Leave ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="c6843-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c6843-106">Return Value</span></span>  
  
|<span data-ttu-id="c6843-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c6843-107">HRESULT</span></span>|<span data-ttu-id="c6843-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="c6843-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c6843-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="c6843-109">S_OK</span></span>|<span data-ttu-id="c6843-110">`Leave` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="c6843-110">`Leave` returned successfully.</span></span>|  
|<span data-ttu-id="c6843-111">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c6843-111">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c6843-112">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="c6843-112">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c6843-113">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c6843-113">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c6843-114">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="c6843-114">The call timed out.</span></span>|  
|<span data-ttu-id="c6843-115">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c6843-115">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c6843-116">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="c6843-116">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c6843-117">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c6843-117">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c6843-118">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="c6843-118">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c6843-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c6843-119">E_FAIL</span></span>|<span data-ttu-id="c6843-120">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="c6843-120">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c6843-121">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="c6843-121">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c6843-122">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c6843-122">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6843-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c6843-123">Remarks</span></span>  

 <span data-ttu-id="c6843-124">`Leave` permite que el CLR se comunique directamente con la implementación de subprocesos del host, en lugar de usar la función de Win32 correspondiente `LeaveCriticalSection` .</span><span class="sxs-lookup"><span data-stu-id="c6843-124">`Leave` allows the CLR to communicate directly with the host's threading implementation, rather than using the corresponding Win32 `LeaveCriticalSection` function.</span></span> <span data-ttu-id="c6843-125">Un subproceso que toma la propiedad de la sección crítica representada por la `IHostCrst` instancia actual debe llamar `Leave` una vez para cada vez que entra en la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="c6843-125">A thread that takes ownership of the critical section represented by the current `IHostCrst` instance must call `Leave` once for each time it enters that critical section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6843-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c6843-126">Requirements</span></span>  

 <span data-ttu-id="c6843-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6843-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6843-128">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c6843-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c6843-129">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c6843-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c6843-130">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6843-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6843-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="c6843-131">See also</span></span>

- [<span data-ttu-id="c6843-132">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c6843-132">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="c6843-133">IHostCrst (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c6843-133">IHostCrst Interface</span></span>](ihostcrst-interface.md)
- [<span data-ttu-id="c6843-134">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c6843-134">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
