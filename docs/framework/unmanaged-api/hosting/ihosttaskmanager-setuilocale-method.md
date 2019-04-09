---
title: IHostTaskManager::SetUILocale (Método)
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SetUILocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SetUILocale
helpviewer_keywords:
- SetUILocale method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::SetUILocale method [.NET Framework hosting]
ms.assetid: d0c87a9c-ea81-4237-a16b-c22b36ec9dc8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e110f1f5ea326c232c7c96bb05913080e950083d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59158904"
---
# <a name="ihosttaskmanagersetuilocale-method"></a><span data-ttu-id="e7bda-102">IHostTaskManager::SetUILocale (Método)</span><span class="sxs-lookup"><span data-stu-id="e7bda-102">IHostTaskManager::SetUILocale Method</span></span>
<span data-ttu-id="e7bda-103">Notifica al host que common language runtime (CLR) ha cambiado la configuración regional del usuario (UI) de la interfaz, o la referencia cultural en la tarea está ejecuta actualmente.</span><span class="sxs-lookup"><span data-stu-id="e7bda-103">Notifies the host that the common language runtime (CLR) has changed the user interface (UI) locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7bda-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e7bda-104">Syntax</span></span>  
  
```  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7bda-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e7bda-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="e7bda-106">[in] El valor de identificador de configuración regional que se asigna a la cultura geográfica recién asignado y el idioma.</span><span class="sxs-lookup"><span data-stu-id="e7bda-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e7bda-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e7bda-107">Return Value</span></span>  
  
|<span data-ttu-id="e7bda-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e7bda-108">HRESULT</span></span>|<span data-ttu-id="e7bda-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7bda-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e7bda-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e7bda-110">S_OK</span></span>|`SetUILocale` <span data-ttu-id="e7bda-111">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="e7bda-111">returned successfully.</span></span>|  
|<span data-ttu-id="e7bda-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e7bda-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e7bda-113">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="e7bda-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e7bda-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e7bda-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e7bda-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="e7bda-115">The call timed out.</span></span>|  
|<span data-ttu-id="e7bda-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e7bda-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e7bda-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="e7bda-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e7bda-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e7bda-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e7bda-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="e7bda-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e7bda-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e7bda-120">E_FAIL</span></span>|<span data-ttu-id="e7bda-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="e7bda-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e7bda-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="e7bda-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e7bda-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e7bda-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e7bda-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="e7bda-124">E_NOTIMPL</span></span>|<span data-ttu-id="e7bda-125">El host no admite el código de usuario administrado para cambiar la referencia cultural de interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="e7bda-125">The host does not allow managed user code to change the UI culture.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7bda-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e7bda-126">Remarks</span></span>  
 <span data-ttu-id="e7bda-127">El runtime llama a `SetUILocale` cuando el valor de la <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> propiedad se modifica mediante código administrado.</span><span class="sxs-lookup"><span data-stu-id="e7bda-127">The runtime calls `SetUILocale` when the value of the <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> property is changed by managed code.</span></span> <span data-ttu-id="e7bda-128">Este método proporciona una oportunidad para que el host ejecutar los mecanismos que sean necesarios para la sincronización de configuraciones regionales.</span><span class="sxs-lookup"><span data-stu-id="e7bda-128">This method provides an opportunity for the host to execute any mechanisms it might have for synchronization of locales.</span></span> <span data-ttu-id="e7bda-129">Si un host no admite la configuración regional de interfaz de usuario se puede cambiar desde el código administrado o no implementa un mecanismo para sincronizar las configuraciones regionales, debe devolver E_NOTIMPL desde este método.</span><span class="sxs-lookup"><span data-stu-id="e7bda-129">If a host does not allow the UI locale to be changed from managed code, or does not implement a mechanism to synchronize locales, it should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7bda-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e7bda-130">Requirements</span></span>  
 <span data-ttu-id="e7bda-131">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7bda-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7bda-132">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e7bda-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e7bda-133">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e7bda-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="e7bda-134">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e7bda-134">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e7bda-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7bda-135">See also</span></span>

- [<span data-ttu-id="e7bda-136">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e7bda-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="e7bda-137">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e7bda-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="e7bda-138">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e7bda-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="e7bda-139">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e7bda-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="e7bda-140">Método SetLocale</span><span class="sxs-lookup"><span data-stu-id="e7bda-140">SetLocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setlocale-method.md)
