---
title: ICLRTaskManager::SetUILocale (Método)
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.SetUILocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::SetUILocale
helpviewer_keywords:
- ICLRTaskManager::SetUILocale method [.NET Framework hosting]
- SetUILocale method, ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: 03adaa9a-2beb-49b3-b2c4-6b4fc3f10715
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03c5c9d04567832951062fe1512a292f9b32a94b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59155682"
---
# <a name="iclrtaskmanagersetuilocale-method"></a><span data-ttu-id="32d87-102">ICLRTaskManager::SetUILocale (Método)</span><span class="sxs-lookup"><span data-stu-id="32d87-102">ICLRTaskManager::SetUILocale Method</span></span>
<span data-ttu-id="32d87-103">Notifica a common language runtime (CLR) que el host ha modificado la configuración regional del usuario (UI) de la interfaz, o la referencia cultural en la tarea está ejecuta actualmente.</span><span class="sxs-lookup"><span data-stu-id="32d87-103">Notifies the common language runtime (CLR) that the host has modified the user interface (UI) locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32d87-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="32d87-104">Syntax</span></span>  
  
```  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32d87-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="32d87-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="32d87-106">[in] El valor de identificador de configuración regional que se asigna a la cultura geográfica recién asignado y el idioma de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="32d87-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language for the user interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="32d87-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="32d87-107">Return Value</span></span>  
  
|<span data-ttu-id="32d87-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="32d87-108">HRESULT</span></span>|<span data-ttu-id="32d87-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="32d87-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="32d87-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="32d87-110">S_OK</span></span>|<span data-ttu-id="32d87-111">`SetUILocale` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="32d87-111">`SetUILocale` returned successfully.</span></span>|  
|<span data-ttu-id="32d87-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="32d87-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="32d87-113">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="32d87-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="32d87-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="32d87-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="32d87-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="32d87-115">The call timed out.</span></span>|  
|<span data-ttu-id="32d87-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="32d87-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="32d87-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="32d87-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="32d87-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="32d87-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="32d87-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="32d87-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="32d87-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="32d87-120">E_FAIL</span></span>|<span data-ttu-id="32d87-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="32d87-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="32d87-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="32d87-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="32d87-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="32d87-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32d87-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="32d87-124">Remarks</span></span>  
 <span data-ttu-id="32d87-125">`SetUILocale` Proporciona una oportunidad para que el host ejecutar los mecanismos que sean necesarios para la sincronización de configuraciones regionales.</span><span class="sxs-lookup"><span data-stu-id="32d87-125">`SetUILocale` provides an opportunity for the host to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32d87-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="32d87-126">Requirements</span></span>  
 <span data-ttu-id="32d87-127">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32d87-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32d87-128">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="32d87-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="32d87-129">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="32d87-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="32d87-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32d87-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32d87-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="32d87-131">See also</span></span>

- [<span data-ttu-id="32d87-132">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="32d87-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="32d87-133">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="32d87-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="32d87-134">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="32d87-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="32d87-135">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="32d87-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
