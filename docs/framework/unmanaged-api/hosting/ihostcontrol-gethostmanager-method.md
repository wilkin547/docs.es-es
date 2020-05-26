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
ms.openlocfilehash: 25e931ec17cad3508d548fb4ca7e53b0ade3f119
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804955"
---
# <a name="ihostcontrolgethostmanager-method"></a><span data-ttu-id="154c6-102">IHostControl::GetHostManager (Método)</span><span class="sxs-lookup"><span data-stu-id="154c6-102">IHostControl::GetHostManager Method</span></span>
<span data-ttu-id="154c6-103">Obtiene un puntero de interfaz a la implementación del host de la interfaz con el especificado `IID` .</span><span class="sxs-lookup"><span data-stu-id="154c6-103">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="154c6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="154c6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHostManager (  
    [in] REFIID riid,  
    [out, iid_is(riid)] void** ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="154c6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="154c6-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="154c6-106">de `IID`De la interfaz que el Common Language Runtime (CLR) está consultando.</span><span class="sxs-lookup"><span data-stu-id="154c6-106">[in] The `IID` of the interface that the common language runtime (CLR) is querying for.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="154c6-107">enuncia Un puntero a la interfaz implementada por el host, o null si el host no admite esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="154c6-107">[out] A pointer to the host-implemented interface, or null if the host does not support this interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="154c6-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="154c6-108">Return Value</span></span>  
  
|<span data-ttu-id="154c6-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="154c6-109">HRESULT</span></span>|<span data-ttu-id="154c6-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="154c6-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="154c6-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="154c6-111">S_OK</span></span>|<span data-ttu-id="154c6-112">`GetHostManager`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="154c6-112">`GetHostManager` returned successfully.</span></span>|  
|<span data-ttu-id="154c6-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="154c6-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="154c6-114">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="154c6-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="154c6-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="154c6-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="154c6-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="154c6-116">The call timed out.</span></span>|  
|<span data-ttu-id="154c6-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="154c6-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="154c6-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="154c6-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="154c6-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="154c6-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="154c6-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="154c6-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="154c6-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="154c6-121">E_FAIL</span></span>|<span data-ttu-id="154c6-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="154c6-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="154c6-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="154c6-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="154c6-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="154c6-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="154c6-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="154c6-125">E_INVALIDARG</span></span>|<span data-ttu-id="154c6-126">La solicitud solicitada `IID` no es válida.</span><span class="sxs-lookup"><span data-stu-id="154c6-126">The requested `IID` is not valid.</span></span>|  
|<span data-ttu-id="154c6-127">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="154c6-127">E_NOINTERFACE</span></span>|<span data-ttu-id="154c6-128">No se admite la interfaz solicitada.</span><span class="sxs-lookup"><span data-stu-id="154c6-128">The requested interface is not supported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="154c6-129">Observaciones</span><span class="sxs-lookup"><span data-stu-id="154c6-129">Remarks</span></span>  
 <span data-ttu-id="154c6-130">CLR consulta el host para determinar si es compatible con una o varias de las interfaces siguientes:</span><span class="sxs-lookup"><span data-stu-id="154c6-130">The CLR queries the host to determine whether it supports one or more of the following interfaces:</span></span>  
  
- [<span data-ttu-id="154c6-131">IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="154c6-131">IHostMemoryManager</span></span>](ihostmemorymanager-interface.md)  
  
- [<span data-ttu-id="154c6-132">IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="154c6-132">IHostTaskManager</span></span>](ihosttaskmanager-interface.md)  
  
- [<span data-ttu-id="154c6-133">IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="154c6-133">IHostThreadPoolManager</span></span>](ihostthreadpoolmanager-interface.md)  
  
- [<span data-ttu-id="154c6-134">IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="154c6-134">IHostIoCompletionManager</span></span>](ihostiocompletionmanager-interface.md)  
  
- [<span data-ttu-id="154c6-135">IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="154c6-135">IHostSyncManager</span></span>](ihostsyncmanager-interface.md)  
  
- [<span data-ttu-id="154c6-136">IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="154c6-136">IHostAssemblyManager</span></span>](ihostassemblymanager-interface.md)  
  
- [<span data-ttu-id="154c6-137">IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="154c6-137">IHostGCManager</span></span>](ihostgcmanager-interface.md)  
  
- [<span data-ttu-id="154c6-138">IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="154c6-138">IHostPolicyManager</span></span>](ihostpolicymanager-interface.md)  
  
- [<span data-ttu-id="154c6-139">IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="154c6-139">IHostSecurityManager</span></span>](ihostsecuritymanager-interface.md)  
  
 <span data-ttu-id="154c6-140">Si el host admite la interfaz especificada, establece `ppObject` en su implementación de esa interfaz.</span><span class="sxs-lookup"><span data-stu-id="154c6-140">If the host supports the specified interface, it sets `ppObject` to its implementation of that interface.</span></span> <span data-ttu-id="154c6-141">De lo contrario, se establece `ppObject` en NULL.</span><span class="sxs-lookup"><span data-stu-id="154c6-141">Otherwise, it sets `ppObject` to null.</span></span>  
  
 <span data-ttu-id="154c6-142">CLR no llama a `Release` en los administradores de host, incluso cuando se apaga.</span><span class="sxs-lookup"><span data-stu-id="154c6-142">The CLR does not call `Release` on host managers, even when you shut it down.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="154c6-143">Requisitos</span><span class="sxs-lookup"><span data-stu-id="154c6-143">Requirements</span></span>  
 <span data-ttu-id="154c6-144">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="154c6-144">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="154c6-145">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="154c6-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="154c6-146">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="154c6-146">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="154c6-147">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="154c6-147">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="154c6-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="154c6-148">See also</span></span>

- [<span data-ttu-id="154c6-149">IHostControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="154c6-149">IHostControl Interface</span></span>](ihostcontrol-interface.md)
