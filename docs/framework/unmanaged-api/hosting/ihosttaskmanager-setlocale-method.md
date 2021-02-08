---
description: 'Más información acerca de: IHostTaskManager:: SetLocale (método)'
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
ms.openlocfilehash: 522a3da9bcd8d61754684091f6de3f11f7ed478c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789416"
---
# <a name="ihosttaskmanagersetlocale-method"></a><span data-ttu-id="57712-103">IHostTaskManager::SetLocale (Método)</span><span class="sxs-lookup"><span data-stu-id="57712-103">IHostTaskManager::SetLocale Method</span></span>

<span data-ttu-id="57712-104">Notifica al host que el Common Language Runtime (CLR) ha cambiado la configuración regional o la referencia cultural de la tarea que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="57712-104">Notifies the host that the common language runtime (CLR) has changed the locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57712-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="57712-105">Syntax</span></span>  
  
```cpp  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="57712-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="57712-106">Parameters</span></span>  

 `lcid`  
 <span data-ttu-id="57712-107">de Valor del identificador de configuración regional que se asigna a la referencia cultural geográfica y al idioma recién asignados.</span><span class="sxs-lookup"><span data-stu-id="57712-107">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="57712-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="57712-108">Return Value</span></span>  
  
|<span data-ttu-id="57712-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="57712-109">HRESULT</span></span>|<span data-ttu-id="57712-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="57712-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="57712-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="57712-111">S_OK</span></span>|<span data-ttu-id="57712-112">`SetLocale` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="57712-112">`SetLocale` returned successfully.</span></span>|  
|<span data-ttu-id="57712-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="57712-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="57712-114">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="57712-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="57712-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="57712-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="57712-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="57712-116">The call timed out.</span></span>|  
|<span data-ttu-id="57712-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="57712-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="57712-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="57712-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="57712-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="57712-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="57712-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="57712-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="57712-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="57712-121">E_FAIL</span></span>|<span data-ttu-id="57712-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="57712-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="57712-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="57712-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="57712-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="57712-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="57712-125">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="57712-125">E_NOTIMPL</span></span>|<span data-ttu-id="57712-126">El host no permite que el código de usuario administrado modifique la configuración regional.</span><span class="sxs-lookup"><span data-stu-id="57712-126">The host does not allow managed user code to modify the locale.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="57712-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="57712-127">Remarks</span></span>  

 <span data-ttu-id="57712-128">El Runtime llama a `SetLocale` cuando el valor de la <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> propiedad se cambia mediante código administrado.</span><span class="sxs-lookup"><span data-stu-id="57712-128">The runtime calls `SetLocale` when the value of the <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> property is changed by managed code.</span></span> <span data-ttu-id="57712-129">Este método proporciona una oportunidad para que el host ejecute cualquier mecanismo que pueda tener para la sincronización de configuraciones regionales.</span><span class="sxs-lookup"><span data-stu-id="57712-129">This method provides an opportunity for the host to execute any mechanisms it might have for synchronization of locales.</span></span> <span data-ttu-id="57712-130">Si un host no permite cambiar la configuración regional del código administrado o no implementa un mecanismo para sincronizar configuraciones regionales, debe devolver E_NOTIMPL desde este método.</span><span class="sxs-lookup"><span data-stu-id="57712-130">If a host does not allow the locale to be changed from managed code, or does not implement a mechanism to synchronize locales, it should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57712-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="57712-131">Requirements</span></span>  

 <span data-ttu-id="57712-132">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57712-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57712-133">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="57712-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="57712-134">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="57712-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="57712-135">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57712-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57712-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="57712-136">See also</span></span>

- [<span data-ttu-id="57712-137">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="57712-137">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="57712-138">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="57712-138">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="57712-139">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="57712-139">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="57712-140">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="57712-140">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="57712-141">Método SetUILocale</span><span class="sxs-lookup"><span data-stu-id="57712-141">SetUILocale Method</span></span>](ihosttaskmanager-setuilocale-method.md)
