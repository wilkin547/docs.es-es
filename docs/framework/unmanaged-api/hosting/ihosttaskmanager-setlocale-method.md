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
ms.openlocfilehash: f388a52c320c3f0d5f4ad7e073e1e8960d7947dc
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749365"
---
# <a name="ihosttaskmanagersetlocale-method"></a><span data-ttu-id="32964-102">IHostTaskManager::SetLocale (Método)</span><span class="sxs-lookup"><span data-stu-id="32964-102">IHostTaskManager::SetLocale Method</span></span>
<span data-ttu-id="32964-103">Notifica al host que common language runtime (CLR) ha cambiado la configuración regional o la referencia cultural en la tarea está ejecuta actualmente.</span><span class="sxs-lookup"><span data-stu-id="32964-103">Notifies the host that the common language runtime (CLR) has changed the locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32964-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="32964-104">Syntax</span></span>  
  
```cpp  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32964-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="32964-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="32964-106">[in] El valor de identificador de configuración regional que se asigna a la cultura geográfica recién asignado y el idioma.</span><span class="sxs-lookup"><span data-stu-id="32964-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="32964-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="32964-107">Return Value</span></span>  
  
|<span data-ttu-id="32964-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="32964-108">HRESULT</span></span>|<span data-ttu-id="32964-109">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="32964-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="32964-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="32964-110">S_OK</span></span>|<span data-ttu-id="32964-111">`SetLocale` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="32964-111">`SetLocale` returned successfully.</span></span>|  
|<span data-ttu-id="32964-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="32964-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="32964-113">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="32964-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="32964-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="32964-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="32964-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="32964-115">The call timed out.</span></span>|  
|<span data-ttu-id="32964-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="32964-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="32964-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="32964-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="32964-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="32964-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="32964-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="32964-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="32964-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="32964-120">E_FAIL</span></span>|<span data-ttu-id="32964-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="32964-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="32964-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="32964-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="32964-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="32964-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="32964-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="32964-124">E_NOTIMPL</span></span>|<span data-ttu-id="32964-125">El host no admite el código de usuario administrado modificar la configuración regional.</span><span class="sxs-lookup"><span data-stu-id="32964-125">The host does not allow managed user code to modify the locale.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32964-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="32964-126">Remarks</span></span>  
 <span data-ttu-id="32964-127">El runtime llama a `SetLocale` cuando el valor de la <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> propiedad se modifica mediante código administrado.</span><span class="sxs-lookup"><span data-stu-id="32964-127">The runtime calls `SetLocale` when the value of the <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> property is changed by managed code.</span></span> <span data-ttu-id="32964-128">Este método proporciona una oportunidad para que el host ejecutar los mecanismos que sean necesarios para la sincronización de configuraciones regionales.</span><span class="sxs-lookup"><span data-stu-id="32964-128">This method provides an opportunity for the host to execute any mechanisms it might have for synchronization of locales.</span></span> <span data-ttu-id="32964-129">Si un host no admite la configuración regional que se puede cambiar desde el código administrado o no implementa un mecanismo para sincronizar las configuraciones regionales, debe devolver E_NOTIMPL desde este método.</span><span class="sxs-lookup"><span data-stu-id="32964-129">If a host does not allow the locale to be changed from managed code, or does not implement a mechanism to synchronize locales, it should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32964-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="32964-130">Requirements</span></span>  
 <span data-ttu-id="32964-131">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32964-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32964-132">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="32964-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="32964-133">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="32964-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="32964-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32964-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32964-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="32964-135">See also</span></span>

- [<span data-ttu-id="32964-136">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="32964-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="32964-137">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="32964-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="32964-138">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="32964-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="32964-139">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="32964-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="32964-140">SetUILocale (método)</span><span class="sxs-lookup"><span data-stu-id="32964-140">SetUILocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setuilocale-method.md)
