---
title: IHostControl::GetHostManager (Método)
ms.date: 03/30/2017
api_name:
- IHostControl.GetHostManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl::GetHostManager
helpviewer_keywords:
- GetHostManager method [.NET Framework hosting]
- IHostControl::GetHostManager method [.NET Framework hosting]
ms.assetid: 0fa34bca-ed18-4626-9e78-d33684d18edb
topic_type:
- apiref
ms.openlocfilehash: e340dcb5dc093f965e6c08a24a3d65ed0aa6e07a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680838"
---
# <a name="ihostcontrolgethostmanager-method"></a><span data-ttu-id="19ccd-102">IHostControl::GetHostManager (Método)</span><span class="sxs-lookup"><span data-stu-id="19ccd-102">IHostControl::GetHostManager Method</span></span>

<span data-ttu-id="19ccd-103">Obtiene un puntero de interfaz a la implementación del host de la interfaz con el especificado `IID` .</span><span class="sxs-lookup"><span data-stu-id="19ccd-103">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19ccd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="19ccd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHostManager (  
    [in] REFIID riid,  
    [out, iid_is(riid)] void** ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19ccd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="19ccd-105">Parameters</span></span>  

 `riid`  
 <span data-ttu-id="19ccd-106">de `IID` De la interfaz que el Common Language Runtime (CLR) está consultando.</span><span class="sxs-lookup"><span data-stu-id="19ccd-106">[in] The `IID` of the interface that the common language runtime (CLR) is querying for.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="19ccd-107">enuncia Un puntero a la interfaz implementada por el host, o null si el host no admite esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="19ccd-107">[out] A pointer to the host-implemented interface, or null if the host does not support this interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="19ccd-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="19ccd-108">Return Value</span></span>  
  
|<span data-ttu-id="19ccd-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="19ccd-109">HRESULT</span></span>|<span data-ttu-id="19ccd-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="19ccd-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="19ccd-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="19ccd-111">S_OK</span></span>|<span data-ttu-id="19ccd-112">`GetHostManager` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="19ccd-112">`GetHostManager` returned successfully.</span></span>|  
|<span data-ttu-id="19ccd-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="19ccd-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="19ccd-114">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="19ccd-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="19ccd-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="19ccd-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="19ccd-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="19ccd-116">The call timed out.</span></span>|  
|<span data-ttu-id="19ccd-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="19ccd-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="19ccd-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="19ccd-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="19ccd-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="19ccd-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="19ccd-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="19ccd-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="19ccd-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="19ccd-121">E_FAIL</span></span>|<span data-ttu-id="19ccd-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="19ccd-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="19ccd-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="19ccd-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="19ccd-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="19ccd-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="19ccd-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="19ccd-125">E_INVALIDARG</span></span>|<span data-ttu-id="19ccd-126">La solicitud solicitada `IID` no es válida.</span><span class="sxs-lookup"><span data-stu-id="19ccd-126">The requested `IID` is not valid.</span></span>|  
|<span data-ttu-id="19ccd-127">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="19ccd-127">E_NOINTERFACE</span></span>|<span data-ttu-id="19ccd-128">No se admite la interfaz solicitada.</span><span class="sxs-lookup"><span data-stu-id="19ccd-128">The requested interface is not supported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19ccd-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="19ccd-129">Remarks</span></span>  

 <span data-ttu-id="19ccd-130">CLR consulta el host para determinar si es compatible con una o varias de las interfaces siguientes:</span><span class="sxs-lookup"><span data-stu-id="19ccd-130">The CLR queries the host to determine whether it supports one or more of the following interfaces:</span></span>  
  
- [<span data-ttu-id="19ccd-131">IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="19ccd-131">IHostMemoryManager</span></span>](ihostmemorymanager-interface.md)  
  
- [<span data-ttu-id="19ccd-132">IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="19ccd-132">IHostTaskManager</span></span>](ihosttaskmanager-interface.md)  
  
- [<span data-ttu-id="19ccd-133">IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="19ccd-133">IHostThreadPoolManager</span></span>](ihostthreadpoolmanager-interface.md)  
  
- [<span data-ttu-id="19ccd-134">IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="19ccd-134">IHostIoCompletionManager</span></span>](ihostiocompletionmanager-interface.md)  
  
- [<span data-ttu-id="19ccd-135">IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="19ccd-135">IHostSyncManager</span></span>](ihostsyncmanager-interface.md)  
  
- [<span data-ttu-id="19ccd-136">IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="19ccd-136">IHostAssemblyManager</span></span>](ihostassemblymanager-interface.md)  
  
- [<span data-ttu-id="19ccd-137">IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="19ccd-137">IHostGCManager</span></span>](ihostgcmanager-interface.md)  
  
- [<span data-ttu-id="19ccd-138">IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="19ccd-138">IHostPolicyManager</span></span>](ihostpolicymanager-interface.md)  
  
- [<span data-ttu-id="19ccd-139">IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="19ccd-139">IHostSecurityManager</span></span>](ihostsecuritymanager-interface.md)  
  
 <span data-ttu-id="19ccd-140">Si el host admite la interfaz especificada, establece `ppObject` en su implementación de esa interfaz.</span><span class="sxs-lookup"><span data-stu-id="19ccd-140">If the host supports the specified interface, it sets `ppObject` to its implementation of that interface.</span></span> <span data-ttu-id="19ccd-141">De lo contrario, se establece `ppObject` en NULL.</span><span class="sxs-lookup"><span data-stu-id="19ccd-141">Otherwise, it sets `ppObject` to null.</span></span>  
  
 <span data-ttu-id="19ccd-142">CLR no llama a `Release` en los administradores de host, incluso cuando se apaga.</span><span class="sxs-lookup"><span data-stu-id="19ccd-142">The CLR does not call `Release` on host managers, even when you shut it down.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19ccd-143">Requisitos</span><span class="sxs-lookup"><span data-stu-id="19ccd-143">Requirements</span></span>  

 <span data-ttu-id="19ccd-144">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19ccd-144">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19ccd-145">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="19ccd-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="19ccd-146">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="19ccd-146">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="19ccd-147">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19ccd-147">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19ccd-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="19ccd-148">See also</span></span>

- [<span data-ttu-id="19ccd-149">IHostControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="19ccd-149">IHostControl Interface</span></span>](ihostcontrol-interface.md)
