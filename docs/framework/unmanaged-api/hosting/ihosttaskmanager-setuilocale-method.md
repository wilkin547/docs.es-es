---
title: "IHostTaskManager::SetUILocale (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.SetUILocale
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::SetUILocale
helpviewer_keywords:
- SetUILocale method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::SetUILocale method [.NET Framework hosting]
ms.assetid: d0c87a9c-ea81-4237-a16b-c22b36ec9dc8
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 099c3d4878e7dd83be9240e121777c71c2890c88
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttaskmanagersetuilocale-method"></a><span data-ttu-id="4fc76-102">IHostTaskManager::SetUILocale (Método)</span><span class="sxs-lookup"><span data-stu-id="4fc76-102">IHostTaskManager::SetUILocale Method</span></span>
<span data-ttu-id="4fc76-103">Notifica al host que common language runtime (CLR) ha cambiado la configuración regional del usuario (UI) de la interfaz o la referencia cultural en la tarea que se ejecuta actualmente.</span><span class="sxs-lookup"><span data-stu-id="4fc76-103">Notifies the host that the common language runtime (CLR) has changed the user interface (UI) locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fc76-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4fc76-104">Syntax</span></span>  
  
```  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4fc76-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4fc76-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="4fc76-106">[in] El valor de identificador de configuración regional que se asigna a un idioma y la referencia cultural geográfica recién asignada.</span><span class="sxs-lookup"><span data-stu-id="4fc76-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4fc76-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4fc76-107">Return Value</span></span>  
  
|<span data-ttu-id="4fc76-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4fc76-108">HRESULT</span></span>|<span data-ttu-id="4fc76-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="4fc76-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4fc76-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4fc76-110">S_OK</span></span>|<span data-ttu-id="4fc76-111">`SetUILocale`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="4fc76-111">`SetUILocale` returned successfully.</span></span>|  
|<span data-ttu-id="4fc76-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4fc76-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4fc76-113">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="4fc76-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4fc76-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4fc76-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4fc76-115">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="4fc76-115">The call timed out.</span></span>|  
|<span data-ttu-id="4fc76-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4fc76-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4fc76-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="4fc76-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4fc76-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4fc76-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4fc76-119">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="4fc76-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4fc76-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4fc76-120">E_FAIL</span></span>|<span data-ttu-id="4fc76-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="4fc76-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4fc76-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="4fc76-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4fc76-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4fc76-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="4fc76-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="4fc76-124">E_NOTIMPL</span></span>|<span data-ttu-id="4fc76-125">El host no permite al código de usuario administrado cambiar la referencia cultural de interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="4fc76-125">The host does not allow managed user code to change the UI culture.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4fc76-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4fc76-126">Remarks</span></span>  
 <span data-ttu-id="4fc76-127">El runtime llama `SetUILocale` cuando el valor de la <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> propiedad se modifica mediante código administrado.</span><span class="sxs-lookup"><span data-stu-id="4fc76-127">The runtime calls `SetUILocale` when the value of the <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> property is changed by managed code.</span></span> <span data-ttu-id="4fc76-128">Este método proporciona una oportunidad para que el host ejecutar los mecanismos que sean necesarios para la sincronización de configuraciones regionales.</span><span class="sxs-lookup"><span data-stu-id="4fc76-128">This method provides an opportunity for the host to execute any mechanisms it might have for synchronization of locales.</span></span> <span data-ttu-id="4fc76-129">Si un host no admite la configuración regional de interfaz de usuario se cambió de código administrado o no implementa un mecanismo para sincronizar las configuraciones regionales, debe devolver E_NOTIMPL desde este método.</span><span class="sxs-lookup"><span data-stu-id="4fc76-129">If a host does not allow the UI locale to be changed from managed code, or does not implement a mechanism to synchronize locales, it should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4fc76-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4fc76-130">Requirements</span></span>  
 <span data-ttu-id="4fc76-131">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4fc76-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4fc76-132">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4fc76-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4fc76-133">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4fc76-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4fc76-134">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4fc76-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fc76-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="4fc76-135">See Also</span></span>  
 [<span data-ttu-id="4fc76-136">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4fc76-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="4fc76-137">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4fc76-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="4fc76-138">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4fc76-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="4fc76-139">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4fc76-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="4fc76-140">SetLocale (método)</span><span class="sxs-lookup"><span data-stu-id="4fc76-140">SetLocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setlocale-method.md)
