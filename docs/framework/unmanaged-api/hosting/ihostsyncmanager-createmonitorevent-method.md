---
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
ms.openlocfilehash: f7426585045c7ae81377ec9bfca9d397d6f734cb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192013"
---
# <a name="ihostsyncmanagercreatemonitorevent-method"></a><span data-ttu-id="71a59-102">IHostSyncManager::CreateMonitorEvent (Método)</span><span class="sxs-lookup"><span data-stu-id="71a59-102">IHostSyncManager::CreateMonitorEvent Method</span></span>
<span data-ttu-id="71a59-103">Crea un objeto de evento de restablecimiento automático supervisado.</span><span class="sxs-lookup"><span data-stu-id="71a59-103">Creates a monitored auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71a59-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="71a59-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateMonitorEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71a59-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="71a59-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="71a59-106">de Cookie que se va a asociar al objeto de evento.</span><span class="sxs-lookup"><span data-stu-id="71a59-106">[in] A cookie to associate with the event object.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="71a59-107">enuncia Puntero a la dirección de una instancia de [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) o null si no se pudo crear el objeto de evento.</span><span class="sxs-lookup"><span data-stu-id="71a59-107">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="71a59-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="71a59-108">Return Value</span></span>  
  
|<span data-ttu-id="71a59-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="71a59-109">HRESULT</span></span>|<span data-ttu-id="71a59-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="71a59-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="71a59-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="71a59-111">S_OK</span></span>|<span data-ttu-id="71a59-112">`CreateMonitorEvent` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="71a59-112">`CreateMonitorEvent` returned successfully.</span></span>|  
|<span data-ttu-id="71a59-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="71a59-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="71a59-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="71a59-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="71a59-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="71a59-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="71a59-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="71a59-116">The call timed out.</span></span>|  
|<span data-ttu-id="71a59-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="71a59-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="71a59-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="71a59-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="71a59-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="71a59-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="71a59-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="71a59-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="71a59-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="71a59-121">E_FAIL</span></span>|<span data-ttu-id="71a59-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="71a59-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="71a59-123">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="71a59-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="71a59-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="71a59-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="71a59-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="71a59-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="71a59-126">No había suficiente memoria disponible para crear el objeto de evento solicitado.</span><span class="sxs-lookup"><span data-stu-id="71a59-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71a59-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="71a59-127">Remarks</span></span>  
 <span data-ttu-id="71a59-128">`CreateMonitorEvent` devuelve un `IHostAutoEvent` que CLR usa en su implementación del tipo de <xref:System.Threading.Monitor?displayProperty=nameWithType> administrado.</span><span class="sxs-lookup"><span data-stu-id="71a59-128">`CreateMonitorEvent` returns an `IHostAutoEvent` that the CLR uses in its implementation of the managed <xref:System.Threading.Monitor?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="71a59-129">Este método refleja la función de `CreateEvent` de Win32, con un valor de `false` especificado para el parámetro `bManualReset`.</span><span class="sxs-lookup"><span data-stu-id="71a59-129">This method mirrors the Win32 `CreateEvent` function, with a value of `false` specified for the `bManualReset` parameter.</span></span>  
  
 <span data-ttu-id="71a59-130">El host puede usar la cookie para determinar qué tarea está esperando en el monitor llamando al método [ICLRSyncManager:: GetMonitorOwner (](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md) .</span><span class="sxs-lookup"><span data-stu-id="71a59-130">The host can use the cookie to determine which task is waiting on the monitor by calling the [ICLRSyncManager::GetMonitorOwner](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71a59-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="71a59-131">Requirements</span></span>  
 <span data-ttu-id="71a59-132">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71a59-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71a59-133">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="71a59-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="71a59-134">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="71a59-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="71a59-135">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71a59-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71a59-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="71a59-136">See also</span></span>

- [<span data-ttu-id="71a59-137">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="71a59-137">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="71a59-138">IHostAutoEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="71a59-138">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="71a59-139">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="71a59-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- <xref:System.Threading.Monitor>
