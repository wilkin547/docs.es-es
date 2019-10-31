---
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
ms.openlocfilehash: 13eb23c530a4fe1b491f41cc65cc94dacc9d34f4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192003"
---
# <a name="ihostsyncmanagercreaterwlockwriterevent-method"></a><span data-ttu-id="2bf1a-102">IHostSyncManager::CreateRWLockWriterEvent (Método)</span><span class="sxs-lookup"><span data-stu-id="2bf1a-102">IHostSyncManager::CreateRWLockWriterEvent Method</span></span>
<span data-ttu-id="2bf1a-103">Crea un objeto de evento de restablecimiento automático para la implementación de un bloqueo de escritor.</span><span class="sxs-lookup"><span data-stu-id="2bf1a-103">Creates an auto-reset event object for the implementation of a writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bf1a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2bf1a-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateRWLockWriterEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2bf1a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2bf1a-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="2bf1a-106">de Cookie que se va a asociar al evento de restablecimiento automático.</span><span class="sxs-lookup"><span data-stu-id="2bf1a-106">[in] A cookie to associate with the auto-reset event.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="2bf1a-107">enuncia Puntero a la dirección de una instancia de [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) o null si no se pudo crear el objeto de evento.</span><span class="sxs-lookup"><span data-stu-id="2bf1a-107">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2bf1a-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2bf1a-108">Return Value</span></span>  
  
|<span data-ttu-id="2bf1a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2bf1a-109">HRESULT</span></span>|<span data-ttu-id="2bf1a-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="2bf1a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2bf1a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2bf1a-111">S_OK</span></span>|<span data-ttu-id="2bf1a-112">`CreateRWLockWriterEvent` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="2bf1a-112">`CreateRWLockWriterEvent` returned successfully.</span></span>|  
|<span data-ttu-id="2bf1a-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2bf1a-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2bf1a-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="2bf1a-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2bf1a-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2bf1a-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2bf1a-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2bf1a-116">The call timed out.</span></span>|  
|<span data-ttu-id="2bf1a-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2bf1a-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2bf1a-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="2bf1a-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2bf1a-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2bf1a-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2bf1a-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="2bf1a-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2bf1a-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2bf1a-121">E_FAIL</span></span>|<span data-ttu-id="2bf1a-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="2bf1a-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2bf1a-123">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="2bf1a-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2bf1a-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2bf1a-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2bf1a-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="2bf1a-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="2bf1a-126">No había suficiente memoria disponible para crear el objeto de evento solicitado.</span><span class="sxs-lookup"><span data-stu-id="2bf1a-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2bf1a-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2bf1a-127">Remarks</span></span>  
 <span data-ttu-id="2bf1a-128">CLR llama al método `CreateRWLockWriterEvent` para obtener una referencia a una instancia de `IHostAutoEvent` que se va a utilizar en su implementación de un bloqueo de escritor.</span><span class="sxs-lookup"><span data-stu-id="2bf1a-128">The CLR calls the `CreateRWLockWriterEvent` method to get a reference to an `IHostAutoEvent` instance to use in its implementation of a writer lock.</span></span> <span data-ttu-id="2bf1a-129">El host puede usar la cookie especificada para determinar qué tareas están esperando en el bloqueo mediante una llamada a los métodos de iteración de la interfaz [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="2bf1a-129">The host can use the specified cookie to determine which tasks are waiting on the lock by calling the iteration methods of the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bf1a-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2bf1a-130">Requirements</span></span>  
 <span data-ttu-id="2bf1a-131">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2bf1a-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bf1a-132">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2bf1a-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2bf1a-133">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2bf1a-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2bf1a-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bf1a-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bf1a-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="2bf1a-135">See also</span></span>

- [<span data-ttu-id="2bf1a-136">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2bf1a-136">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="2bf1a-137">IHostAutoEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2bf1a-137">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="2bf1a-138">IHostManualEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2bf1a-138">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="2bf1a-139">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2bf1a-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
