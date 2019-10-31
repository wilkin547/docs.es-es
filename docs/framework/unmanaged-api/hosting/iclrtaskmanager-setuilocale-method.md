---
title: ICLRTaskManager::SetUILocale (Método)
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.SetUILocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::SetUILocale
helpviewer_keywords:
- ICLRTaskManager::SetUILocale method [.NET Framework hosting]
- SetUILocale method, ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: 03adaa9a-2beb-49b3-b2c4-6b4fc3f10715
topic_type:
- apiref
ms.openlocfilehash: 051bd5cb846eb4e6e3390e17b3011a1c5b50bc45
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127876"
---
# <a name="iclrtaskmanagersetuilocale-method"></a><span data-ttu-id="12d2b-102">ICLRTaskManager::SetUILocale (Método)</span><span class="sxs-lookup"><span data-stu-id="12d2b-102">ICLRTaskManager::SetUILocale Method</span></span>
<span data-ttu-id="12d2b-103">Notifica a la Common Language Runtime (CLR) que el host ha modificado la configuración regional de la interfaz de usuario (UI), o la referencia cultural, en la tarea que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="12d2b-103">Notifies the common language runtime (CLR) that the host has modified the user interface (UI) locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12d2b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="12d2b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12d2b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="12d2b-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="12d2b-106">de Valor del identificador de configuración regional que se asigna a la referencia cultural geográfica recién asignada y al idioma de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="12d2b-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language for the user interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="12d2b-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="12d2b-107">Return Value</span></span>  
  
|<span data-ttu-id="12d2b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="12d2b-108">HRESULT</span></span>|<span data-ttu-id="12d2b-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="12d2b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="12d2b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="12d2b-110">S_OK</span></span>|<span data-ttu-id="12d2b-111">`SetUILocale` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="12d2b-111">`SetUILocale` returned successfully.</span></span>|  
|<span data-ttu-id="12d2b-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="12d2b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="12d2b-113">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="12d2b-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="12d2b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="12d2b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="12d2b-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="12d2b-115">The call timed out.</span></span>|  
|<span data-ttu-id="12d2b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="12d2b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="12d2b-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="12d2b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="12d2b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="12d2b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="12d2b-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="12d2b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="12d2b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="12d2b-120">E_FAIL</span></span>|<span data-ttu-id="12d2b-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="12d2b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="12d2b-122">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="12d2b-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="12d2b-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="12d2b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12d2b-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="12d2b-124">Remarks</span></span>  
 <span data-ttu-id="12d2b-125">`SetUILocale` proporciona una oportunidad para que el host ejecute cualquier mecanismo que pueda tener para la sincronización de configuraciones regionales.</span><span class="sxs-lookup"><span data-stu-id="12d2b-125">`SetUILocale` provides an opportunity for the host to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12d2b-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="12d2b-126">Requirements</span></span>  
 <span data-ttu-id="12d2b-127">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12d2b-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12d2b-128">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="12d2b-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="12d2b-129">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="12d2b-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="12d2b-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12d2b-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12d2b-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="12d2b-131">See also</span></span>

- [<span data-ttu-id="12d2b-132">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="12d2b-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="12d2b-133">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="12d2b-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="12d2b-134">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="12d2b-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="12d2b-135">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="12d2b-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
