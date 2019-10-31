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
ms.openlocfilehash: a929a125fc8c70744246f4f96d8a09a4605f537c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132940"
---
# <a name="ihosttaskmanagersetuilocale-method"></a><span data-ttu-id="ae053-102">IHostTaskManager::SetUILocale (Método)</span><span class="sxs-lookup"><span data-stu-id="ae053-102">IHostTaskManager::SetUILocale Method</span></span>
<span data-ttu-id="ae053-103">Notifica al host que el Common Language Runtime (CLR) ha cambiado la configuración regional de la interfaz de usuario (UI), o la referencia cultural, en la tarea que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="ae053-103">Notifies the host that the common language runtime (CLR) has changed the user interface (UI) locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae053-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ae053-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae053-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ae053-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="ae053-106">de Valor del identificador de configuración regional que se asigna a la referencia cultural geográfica y al idioma recién asignados.</span><span class="sxs-lookup"><span data-stu-id="ae053-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ae053-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ae053-107">Return Value</span></span>  
  
|<span data-ttu-id="ae053-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ae053-108">HRESULT</span></span>|<span data-ttu-id="ae053-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="ae053-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ae053-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ae053-110">S_OK</span></span>|<span data-ttu-id="ae053-111">`SetUILocale` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="ae053-111">`SetUILocale` returned successfully.</span></span>|  
|<span data-ttu-id="ae053-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ae053-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ae053-113">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="ae053-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ae053-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ae053-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ae053-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="ae053-115">The call timed out.</span></span>|  
|<span data-ttu-id="ae053-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ae053-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ae053-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="ae053-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ae053-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ae053-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ae053-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="ae053-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ae053-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ae053-120">E_FAIL</span></span>|<span data-ttu-id="ae053-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="ae053-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ae053-122">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="ae053-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ae053-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ae053-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ae053-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="ae053-124">E_NOTIMPL</span></span>|<span data-ttu-id="ae053-125">El host no permite que el código de usuario administrado cambie la referencia cultural de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="ae053-125">The host does not allow managed user code to change the UI culture.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae053-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ae053-126">Remarks</span></span>  
 <span data-ttu-id="ae053-127">El Runtime llama a `SetUILocale` cuando el valor de la propiedad <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> cambia por código administrado.</span><span class="sxs-lookup"><span data-stu-id="ae053-127">The runtime calls `SetUILocale` when the value of the <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> property is changed by managed code.</span></span> <span data-ttu-id="ae053-128">Este método proporciona una oportunidad para que el host ejecute cualquier mecanismo que pueda tener para la sincronización de configuraciones regionales.</span><span class="sxs-lookup"><span data-stu-id="ae053-128">This method provides an opportunity for the host to execute any mechanisms it might have for synchronization of locales.</span></span> <span data-ttu-id="ae053-129">Si un host no permite cambiar la configuración regional de la interfaz de usuario del código administrado o no implementa un mecanismo para sincronizar configuraciones regionales, debe devolver E_NOTIMPL desde este método.</span><span class="sxs-lookup"><span data-stu-id="ae053-129">If a host does not allow the UI locale to be changed from managed code, or does not implement a mechanism to synchronize locales, it should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae053-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ae053-130">Requirements</span></span>  
 <span data-ttu-id="ae053-131">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae053-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae053-132">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ae053-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ae053-133">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ae053-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ae053-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae053-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae053-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae053-135">See also</span></span>

- [<span data-ttu-id="ae053-136">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ae053-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="ae053-137">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ae053-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="ae053-138">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ae053-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="ae053-139">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ae053-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="ae053-140">SetLocale (método)</span><span class="sxs-lookup"><span data-stu-id="ae053-140">SetLocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setlocale-method.md)
