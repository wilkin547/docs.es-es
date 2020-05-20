---
title: ICLRGCManager::Collect (Método)
ms.date: 03/30/2017
api_name:
- ICLRGCManager.Collect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::Collect
helpviewer_keywords:
- ICLRGCManager::Collect method [.NET Framework hosting]
- Collect method, ICLRGCManager interface [.NET Framework hosting]
ms.assetid: 0c6cbbea-c27c-4695-bda3-17c1910d8ddb
topic_type:
- apiref
ms.openlocfilehash: aa906e314c408b7653e611b07d7ad21d4519b715
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616988"
---
# <a name="iclrgcmanagercollect-method"></a><span data-ttu-id="78355-102">ICLRGCManager::Collect (Método)</span><span class="sxs-lookup"><span data-stu-id="78355-102">ICLRGCManager::Collect Method</span></span>
<span data-ttu-id="78355-103">Fuerza una recolección de elementos no utilizados para la generación especificada.</span><span class="sxs-lookup"><span data-stu-id="78355-103">Forces a garbage collection for the specified generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78355-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="78355-104">Syntax</span></span>  
  
```cpp  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78355-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="78355-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="78355-106">de Generación que se va a recopilar.</span><span class="sxs-lookup"><span data-stu-id="78355-106">[in] The generation to collect.</span></span> <span data-ttu-id="78355-107">Un valor de-1 fuerza una colección de todas las generaciones.</span><span class="sxs-lookup"><span data-stu-id="78355-107">A value of -1 forces a collection of all generations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="78355-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="78355-108">Return Value</span></span>  
  
|<span data-ttu-id="78355-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="78355-109">HRESULT</span></span>|<span data-ttu-id="78355-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="78355-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="78355-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="78355-111">S_OK</span></span>|<span data-ttu-id="78355-112">`Collect`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="78355-112">`Collect` returned successfully.</span></span>|  
|<span data-ttu-id="78355-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="78355-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="78355-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="78355-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="78355-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="78355-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="78355-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78355-116">The call timed out.</span></span>|  
|<span data-ttu-id="78355-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="78355-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="78355-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="78355-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="78355-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="78355-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="78355-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="78355-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="78355-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="78355-121">E_FAIL</span></span>|<span data-ttu-id="78355-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="78355-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="78355-123">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="78355-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="78355-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="78355-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78355-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="78355-125">Remarks</span></span>  
 <span data-ttu-id="78355-126">El `Collect` método obliga al recolector de elementos no utilizados de CLR a realizar una recolección, independientemente de su estado actual.</span><span class="sxs-lookup"><span data-stu-id="78355-126">The `Collect` method forces the CLR's garbage collector to perform a collection regardless of its current state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78355-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="78355-127">Requirements</span></span>  
 <span data-ttu-id="78355-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78355-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78355-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="78355-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="78355-130">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="78355-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="78355-131">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78355-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78355-132">Consulta también</span><span class="sxs-lookup"><span data-stu-id="78355-132">See also</span></span>

- [<span data-ttu-id="78355-133">Administración de memoria automática</span><span class="sxs-lookup"><span data-stu-id="78355-133">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="78355-134">Recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="78355-134">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="78355-135">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="78355-135">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="78355-136">ICLRGCManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="78355-136">ICLRGCManager Interface</span></span>](iclrgcmanager-interface.md)
- [<span data-ttu-id="78355-137">Interfaces de hospedaje de CLR</span><span class="sxs-lookup"><span data-stu-id="78355-137">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)
- [<span data-ttu-id="78355-138">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="78355-138">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="78355-139">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="78355-139">Hosting</span></span>](index.md)
