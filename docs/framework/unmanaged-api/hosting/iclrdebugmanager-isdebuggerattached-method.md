---
description: 'Más información sobre: ICLRDebugManager:: Isdebuggerattached ((método)'
title: ICLRDebugManager::IsDebuggerAttached (Método)
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.IsDebuggerAttached
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::IsDebuggerAttached
helpviewer_keywords:
- IsDebuggerAttached method, ICLRDebugManager interface [.NET Framework hosting]
- ICLRDebugManager::IsDebuggerAttached method [.NET Framework hosting]
ms.assetid: 2f105fe0-f52d-49c5-bda5-583fb27e3aa6
topic_type:
- apiref
ms.openlocfilehash: 74305989797bcb553feb727a133e24bd308ac715
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772138"
---
# <a name="iclrdebugmanagerisdebuggerattached-method"></a><span data-ttu-id="e9c27-103">ICLRDebugManager::IsDebuggerAttached (Método)</span><span class="sxs-lookup"><span data-stu-id="e9c27-103">ICLRDebugManager::IsDebuggerAttached Method</span></span>

<span data-ttu-id="e9c27-104">Obtiene un valor que indica si hay un depurador asociado al proceso.</span><span class="sxs-lookup"><span data-stu-id="e9c27-104">Gets a value that indicates whether a debugger is attached to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9c27-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e9c27-105">Syntax</span></span>  
  
```cpp  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9c27-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e9c27-106">Parameters</span></span>  

 `pbAttached`  
 <span data-ttu-id="e9c27-107">[out] `true` Si hay un depurador asociado al proceso; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="e9c27-107">[out] `true` if a debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e9c27-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e9c27-108">Return Value</span></span>  
  
|<span data-ttu-id="e9c27-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e9c27-109">HRESULT</span></span>|<span data-ttu-id="e9c27-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="e9c27-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e9c27-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e9c27-111">S_OK</span></span>|<span data-ttu-id="e9c27-112">`IsDebuggerAttached` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="e9c27-112">`IsDebuggerAttached` returned successfully.</span></span>|  
|<span data-ttu-id="e9c27-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e9c27-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e9c27-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="e9c27-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e9c27-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e9c27-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e9c27-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="e9c27-116">The call timed out.</span></span>|  
|<span data-ttu-id="e9c27-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e9c27-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e9c27-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="e9c27-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e9c27-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e9c27-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e9c27-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="e9c27-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e9c27-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e9c27-121">E_FAIL</span></span>|<span data-ttu-id="e9c27-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="e9c27-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e9c27-123">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="e9c27-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e9c27-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e9c27-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9c27-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e9c27-125">Remarks</span></span>  

 <span data-ttu-id="e9c27-126">`IsDebuggerAttached` permite que el host consulte a CLR para determinar si hay un depurador asociado al proceso.</span><span class="sxs-lookup"><span data-stu-id="e9c27-126">`IsDebuggerAttached` allows the host to query the CLR to determine whether a debugger is attached to the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9c27-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e9c27-127">Requirements</span></span>  

 <span data-ttu-id="e9c27-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9c27-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9c27-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e9c27-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e9c27-130">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e9c27-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9c27-131">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9c27-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9c27-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9c27-132">See also</span></span>

- [<span data-ttu-id="e9c27-133">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e9c27-133">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="e9c27-134">ICLRDebugManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e9c27-134">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
- [<span data-ttu-id="e9c27-135">IHostControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e9c27-135">IHostControl Interface</span></span>](ihostcontrol-interface.md)
