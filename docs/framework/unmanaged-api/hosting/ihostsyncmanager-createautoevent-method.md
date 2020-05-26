---
title: IHostSyncManager::CreateAutoEvent (Método)
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateAutoEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateAutoEvent
helpviewer_keywords:
- IHostSyncManager::CreateAutoEvent method [.NET Framework hosting]
- CreateAutoEvent method [.NET Framework hosting]
ms.assetid: 3153643e-cf5c-4b44-8e0e-c2b22cb08208
topic_type:
- apiref
ms.openlocfilehash: ba221beaa0edce49e75f75edddaee72e1beb9747
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803502"
---
# <a name="ihostsyncmanagercreateautoevent-method"></a><span data-ttu-id="ca9f6-102">IHostSyncManager::CreateAutoEvent (Método)</span><span class="sxs-lookup"><span data-stu-id="ca9f6-102">IHostSyncManager::CreateAutoEvent Method</span></span>
<span data-ttu-id="ca9f6-103">Crea un objeto de evento de restablecimiento automático.</span><span class="sxs-lookup"><span data-stu-id="ca9f6-103">Creates an auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca9f6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ca9f6-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAutoEvent (  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca9f6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ca9f6-105">Parameters</span></span>  
 `ppEvent`  
 <span data-ttu-id="ca9f6-106">enuncia Un puntero a la dirección de una instancia de [IHostAutoEvent](ihostautoevent-interface.md) implementada por el host, o null si no se pudo crear el objeto de evento.</span><span class="sxs-lookup"><span data-stu-id="ca9f6-106">[out] A pointer to the address of an [IHostAutoEvent](ihostautoevent-interface.md) instance implemented by the host, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ca9f6-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ca9f6-107">Return Value</span></span>  
  
|<span data-ttu-id="ca9f6-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ca9f6-108">HRESULT</span></span>|<span data-ttu-id="ca9f6-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="ca9f6-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ca9f6-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ca9f6-110">S_OK</span></span>|<span data-ttu-id="ca9f6-111">`CreateAutoEvent`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="ca9f6-111">`CreateAutoEvent` returned successfully.</span></span>|  
|<span data-ttu-id="ca9f6-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ca9f6-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ca9f6-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="ca9f6-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ca9f6-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ca9f6-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ca9f6-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="ca9f6-115">The call timed out.</span></span>|  
|<span data-ttu-id="ca9f6-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ca9f6-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ca9f6-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="ca9f6-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ca9f6-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ca9f6-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ca9f6-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="ca9f6-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ca9f6-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ca9f6-120">E_FAIL</span></span>|<span data-ttu-id="ca9f6-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="ca9f6-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ca9f6-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="ca9f6-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ca9f6-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ca9f6-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ca9f6-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="ca9f6-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="ca9f6-125">No había suficiente memoria disponible para crear el objeto de evento solicitado.</span><span class="sxs-lookup"><span data-stu-id="ca9f6-125">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca9f6-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ca9f6-126">Remarks</span></span>  
 <span data-ttu-id="ca9f6-127">`CreateAutoEvent`crea un objeto de evento automático cuyo estado se cambia automáticamente a no señalizado después de que se haya liberado el subproceso en espera.</span><span class="sxs-lookup"><span data-stu-id="ca9f6-127">`CreateAutoEvent` creates an auto-event object whose state is automatically changed to non-signaled after the waiting thread has been released.</span></span> <span data-ttu-id="ca9f6-128">Este método refleja la `CreateEvent` función de Win32 con el valor `false` especificado para el `bManualReset` parámetro.</span><span class="sxs-lookup"><span data-stu-id="ca9f6-128">This method mirrors the Win32 `CreateEvent` function with a value of `false` specified for the `bManualReset` parameter</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca9f6-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ca9f6-129">Requirements</span></span>  
 <span data-ttu-id="ca9f6-130">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca9f6-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca9f6-131">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ca9f6-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ca9f6-132">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ca9f6-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ca9f6-133">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca9f6-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca9f6-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ca9f6-134">See also</span></span>

- [<span data-ttu-id="ca9f6-135">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ca9f6-135">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="ca9f6-136">IHostAutoEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ca9f6-136">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="ca9f6-137">IHostControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ca9f6-137">IHostControl Interface</span></span>](ihostcontrol-interface.md)
- [<span data-ttu-id="ca9f6-138">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ca9f6-138">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
