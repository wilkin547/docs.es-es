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
ms.openlocfilehash: a21391f52a27e7f7a3abe533499c6b2581ec4a73
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615763"
---
# <a name="iclrdebugmanagerisdebuggerattached-method"></a><span data-ttu-id="bf649-102">ICLRDebugManager::IsDebuggerAttached (Método)</span><span class="sxs-lookup"><span data-stu-id="bf649-102">ICLRDebugManager::IsDebuggerAttached Method</span></span>
<span data-ttu-id="bf649-103">Obtiene un valor que indica si hay un depurador asociado al proceso.</span><span class="sxs-lookup"><span data-stu-id="bf649-103">Gets a value that indicates whether a debugger is attached to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf649-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bf649-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf649-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bf649-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="bf649-106">[out] `true` Si hay un depurador asociado al proceso; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="bf649-106">[out] `true` if a debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bf649-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bf649-107">Return Value</span></span>  
  
|<span data-ttu-id="bf649-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bf649-108">HRESULT</span></span>|<span data-ttu-id="bf649-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="bf649-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bf649-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="bf649-110">S_OK</span></span>|<span data-ttu-id="bf649-111">`IsDebuggerAttached`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="bf649-111">`IsDebuggerAttached` returned successfully.</span></span>|  
|<span data-ttu-id="bf649-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bf649-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bf649-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="bf649-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bf649-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bf649-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bf649-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="bf649-115">The call timed out.</span></span>|  
|<span data-ttu-id="bf649-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bf649-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bf649-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="bf649-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bf649-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bf649-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bf649-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="bf649-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bf649-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bf649-120">E_FAIL</span></span>|<span data-ttu-id="bf649-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="bf649-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bf649-122">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="bf649-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bf649-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="bf649-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf649-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bf649-124">Remarks</span></span>  
 <span data-ttu-id="bf649-125">`IsDebuggerAttached`permite que el host consulte a CLR para determinar si hay un depurador asociado al proceso.</span><span class="sxs-lookup"><span data-stu-id="bf649-125">`IsDebuggerAttached` allows the host to query the CLR to determine whether a debugger is attached to the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf649-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bf649-126">Requirements</span></span>  
 <span data-ttu-id="bf649-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf649-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf649-128">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="bf649-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bf649-129">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="bf649-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bf649-130">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf649-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf649-131">Consulta también</span><span class="sxs-lookup"><span data-stu-id="bf649-131">See also</span></span>

- [<span data-ttu-id="bf649-132">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bf649-132">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="bf649-133">ICLRDebugManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bf649-133">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
- [<span data-ttu-id="bf649-134">IHostControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bf649-134">IHostControl Interface</span></span>](ihostcontrol-interface.md)
