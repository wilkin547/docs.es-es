---
title: IHostTaskManager::SetLocale (Método)
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SetLocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SetLocale
helpviewer_keywords:
- SetLocale method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::SetLocale method [.NET Framework hosting]
ms.assetid: 747ee407-ee8c-484d-9583-25089236d2d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4b43de32807da2478af23e52997fce2f4da1b339
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54674695"
---
# <a name="ihosttaskmanagersetlocale-method"></a><span data-ttu-id="9b230-102">IHostTaskManager::SetLocale (Método)</span><span class="sxs-lookup"><span data-stu-id="9b230-102">IHostTaskManager::SetLocale Method</span></span>
<span data-ttu-id="9b230-103">Notifica al host que common language runtime (CLR) ha cambiado la configuración regional o la referencia cultural en la tarea está ejecuta actualmente.</span><span class="sxs-lookup"><span data-stu-id="9b230-103">Notifies the host that the common language runtime (CLR) has changed the locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b230-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9b230-104">Syntax</span></span>  
  
```  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9b230-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9b230-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="9b230-106">[in] El valor de identificador de configuración regional que se asigna a la cultura geográfica recién asignado y el idioma.</span><span class="sxs-lookup"><span data-stu-id="9b230-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9b230-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9b230-107">Return Value</span></span>  
  
|<span data-ttu-id="9b230-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9b230-108">HRESULT</span></span>|<span data-ttu-id="9b230-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="9b230-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9b230-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9b230-110">S_OK</span></span>|<span data-ttu-id="9b230-111">`SetLocale` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="9b230-111">`SetLocale` returned successfully.</span></span>|  
|<span data-ttu-id="9b230-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9b230-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9b230-113">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="9b230-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9b230-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9b230-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9b230-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="9b230-115">The call timed out.</span></span>|  
|<span data-ttu-id="9b230-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9b230-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9b230-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="9b230-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9b230-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9b230-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9b230-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="9b230-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9b230-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9b230-120">E_FAIL</span></span>|<span data-ttu-id="9b230-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="9b230-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9b230-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="9b230-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9b230-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9b230-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9b230-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="9b230-124">E_NOTIMPL</span></span>|<span data-ttu-id="9b230-125">El host no admite el código de usuario administrado modificar la configuración regional.</span><span class="sxs-lookup"><span data-stu-id="9b230-125">The host does not allow managed user code to modify the locale.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b230-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9b230-126">Remarks</span></span>  
 <span data-ttu-id="9b230-127">El runtime llama a `SetLocale` cuando el valor de la <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> propiedad se modifica mediante código administrado.</span><span class="sxs-lookup"><span data-stu-id="9b230-127">The runtime calls `SetLocale` when the value of the <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> property is changed by managed code.</span></span> <span data-ttu-id="9b230-128">Este método proporciona una oportunidad para que el host ejecutar los mecanismos que sean necesarios para la sincronización de configuraciones regionales.</span><span class="sxs-lookup"><span data-stu-id="9b230-128">This method provides an opportunity for the host to execute any mechanisms it might have for synchronization of locales.</span></span> <span data-ttu-id="9b230-129">Si un host no admite la configuración regional que se puede cambiar desde el código administrado o no implementa un mecanismo para sincronizar las configuraciones regionales, debe devolver E_NOTIMPL desde este método.</span><span class="sxs-lookup"><span data-stu-id="9b230-129">If a host does not allow the locale to be changed from managed code, or does not implement a mechanism to synchronize locales, it should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b230-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9b230-130">Requirements</span></span>  
 <span data-ttu-id="9b230-131">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b230-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b230-132">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9b230-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9b230-133">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9b230-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9b230-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b230-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b230-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="9b230-135">See also</span></span>
- [<span data-ttu-id="9b230-136">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9b230-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="9b230-137">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9b230-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="9b230-138">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9b230-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="9b230-139">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9b230-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="9b230-140">SetUILocale (método)</span><span class="sxs-lookup"><span data-stu-id="9b230-140">SetUILocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setuilocale-method.md)
