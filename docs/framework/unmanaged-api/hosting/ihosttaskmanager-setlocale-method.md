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
ms.openlocfilehash: 7730c2dddaca98e4cb06cdb381e8a46ff23c97f9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699214"
---
# <a name="ihosttaskmanagersetlocale-method"></a><span data-ttu-id="733c1-102">IHostTaskManager::SetLocale (Método)</span><span class="sxs-lookup"><span data-stu-id="733c1-102">IHostTaskManager::SetLocale Method</span></span>

<span data-ttu-id="733c1-103">Notifica al host que el Common Language Runtime (CLR) ha cambiado la configuración regional o la referencia cultural de la tarea que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="733c1-103">Notifies the host that the common language runtime (CLR) has changed the locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="733c1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="733c1-104">Syntax</span></span>  
  
```cpp  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="733c1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="733c1-105">Parameters</span></span>  

 `lcid`  
 <span data-ttu-id="733c1-106">de Valor del identificador de configuración regional que se asigna a la referencia cultural geográfica y al idioma recién asignados.</span><span class="sxs-lookup"><span data-stu-id="733c1-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="733c1-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="733c1-107">Return Value</span></span>  
  
|<span data-ttu-id="733c1-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="733c1-108">HRESULT</span></span>|<span data-ttu-id="733c1-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="733c1-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="733c1-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="733c1-110">S_OK</span></span>|<span data-ttu-id="733c1-111">`SetLocale` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="733c1-111">`SetLocale` returned successfully.</span></span>|  
|<span data-ttu-id="733c1-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="733c1-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="733c1-113">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="733c1-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="733c1-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="733c1-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="733c1-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="733c1-115">The call timed out.</span></span>|  
|<span data-ttu-id="733c1-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="733c1-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="733c1-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="733c1-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="733c1-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="733c1-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="733c1-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="733c1-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="733c1-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="733c1-120">E_FAIL</span></span>|<span data-ttu-id="733c1-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="733c1-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="733c1-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="733c1-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="733c1-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="733c1-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="733c1-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="733c1-124">E_NOTIMPL</span></span>|<span data-ttu-id="733c1-125">El host no permite que el código de usuario administrado modifique la configuración regional.</span><span class="sxs-lookup"><span data-stu-id="733c1-125">The host does not allow managed user code to modify the locale.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="733c1-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="733c1-126">Remarks</span></span>  

 <span data-ttu-id="733c1-127">El Runtime llama a `SetLocale` cuando el valor de la <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> propiedad se cambia mediante código administrado.</span><span class="sxs-lookup"><span data-stu-id="733c1-127">The runtime calls `SetLocale` when the value of the <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> property is changed by managed code.</span></span> <span data-ttu-id="733c1-128">Este método proporciona una oportunidad para que el host ejecute cualquier mecanismo que pueda tener para la sincronización de configuraciones regionales.</span><span class="sxs-lookup"><span data-stu-id="733c1-128">This method provides an opportunity for the host to execute any mechanisms it might have for synchronization of locales.</span></span> <span data-ttu-id="733c1-129">Si un host no permite cambiar la configuración regional del código administrado o no implementa un mecanismo para sincronizar configuraciones regionales, debe devolver E_NOTIMPL desde este método.</span><span class="sxs-lookup"><span data-stu-id="733c1-129">If a host does not allow the locale to be changed from managed code, or does not implement a mechanism to synchronize locales, it should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="733c1-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="733c1-130">Requirements</span></span>  

 <span data-ttu-id="733c1-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="733c1-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="733c1-132">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="733c1-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="733c1-133">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="733c1-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="733c1-134">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="733c1-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="733c1-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="733c1-135">See also</span></span>

- [<span data-ttu-id="733c1-136">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="733c1-136">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="733c1-137">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="733c1-137">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="733c1-138">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="733c1-138">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="733c1-139">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="733c1-139">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="733c1-140">Método SetUILocale</span><span class="sxs-lookup"><span data-stu-id="733c1-140">SetUILocale Method</span></span>](ihosttaskmanager-setuilocale-method.md)
