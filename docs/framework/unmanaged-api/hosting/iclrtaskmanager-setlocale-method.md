---
title: ICLRTaskManager::SetLocale (Método)
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.SetLocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::SetLocale
helpviewer_keywords:
- SetLocale method, ICLRTaskManager interface [.NET Framework hosting]
- ICLRTaskManager::SetLocale method [.NET Framework hosting]
ms.assetid: ed16bb7f-4206-43a8-b9e9-c5737b69e3af
topic_type:
- apiref
ms.openlocfilehash: 79f24b3ccacd84037042a883d3a034bb7b4d200a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092087"
---
# <a name="iclrtaskmanagersetlocale-method"></a><span data-ttu-id="78200-102">ICLRTaskManager::SetLocale (Método)</span><span class="sxs-lookup"><span data-stu-id="78200-102">ICLRTaskManager::SetLocale Method</span></span>
<span data-ttu-id="78200-103">Notifica a la Common Language Runtime (CLR) que el host ha modificado el valor del identificador de configuración regional (que se asigna a la referencia cultural geográfica y al idioma) de la tarea que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="78200-103">Notifies the common language runtime (CLR) that the host has modified the value of the locale identifier (which maps to the geographical culture and language) on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78200-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="78200-104">Syntax</span></span>  
  
```cpp  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78200-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="78200-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="78200-106">de Valor del identificador de configuración regional que se asigna a la referencia cultural geográfica y al idioma recién asignados.</span><span class="sxs-lookup"><span data-stu-id="78200-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="78200-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="78200-107">Return Value</span></span>  
  
|<span data-ttu-id="78200-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="78200-108">HRESULT</span></span>|<span data-ttu-id="78200-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="78200-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="78200-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="78200-110">S_OK</span></span>|<span data-ttu-id="78200-111">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="78200-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="78200-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="78200-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="78200-113">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="78200-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="78200-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="78200-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="78200-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="78200-115">The call timed out.</span></span>|  
|<span data-ttu-id="78200-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="78200-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="78200-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="78200-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="78200-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="78200-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="78200-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="78200-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="78200-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="78200-120">E_FAIL</span></span>|<span data-ttu-id="78200-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="78200-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="78200-122">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="78200-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="78200-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="78200-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78200-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="78200-124">Remarks</span></span>  
 <span data-ttu-id="78200-125">`SetLocale` proporciona al host una oportunidad para ejecutar cualquier mecanismo que pueda tener para la sincronización de configuraciones regionales.</span><span class="sxs-lookup"><span data-stu-id="78200-125">`SetLocale` gives the host an opportunity to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78200-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="78200-126">Requirements</span></span>  
 <span data-ttu-id="78200-127">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78200-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78200-128">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="78200-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="78200-129">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="78200-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="78200-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78200-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78200-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="78200-131">See also</span></span>

- [<span data-ttu-id="78200-132">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="78200-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="78200-133">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="78200-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="78200-134">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="78200-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="78200-135">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="78200-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
