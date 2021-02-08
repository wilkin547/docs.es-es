---
description: 'Más información acerca de: IHostSyncManager:: Createrwlockwriterevent ((método)'
title: IHostSyncManager::CreateRWLockWriterEvent (Método)
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateRWLockWriterEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateRWLockWriterEvent
helpviewer_keywords:
- CreateRWLockWriterEvent method [.NET Framework hosting]
- IHostSyncManager::CreateRWLockWriterEvent method [.NET Framework hosting]
ms.assetid: 70e488c2-cf53-4dc0-ba52-74372d215c41
topic_type:
- apiref
ms.openlocfilehash: 509f18ff49966e5da3a25e39258d33caf69249a0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784761"
---
# <a name="ihostsyncmanagercreaterwlockwriterevent-method"></a><span data-ttu-id="c373b-103">IHostSyncManager::CreateRWLockWriterEvent (Método)</span><span class="sxs-lookup"><span data-stu-id="c373b-103">IHostSyncManager::CreateRWLockWriterEvent Method</span></span>

<span data-ttu-id="c373b-104">Crea un objeto de evento de restablecimiento automático para la implementación de un bloqueo de escritor.</span><span class="sxs-lookup"><span data-stu-id="c373b-104">Creates an auto-reset event object for the implementation of a writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c373b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c373b-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateRWLockWriterEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c373b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c373b-106">Parameters</span></span>  

 `cookie`  
 <span data-ttu-id="c373b-107">de Cookie que se va a asociar al evento de restablecimiento automático.</span><span class="sxs-lookup"><span data-stu-id="c373b-107">[in] A cookie to associate with the auto-reset event.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="c373b-108">enuncia Puntero a la dirección de una instancia de [IHostAutoEvent](ihostautoevent-interface.md) o null si no se pudo crear el objeto de evento.</span><span class="sxs-lookup"><span data-stu-id="c373b-108">[out] A pointer to the address of an [IHostAutoEvent](ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c373b-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c373b-109">Return Value</span></span>  
  
|<span data-ttu-id="c373b-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c373b-110">HRESULT</span></span>|<span data-ttu-id="c373b-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="c373b-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c373b-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="c373b-112">S_OK</span></span>|<span data-ttu-id="c373b-113">`CreateRWLockWriterEvent` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="c373b-113">`CreateRWLockWriterEvent` returned successfully.</span></span>|  
|<span data-ttu-id="c373b-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c373b-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c373b-115">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="c373b-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c373b-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c373b-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c373b-117">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="c373b-117">The call timed out.</span></span>|  
|<span data-ttu-id="c373b-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c373b-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c373b-119">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="c373b-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c373b-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c373b-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c373b-121">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="c373b-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c373b-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c373b-122">E_FAIL</span></span>|<span data-ttu-id="c373b-123">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="c373b-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c373b-124">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="c373b-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c373b-125">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c373b-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c373b-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="c373b-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="c373b-127">No había suficiente memoria disponible para crear el objeto de evento solicitado.</span><span class="sxs-lookup"><span data-stu-id="c373b-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c373b-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c373b-128">Remarks</span></span>  

 <span data-ttu-id="c373b-129">CLR llama al `CreateRWLockWriterEvent` método para obtener una referencia a una `IHostAutoEvent` instancia de que se va a utilizar en su implementación de un bloqueo de escritor.</span><span class="sxs-lookup"><span data-stu-id="c373b-129">The CLR calls the `CreateRWLockWriterEvent` method to get a reference to an `IHostAutoEvent` instance to use in its implementation of a writer lock.</span></span> <span data-ttu-id="c373b-130">El host puede usar la cookie especificada para determinar qué tareas están esperando en el bloqueo mediante una llamada a los métodos de iteración de la interfaz [ICLRSyncManager](iclrsyncmanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="c373b-130">The host can use the specified cookie to determine which tasks are waiting on the lock by calling the iteration methods of the [ICLRSyncManager](iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c373b-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c373b-131">Requirements</span></span>  

 <span data-ttu-id="c373b-132">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c373b-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c373b-133">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c373b-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c373b-134">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c373b-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c373b-135">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c373b-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c373b-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="c373b-136">See also</span></span>

- [<span data-ttu-id="c373b-137">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c373b-137">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="c373b-138">IHostAutoEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c373b-138">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="c373b-139">IHostManualEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c373b-139">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="c373b-140">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c373b-140">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
