---
title: "IHostTaskManager::BeginThreadAffinity (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.BeginThreadAffinity
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::BeginThreadAffinity
helpviewer_keywords:
- IHostTaskManager::BeginThreadAffinity method [.NET Framework hosting]
- BeginThreadAffinity method [.NET Framework hosting]
ms.assetid: fea3ab88-ce41-4c5a-847b-bb78cd748da6
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9c86473fba6447bc97619aeb6a6d7b10472120fc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttaskmanagerbeginthreadaffinity-method"></a><span data-ttu-id="820db-102">IHostTaskManager::BeginThreadAffinity (Método)</span><span class="sxs-lookup"><span data-stu-id="820db-102">IHostTaskManager::BeginThreadAffinity Method</span></span>
<span data-ttu-id="820db-103">Notifica al host que el código administrado está entrando en un período en el que la tarea actual no se mueven a otro subproceso del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="820db-103">Notifies the host that managed code is entering a period in which the current task must not be moved to another operating system thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="820db-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="820db-104">Syntax</span></span>  
  
```  
HRESULT BeginThreadAffinity ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="820db-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="820db-105">Return Value</span></span>  
  
|<span data-ttu-id="820db-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="820db-106">HRESULT</span></span>|<span data-ttu-id="820db-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="820db-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="820db-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="820db-108">S_OK</span></span>|<span data-ttu-id="820db-109">`BeginThreadAffinity`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="820db-109">`BeginThreadAffinity` returned successfully.</span></span>|  
|<span data-ttu-id="820db-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="820db-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="820db-111">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="820db-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="820db-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="820db-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="820db-113">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="820db-113">The call timed out.</span></span>|  
|<span data-ttu-id="820db-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="820db-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="820db-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="820db-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="820db-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="820db-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="820db-117">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="820db-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="820db-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="820db-118">E_FAIL</span></span>|<span data-ttu-id="820db-119">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="820db-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="820db-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="820db-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="820db-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="820db-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="820db-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="820db-122">Remarks</span></span>  
 <span data-ttu-id="820db-123">CLR llama normalmente `IHostTaskManager::BeginThreadAffinity` en el contexto de una llamada a <xref:System.Threading.Thread.BeginThreadAffinity%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="820db-123">The CLR typically calls `IHostTaskManager::BeginThreadAffinity` in the context of a call to <xref:System.Threading.Thread.BeginThreadAffinity%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="820db-124">No se debe programar la tarea actual hasta que se realiza una llamada correspondiente a [IHostTaskManager:: EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md).</span><span class="sxs-lookup"><span data-stu-id="820db-124">The current task must not be rescheduled until a corresponding call is made to [IHostTaskManager::EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md).</span></span> <span data-ttu-id="820db-125">Las tareas se pueden cambiar a, pero cuando se cambian en, deben asignarse en el mismo subproceso de sistema operativo desde el que se intercambiaron out. Anidar las llamadas a `BeginThreadAffinity` no tienen ningún efecto, porque la llamada hace referencia a la tarea actual.</span><span class="sxs-lookup"><span data-stu-id="820db-125">Tasks can be switched out, but when they are switched back in, they must be assigned to the same operating system thread from which they were switched out. Nested calls to `BeginThreadAffinity` have no effect, because the call refers to the current task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="820db-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="820db-126">Requirements</span></span>  
 <span data-ttu-id="820db-127">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="820db-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="820db-128">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="820db-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="820db-129">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="820db-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="820db-130">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="820db-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="820db-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="820db-131">See Also</span></span>  
 [<span data-ttu-id="820db-132">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="820db-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="820db-133">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="820db-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="820db-134">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="820db-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="820db-135">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="820db-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
