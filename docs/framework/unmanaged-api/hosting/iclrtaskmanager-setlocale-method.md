---
title: "ICLRTaskManager::SetLocale (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTaskManager.SetLocale
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTaskManager::SetLocale
helpviewer_keywords:
- SetLocale method, ICLRTaskManager interface [.NET Framework hosting]
- ICLRTaskManager::SetLocale method [.NET Framework hosting]
ms.assetid: ed16bb7f-4206-43a8-b9e9-c5737b69e3af
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bbed6bff52d7ccad38eb45d12a31d08dc8b1b774
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtaskmanagersetlocale-method"></a><span data-ttu-id="dc981-102">ICLRTaskManager::SetLocale (Método)</span><span class="sxs-lookup"><span data-stu-id="dc981-102">ICLRTaskManager::SetLocale Method</span></span>
<span data-ttu-id="dc981-103">Notifica a common language runtime (CLR) que el host ha modificado el valor de identificador de configuración regional (que se asigna a la referencia cultural geográfica y el idioma) en la tarea que se ejecuta actualmente.</span><span class="sxs-lookup"><span data-stu-id="dc981-103">Notifies the common language runtime (CLR) that the host has modified the value of the locale identifier (which maps to the geographical culture and language) on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc981-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dc981-104">Syntax</span></span>  
  
```  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dc981-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dc981-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="dc981-106">[in] El valor de identificador de configuración regional que se asigna a un idioma y la referencia cultural geográfica recién asignada.</span><span class="sxs-lookup"><span data-stu-id="dc981-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dc981-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="dc981-107">Return Value</span></span>  
  
|<span data-ttu-id="dc981-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dc981-108">HRESULT</span></span>|<span data-ttu-id="dc981-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="dc981-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dc981-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="dc981-110">S_OK</span></span>|<span data-ttu-id="dc981-111">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="dc981-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="dc981-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dc981-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dc981-113">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="dc981-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dc981-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dc981-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dc981-115">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="dc981-115">The call timed out.</span></span>|  
|<span data-ttu-id="dc981-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dc981-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dc981-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="dc981-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dc981-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dc981-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dc981-119">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="dc981-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dc981-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dc981-120">E_FAIL</span></span>|<span data-ttu-id="dc981-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="dc981-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dc981-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="dc981-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dc981-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="dc981-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc981-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dc981-124">Remarks</span></span>  
 <span data-ttu-id="dc981-125">`SetLocale`proporciona al host una oportunidad de ejecutarse los mecanismos que sean necesarios para la sincronización de configuraciones regionales.</span><span class="sxs-lookup"><span data-stu-id="dc981-125">`SetLocale` gives the host an opportunity to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc981-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dc981-126">Requirements</span></span>  
 <span data-ttu-id="dc981-127">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc981-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc981-128">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dc981-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dc981-129">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dc981-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dc981-130">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc981-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc981-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc981-131">See Also</span></span>  
 [<span data-ttu-id="dc981-132">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dc981-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="dc981-133">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dc981-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="dc981-134">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dc981-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="dc981-135">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dc981-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
