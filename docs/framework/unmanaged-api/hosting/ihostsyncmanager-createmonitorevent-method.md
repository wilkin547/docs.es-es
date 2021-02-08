---
description: 'Más información acerca de: IHostSyncManager:: CreateMonitorEvent ((método)'
title: IHostSyncManager::CreateMonitorEvent (Método)
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateMonitorEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateMonitorEvent
helpviewer_keywords:
- CreateMonitorEvent method [.NET Framework hosting]
- IHostSyncManager::CreateMonitorEvent method [.NET Framework hosting]
ms.assetid: 524c7fd3-9b5c-46e7-99ba-555fd2fe33f0
topic_type:
- apiref
ms.openlocfilehash: b48d0417e614cf04c3ab150f0bdda73408b7a273
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784787"
---
# <a name="ihostsyncmanagercreatemonitorevent-method"></a><span data-ttu-id="5a3fe-103">IHostSyncManager::CreateMonitorEvent (Método)</span><span class="sxs-lookup"><span data-stu-id="5a3fe-103">IHostSyncManager::CreateMonitorEvent Method</span></span>

<span data-ttu-id="5a3fe-104">Crea un objeto de evento de restablecimiento automático supervisado.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-104">Creates a monitored auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a3fe-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5a3fe-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateMonitorEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a3fe-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5a3fe-106">Parameters</span></span>  

 `cookie`  
 <span data-ttu-id="5a3fe-107">de Cookie que se va a asociar al objeto de evento.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-107">[in] A cookie to associate with the event object.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="5a3fe-108">enuncia Puntero a la dirección de una instancia de [IHostAutoEvent](ihostautoevent-interface.md) o null si no se pudo crear el objeto de evento.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-108">[out] A pointer to the address of an [IHostAutoEvent](ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5a3fe-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5a3fe-109">Return Value</span></span>  
  
|<span data-ttu-id="5a3fe-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5a3fe-110">HRESULT</span></span>|<span data-ttu-id="5a3fe-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="5a3fe-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5a3fe-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="5a3fe-112">S_OK</span></span>|<span data-ttu-id="5a3fe-113">`CreateMonitorEvent` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-113">`CreateMonitorEvent` returned successfully.</span></span>|  
|<span data-ttu-id="5a3fe-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5a3fe-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5a3fe-115">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5a3fe-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5a3fe-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5a3fe-117">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-117">The call timed out.</span></span>|  
|<span data-ttu-id="5a3fe-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5a3fe-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5a3fe-119">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5a3fe-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5a3fe-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5a3fe-121">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5a3fe-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5a3fe-122">E_FAIL</span></span>|<span data-ttu-id="5a3fe-123">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5a3fe-124">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5a3fe-125">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="5a3fe-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="5a3fe-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="5a3fe-127">No había suficiente memoria disponible para crear el objeto de evento solicitado.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a3fe-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5a3fe-128">Remarks</span></span>  

 <span data-ttu-id="5a3fe-129">`CreateMonitorEvent` Devuelve un `IHostAutoEvent` que CLR usa en su implementación del <xref:System.Threading.Monitor?displayProperty=nameWithType> tipo administrado.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-129">`CreateMonitorEvent` returns an `IHostAutoEvent` that the CLR uses in its implementation of the managed <xref:System.Threading.Monitor?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="5a3fe-130">Este método refleja la `CreateEvent` función de Win32, con un valor de `false` especificado para el `bManualReset` parámetro.</span><span class="sxs-lookup"><span data-stu-id="5a3fe-130">This method mirrors the Win32 `CreateEvent` function, with a value of `false` specified for the `bManualReset` parameter.</span></span>  
  
 <span data-ttu-id="5a3fe-131">El host puede usar la cookie para determinar qué tarea está esperando en el monitor llamando al método [ICLRSyncManager:: GetMonitorOwner (](iclrsyncmanager-getmonitorowner-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5a3fe-131">The host can use the cookie to determine which task is waiting on the monitor by calling the [ICLRSyncManager::GetMonitorOwner](iclrsyncmanager-getmonitorowner-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a3fe-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5a3fe-132">Requirements</span></span>  

 <span data-ttu-id="5a3fe-133">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a3fe-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a3fe-134">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5a3fe-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5a3fe-135">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5a3fe-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5a3fe-136">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a3fe-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a3fe-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a3fe-137">See also</span></span>

- [<span data-ttu-id="5a3fe-138">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5a3fe-138">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="5a3fe-139">IHostAutoEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5a3fe-139">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="5a3fe-140">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5a3fe-140">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- <xref:System.Threading.Monitor>
