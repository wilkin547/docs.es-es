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
ms.openlocfilehash: bd1a1d7d2f7f945f345e8af802b881392d6d93e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724226"
---
# <a name="ihosttaskmanagersetuilocale-method"></a><span data-ttu-id="94d4c-102">IHostTaskManager::SetUILocale (Método)</span><span class="sxs-lookup"><span data-stu-id="94d4c-102">IHostTaskManager::SetUILocale Method</span></span>

<span data-ttu-id="94d4c-103">Notifica al host que el Common Language Runtime (CLR) ha cambiado la configuración regional de la interfaz de usuario (UI), o la referencia cultural, en la tarea que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="94d4c-103">Notifies the host that the common language runtime (CLR) has changed the user interface (UI) locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94d4c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="94d4c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94d4c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="94d4c-105">Parameters</span></span>  

 `lcid`  
 <span data-ttu-id="94d4c-106">de Valor del identificador de configuración regional que se asigna a la referencia cultural geográfica y al idioma recién asignados.</span><span class="sxs-lookup"><span data-stu-id="94d4c-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="94d4c-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="94d4c-107">Return Value</span></span>  
  
|<span data-ttu-id="94d4c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="94d4c-108">HRESULT</span></span>|<span data-ttu-id="94d4c-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="94d4c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="94d4c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="94d4c-110">S_OK</span></span>|<span data-ttu-id="94d4c-111">`SetUILocale` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="94d4c-111">`SetUILocale` returned successfully.</span></span>|  
|<span data-ttu-id="94d4c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="94d4c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="94d4c-113">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="94d4c-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="94d4c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="94d4c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="94d4c-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="94d4c-115">The call timed out.</span></span>|  
|<span data-ttu-id="94d4c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="94d4c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="94d4c-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="94d4c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="94d4c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="94d4c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="94d4c-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="94d4c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="94d4c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="94d4c-120">E_FAIL</span></span>|<span data-ttu-id="94d4c-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="94d4c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="94d4c-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="94d4c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="94d4c-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="94d4c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="94d4c-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="94d4c-124">E_NOTIMPL</span></span>|<span data-ttu-id="94d4c-125">El host no permite que el código de usuario administrado cambie la referencia cultural de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="94d4c-125">The host does not allow managed user code to change the UI culture.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94d4c-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="94d4c-126">Remarks</span></span>  

 <span data-ttu-id="94d4c-127">El Runtime llama a `SetUILocale` cuando el valor de la <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> propiedad se cambia mediante código administrado.</span><span class="sxs-lookup"><span data-stu-id="94d4c-127">The runtime calls `SetUILocale` when the value of the <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> property is changed by managed code.</span></span> <span data-ttu-id="94d4c-128">Este método proporciona una oportunidad para que el host ejecute cualquier mecanismo que pueda tener para la sincronización de configuraciones regionales.</span><span class="sxs-lookup"><span data-stu-id="94d4c-128">This method provides an opportunity for the host to execute any mechanisms it might have for synchronization of locales.</span></span> <span data-ttu-id="94d4c-129">Si un host no permite cambiar la configuración regional de la interfaz de usuario desde código administrado o no implementa un mecanismo para sincronizar configuraciones regionales, debe devolver E_NOTIMPL desde este método.</span><span class="sxs-lookup"><span data-stu-id="94d4c-129">If a host does not allow the UI locale to be changed from managed code, or does not implement a mechanism to synchronize locales, it should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94d4c-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="94d4c-130">Requirements</span></span>  

 <span data-ttu-id="94d4c-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94d4c-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94d4c-132">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="94d4c-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="94d4c-133">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="94d4c-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="94d4c-134">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94d4c-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94d4c-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="94d4c-135">See also</span></span>

- [<span data-ttu-id="94d4c-136">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="94d4c-136">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="94d4c-137">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="94d4c-137">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="94d4c-138">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="94d4c-138">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="94d4c-139">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="94d4c-139">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="94d4c-140">Método SetLocale</span><span class="sxs-lookup"><span data-stu-id="94d4c-140">SetLocale Method</span></span>](ihosttaskmanager-setlocale-method.md)
