---
title: "IHostSyncManager::CreateMonitorEvent (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSyncManager.CreateMonitorEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSyncManager::CreateMonitorEvent
helpviewer_keywords:
- CreateMonitorEvent method [.NET Framework hosting]
- IHostSyncManager::CreateMonitorEvent method [.NET Framework hosting]
ms.assetid: 524c7fd3-9b5c-46e7-99ba-555fd2fe33f0
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ae12db71f4eae0f7d887fda26e05401f4f23ee5c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsyncmanagercreatemonitorevent-method"></a><span data-ttu-id="67c3b-102">IHostSyncManager::CreateMonitorEvent (Método)</span><span class="sxs-lookup"><span data-stu-id="67c3b-102">IHostSyncManager::CreateMonitorEvent Method</span></span>
<span data-ttu-id="67c3b-103">Crea un objeto de evento de restablecimiento automático supervisado.</span><span class="sxs-lookup"><span data-stu-id="67c3b-103">Creates a monitored auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67c3b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="67c3b-104">Syntax</span></span>  
  
```  
HRESULT CreateMonitorEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="67c3b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="67c3b-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="67c3b-106">[in] Cookie que se va a asociar con el objeto de evento.</span><span class="sxs-lookup"><span data-stu-id="67c3b-106">[in] A cookie to associate with the event object.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="67c3b-107">[out] Un puntero a la dirección de un [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instancia o null si no se pudo crear el objeto de evento.</span><span class="sxs-lookup"><span data-stu-id="67c3b-107">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="67c3b-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="67c3b-108">Return Value</span></span>  
  
|<span data-ttu-id="67c3b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="67c3b-109">HRESULT</span></span>|<span data-ttu-id="67c3b-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="67c3b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="67c3b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="67c3b-111">S_OK</span></span>|<span data-ttu-id="67c3b-112">`CreateMonitorEvent`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="67c3b-112">`CreateMonitorEvent` returned successfully.</span></span>|  
|<span data-ttu-id="67c3b-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="67c3b-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="67c3b-114">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="67c3b-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="67c3b-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="67c3b-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="67c3b-116">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="67c3b-116">The call timed out.</span></span>|  
|<span data-ttu-id="67c3b-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="67c3b-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="67c3b-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="67c3b-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="67c3b-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="67c3b-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="67c3b-120">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="67c3b-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="67c3b-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="67c3b-121">E_FAIL</span></span>|<span data-ttu-id="67c3b-122">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="67c3b-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="67c3b-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="67c3b-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="67c3b-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="67c3b-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="67c3b-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="67c3b-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="67c3b-126">No había memoria suficiente disponible para crear el objeto de evento solicitado.</span><span class="sxs-lookup"><span data-stu-id="67c3b-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67c3b-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="67c3b-127">Remarks</span></span>  
 <span data-ttu-id="67c3b-128">`CreateMonitorEvent`Devuelve un `IHostAutoEvent` que CLR usa en su implementación de los recursos administrados <xref:System.Threading.Monitor?displayProperty=nameWithType> tipo.</span><span class="sxs-lookup"><span data-stu-id="67c3b-128">`CreateMonitorEvent` returns an `IHostAutoEvent` that the CLR uses in its implementation of the managed <xref:System.Threading.Monitor?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="67c3b-129">Este método refleja el Win32 `CreateEvent` función, con un valor de `false` especificado para el `bManualReset` parámetro.</span><span class="sxs-lookup"><span data-stu-id="67c3b-129">This method mirrors the Win32 `CreateEvent` function, with a value of `false` specified for the `bManualReset` parameter.</span></span>  
  
 <span data-ttu-id="67c3b-130">El host puede utilizar la cookie para determinar qué tarea está esperando en el monitor mediante una llamada a la [ICLRSyncManager:: GetMonitorOwner](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="67c3b-130">The host can use the cookie to determine which task is waiting on the monitor by calling the [ICLRSyncManager::GetMonitorOwner](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67c3b-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="67c3b-131">Requirements</span></span>  
 <span data-ttu-id="67c3b-132">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67c3b-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67c3b-133">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="67c3b-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="67c3b-134">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="67c3b-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="67c3b-135">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67c3b-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67c3b-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="67c3b-136">See Also</span></span>  
 [<span data-ttu-id="67c3b-137">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="67c3b-137">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="67c3b-138">IHostAutoEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="67c3b-138">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="67c3b-139">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="67c3b-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 <span data-ttu-id="67c3b-140">[Monitors](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db) (Clases Monitor)</span><span class="sxs-lookup"><span data-stu-id="67c3b-140">[Monitors](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db)</span></span>
