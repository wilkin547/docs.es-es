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
ms.openlocfilehash: 5f799c140705a5279c996b6bec90ab1f29bd42ef
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732442"
---
# <a name="iclrtaskmanagersetlocale-method"></a><span data-ttu-id="40320-102">ICLRTaskManager::SetLocale (Método)</span><span class="sxs-lookup"><span data-stu-id="40320-102">ICLRTaskManager::SetLocale Method</span></span>

<span data-ttu-id="40320-103">Notifica a la Common Language Runtime (CLR) que el host ha modificado el valor del identificador de configuración regional (que se asigna a la referencia cultural geográfica y al idioma) de la tarea que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="40320-103">Notifies the common language runtime (CLR) that the host has modified the value of the locale identifier (which maps to the geographical culture and language) on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40320-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="40320-104">Syntax</span></span>  
  
```cpp  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40320-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="40320-105">Parameters</span></span>  

 `lcid`  
 <span data-ttu-id="40320-106">de Valor del identificador de configuración regional que se asigna a la referencia cultural geográfica y al idioma recién asignados.</span><span class="sxs-lookup"><span data-stu-id="40320-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="40320-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="40320-107">Return Value</span></span>  
  
|<span data-ttu-id="40320-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="40320-108">HRESULT</span></span>|<span data-ttu-id="40320-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="40320-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="40320-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="40320-110">S_OK</span></span>|<span data-ttu-id="40320-111">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="40320-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="40320-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="40320-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="40320-113">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="40320-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="40320-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="40320-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="40320-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="40320-115">The call timed out.</span></span>|  
|<span data-ttu-id="40320-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="40320-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="40320-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="40320-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="40320-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="40320-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="40320-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="40320-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="40320-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="40320-120">E_FAIL</span></span>|<span data-ttu-id="40320-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="40320-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="40320-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="40320-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="40320-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="40320-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40320-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="40320-124">Remarks</span></span>  

 <span data-ttu-id="40320-125">`SetLocale` proporciona al host una oportunidad para ejecutar cualquier mecanismo que pueda tener para la sincronización de configuraciones regionales.</span><span class="sxs-lookup"><span data-stu-id="40320-125">`SetLocale` gives the host an opportunity to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40320-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="40320-126">Requirements</span></span>  

 <span data-ttu-id="40320-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40320-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40320-128">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="40320-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="40320-129">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="40320-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="40320-130">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40320-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40320-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="40320-131">See also</span></span>

- [<span data-ttu-id="40320-132">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="40320-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="40320-133">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="40320-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="40320-134">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="40320-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="40320-135">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="40320-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
