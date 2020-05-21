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
ms.openlocfilehash: 8f316d91aab4c3862a0ad45b41539a4b80791ab9
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762797"
---
# <a name="iclrtaskmanagersetlocale-method"></a><span data-ttu-id="21f5d-102">ICLRTaskManager::SetLocale (Método)</span><span class="sxs-lookup"><span data-stu-id="21f5d-102">ICLRTaskManager::SetLocale Method</span></span>
<span data-ttu-id="21f5d-103">Notifica a la Common Language Runtime (CLR) que el host ha modificado el valor del identificador de configuración regional (que se asigna a la referencia cultural geográfica y al idioma) de la tarea que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="21f5d-103">Notifies the common language runtime (CLR) that the host has modified the value of the locale identifier (which maps to the geographical culture and language) on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21f5d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="21f5d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21f5d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="21f5d-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="21f5d-106">de Valor del identificador de configuración regional que se asigna a la referencia cultural geográfica y al idioma recién asignados.</span><span class="sxs-lookup"><span data-stu-id="21f5d-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="21f5d-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="21f5d-107">Return Value</span></span>  
  
|<span data-ttu-id="21f5d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="21f5d-108">HRESULT</span></span>|<span data-ttu-id="21f5d-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="21f5d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="21f5d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="21f5d-110">S_OK</span></span>|<span data-ttu-id="21f5d-111">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="21f5d-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="21f5d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="21f5d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="21f5d-113">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="21f5d-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="21f5d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="21f5d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="21f5d-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="21f5d-115">The call timed out.</span></span>|  
|<span data-ttu-id="21f5d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="21f5d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="21f5d-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="21f5d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="21f5d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="21f5d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="21f5d-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="21f5d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="21f5d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="21f5d-120">E_FAIL</span></span>|<span data-ttu-id="21f5d-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="21f5d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="21f5d-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="21f5d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="21f5d-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="21f5d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21f5d-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="21f5d-124">Remarks</span></span>  
 <span data-ttu-id="21f5d-125">`SetLocale`proporciona al host una oportunidad para ejecutar cualquier mecanismo que pueda tener para la sincronización de configuraciones regionales.</span><span class="sxs-lookup"><span data-stu-id="21f5d-125">`SetLocale` gives the host an opportunity to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21f5d-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="21f5d-126">Requirements</span></span>  
 <span data-ttu-id="21f5d-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21f5d-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21f5d-128">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="21f5d-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="21f5d-129">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="21f5d-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="21f5d-130">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21f5d-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21f5d-131">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="21f5d-131">See also</span></span>

- [<span data-ttu-id="21f5d-132">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="21f5d-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="21f5d-133">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="21f5d-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="21f5d-134">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="21f5d-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="21f5d-135">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="21f5d-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
