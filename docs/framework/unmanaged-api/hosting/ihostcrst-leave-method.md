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
ms.openlocfilehash: 050af068579d84b984ed83377d0c201e281bd154
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130535"
---
# <a name="ihostcrstleave-method"></a><span data-ttu-id="3b1da-102">IHostCrst::Leave (Método)</span><span class="sxs-lookup"><span data-stu-id="3b1da-102">IHostCrst::Leave Method</span></span>
<span data-ttu-id="3b1da-103">Deja la sección crítica representada por la instancia actual de [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md).</span><span class="sxs-lookup"><span data-stu-id="3b1da-103">Leaves the critical section that is represented by the current instance of [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b1da-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3b1da-104">Syntax</span></span>  
  
```cpp  
HRESULT Leave ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="3b1da-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3b1da-105">Return Value</span></span>  
  
|<span data-ttu-id="3b1da-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3b1da-106">HRESULT</span></span>|<span data-ttu-id="3b1da-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="3b1da-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3b1da-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="3b1da-108">S_OK</span></span>|<span data-ttu-id="3b1da-109">`Leave` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="3b1da-109">`Leave` returned successfully.</span></span>|  
|<span data-ttu-id="3b1da-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3b1da-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3b1da-111">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="3b1da-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3b1da-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3b1da-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3b1da-113">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="3b1da-113">The call timed out.</span></span>|  
|<span data-ttu-id="3b1da-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3b1da-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3b1da-115">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="3b1da-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3b1da-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3b1da-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3b1da-117">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="3b1da-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3b1da-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3b1da-118">E_FAIL</span></span>|<span data-ttu-id="3b1da-119">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="3b1da-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3b1da-120">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="3b1da-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3b1da-121">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3b1da-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b1da-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3b1da-122">Remarks</span></span>  
 <span data-ttu-id="3b1da-123">`Leave` permite que el CLR se comunique directamente con la implementación de subprocesos del host, en lugar de usar la función de `LeaveCriticalSection` de Win32 correspondiente.</span><span class="sxs-lookup"><span data-stu-id="3b1da-123">`Leave` allows the CLR to communicate directly with the host's threading implementation, rather than using the corresponding Win32 `LeaveCriticalSection` function.</span></span> <span data-ttu-id="3b1da-124">Un subproceso que toma la propiedad de la sección crítica representada por la instancia de `IHostCrst` actual debe llamar a `Leave` una vez cada vez que entra en la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="3b1da-124">A thread that takes ownership of the critical section represented by the current `IHostCrst` instance must call `Leave` once for each time it enters that critical section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b1da-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3b1da-125">Requirements</span></span>  
 <span data-ttu-id="3b1da-126">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b1da-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b1da-127">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3b1da-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3b1da-128">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3b1da-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3b1da-129">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b1da-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b1da-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b1da-130">See also</span></span>

- [<span data-ttu-id="3b1da-131">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3b1da-131">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="3b1da-132">IHostCrst (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3b1da-132">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="3b1da-133">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3b1da-133">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
