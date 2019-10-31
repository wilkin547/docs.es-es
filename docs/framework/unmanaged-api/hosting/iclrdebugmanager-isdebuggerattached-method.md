---
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
ms.openlocfilehash: a58fcb6c1fa2aad96cdd29194a21eaf590536cdd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129393"
---
# <a name="iclrdebugmanagerisdebuggerattached-method"></a><span data-ttu-id="0e5dc-102">ICLRDebugManager::IsDebuggerAttached (Método)</span><span class="sxs-lookup"><span data-stu-id="0e5dc-102">ICLRDebugManager::IsDebuggerAttached Method</span></span>
<span data-ttu-id="0e5dc-103">Obtiene un valor que indica si hay un depurador asociado al proceso.</span><span class="sxs-lookup"><span data-stu-id="0e5dc-103">Gets a value that indicates whether a debugger is attached to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e5dc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0e5dc-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e5dc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0e5dc-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="0e5dc-106">[out] `true` si hay un depurador asociado al proceso; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="0e5dc-106">[out] `true` if a debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0e5dc-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0e5dc-107">Return Value</span></span>  
  
|<span data-ttu-id="0e5dc-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0e5dc-108">HRESULT</span></span>|<span data-ttu-id="0e5dc-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="0e5dc-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0e5dc-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0e5dc-110">S_OK</span></span>|<span data-ttu-id="0e5dc-111">`IsDebuggerAttached` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="0e5dc-111">`IsDebuggerAttached` returned successfully.</span></span>|  
|<span data-ttu-id="0e5dc-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0e5dc-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0e5dc-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="0e5dc-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0e5dc-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0e5dc-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0e5dc-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0e5dc-115">The call timed out.</span></span>|  
|<span data-ttu-id="0e5dc-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0e5dc-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0e5dc-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="0e5dc-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0e5dc-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0e5dc-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0e5dc-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="0e5dc-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0e5dc-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0e5dc-120">E_FAIL</span></span>|<span data-ttu-id="0e5dc-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="0e5dc-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0e5dc-122">Una vez que un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="0e5dc-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0e5dc-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0e5dc-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e5dc-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0e5dc-124">Remarks</span></span>  
 <span data-ttu-id="0e5dc-125">`IsDebuggerAttached` permite que el host consulte a CLR para determinar si hay un depurador asociado al proceso.</span><span class="sxs-lookup"><span data-stu-id="0e5dc-125">`IsDebuggerAttached` allows the host to query the CLR to determine whether a debugger is attached to the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e5dc-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0e5dc-126">Requirements</span></span>  
 <span data-ttu-id="0e5dc-127">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e5dc-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e5dc-128">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0e5dc-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0e5dc-129">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0e5dc-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0e5dc-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e5dc-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e5dc-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="0e5dc-131">See also</span></span>

- [<span data-ttu-id="0e5dc-132">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0e5dc-132">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="0e5dc-133">ICLRDebugManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0e5dc-133">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="0e5dc-134">IHostControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0e5dc-134">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
