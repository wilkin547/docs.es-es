---
title: IHostSyncManager::CreateRWLockReaderEvent (Método)
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateRWLockReaderEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateRWLockReaderEvent
helpviewer_keywords:
- CreateRWLockReaderEvent method [.NET Framework hosting]
- IHostSyncManager::CreateRWLockReaderEvent method [.NET Framework hosting]
ms.assetid: 68c4ea19-c47c-45c6-b420-d3a2ba1c2d50
topic_type:
- apiref
ms.openlocfilehash: 7c9bf2186d3dc4500694225ea4023df3609b9010
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704388"
---
# <a name="ihostsyncmanagercreaterwlockreaderevent-method"></a><span data-ttu-id="f6a2a-102">IHostSyncManager::CreateRWLockReaderEvent (Método)</span><span class="sxs-lookup"><span data-stu-id="f6a2a-102">IHostSyncManager::CreateRWLockReaderEvent Method</span></span>

<span data-ttu-id="f6a2a-103">Crea un objeto de evento de restablecimiento manual para la implementación de un bloqueo de lector.</span><span class="sxs-lookup"><span data-stu-id="f6a2a-103">Creates a manual-reset event object for the implementation of a reader lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6a2a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f6a2a-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateRWLockReaderEvent (  
    [in]  BOOL bInitialState,  
    [in]  SIZE_T cookie,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6a2a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f6a2a-105">Parameters</span></span>  

 `bInitialState`  
 <span data-ttu-id="f6a2a-106">[in] `true` , si `ppEvent` se debe señalizar; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="f6a2a-106">[in] `true`, if `ppEvent` should be signaled; otherwise, `false`.</span></span>  
  
 `cookie`  
 <span data-ttu-id="f6a2a-107">de Cookie que se va a asociar al bloqueo del lector.</span><span class="sxs-lookup"><span data-stu-id="f6a2a-107">[in] A cookie to associate with the reader lock.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="f6a2a-108">enuncia Un puntero a la dirección de una instancia de [IHostManualEvent](ihostmanualevent-interface.md) , o null si no se pudo crear el objeto de evento.</span><span class="sxs-lookup"><span data-stu-id="f6a2a-108">[out] A pointer to the address of an [IHostManualEvent](ihostmanualevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f6a2a-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f6a2a-109">Return Value</span></span>  
  
|<span data-ttu-id="f6a2a-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f6a2a-110">HRESULT</span></span>|<span data-ttu-id="f6a2a-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="f6a2a-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f6a2a-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="f6a2a-112">S_OK</span></span>|<span data-ttu-id="f6a2a-113">`CreateRWLockReaderEvent` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="f6a2a-113">`CreateRWLockReaderEvent` returned successfully.</span></span>|  
|<span data-ttu-id="f6a2a-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f6a2a-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f6a2a-115">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="f6a2a-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f6a2a-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f6a2a-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f6a2a-117">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f6a2a-117">The call timed out.</span></span>|  
|<span data-ttu-id="f6a2a-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f6a2a-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f6a2a-119">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="f6a2a-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f6a2a-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f6a2a-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f6a2a-121">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="f6a2a-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f6a2a-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f6a2a-122">E_FAIL</span></span>|<span data-ttu-id="f6a2a-123">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="f6a2a-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f6a2a-124">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="f6a2a-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f6a2a-125">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f6a2a-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f6a2a-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="f6a2a-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="f6a2a-127">No había suficiente memoria disponible para crear el objeto de evento solicitado.</span><span class="sxs-lookup"><span data-stu-id="f6a2a-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6a2a-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f6a2a-128">Remarks</span></span>  

 <span data-ttu-id="f6a2a-129">CLR llama `CreateRWLockReaderEvent` a para obtener una referencia a una `IHostManualEvent` instancia de que se va a utilizar en su implementación de un bloqueo de lector.</span><span class="sxs-lookup"><span data-stu-id="f6a2a-129">The CLR calls `CreateRWLockReaderEvent` to get a reference to an `IHostManualEvent` instance to use in its implementation of a reader lock.</span></span> <span data-ttu-id="f6a2a-130">El host puede usar la cookie para determinar qué tareas están esperando en el bloqueo del lector consultando la interfaz [ICLRSyncManager](iclrsyncmanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="f6a2a-130">The host can use the cookie to determine which tasks are waiting on the reader lock by querying the [ICLRSyncManager](iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6a2a-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f6a2a-131">Requirements</span></span>  

 <span data-ttu-id="f6a2a-132">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6a2a-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6a2a-133">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f6a2a-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f6a2a-134">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f6a2a-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f6a2a-135">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6a2a-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6a2a-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f6a2a-136">See also</span></span>

- [<span data-ttu-id="f6a2a-137">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f6a2a-137">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="f6a2a-138">IHostAutoEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f6a2a-138">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="f6a2a-139">IHostManualEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f6a2a-139">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="f6a2a-140">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f6a2a-140">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
