---
description: 'Más información acerca de: ICLRTaskManager:: Setuilocale ((método)'
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
ms.openlocfilehash: f4fcc916c520489bd1e39f6a44bc1bb971df4bba
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799465"
---
# <a name="iclrtaskmanagersetuilocale-method"></a><span data-ttu-id="00c48-103">ICLRTaskManager::SetUILocale (Método)</span><span class="sxs-lookup"><span data-stu-id="00c48-103">ICLRTaskManager::SetUILocale Method</span></span>

<span data-ttu-id="00c48-104">Notifica a la Common Language Runtime (CLR) que el host ha modificado la configuración regional de la interfaz de usuario (UI), o la referencia cultural, en la tarea que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="00c48-104">Notifies the common language runtime (CLR) that the host has modified the user interface (UI) locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00c48-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="00c48-105">Syntax</span></span>  
  
```cpp  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00c48-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="00c48-106">Parameters</span></span>  

 `lcid`  
 <span data-ttu-id="00c48-107">de Valor del identificador de configuración regional que se asigna a la referencia cultural geográfica recién asignada y al idioma de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="00c48-107">[in] The locale identifier value that maps to the newly assigned geographical culture and language for the user interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="00c48-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="00c48-108">Return Value</span></span>  
  
|<span data-ttu-id="00c48-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="00c48-109">HRESULT</span></span>|<span data-ttu-id="00c48-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="00c48-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="00c48-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="00c48-111">S_OK</span></span>|<span data-ttu-id="00c48-112">`SetUILocale` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="00c48-112">`SetUILocale` returned successfully.</span></span>|  
|<span data-ttu-id="00c48-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="00c48-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="00c48-114">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="00c48-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="00c48-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="00c48-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="00c48-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="00c48-116">The call timed out.</span></span>|  
|<span data-ttu-id="00c48-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="00c48-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="00c48-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="00c48-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="00c48-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="00c48-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="00c48-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="00c48-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="00c48-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="00c48-121">E_FAIL</span></span>|<span data-ttu-id="00c48-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="00c48-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="00c48-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="00c48-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="00c48-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="00c48-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00c48-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="00c48-125">Remarks</span></span>  

 <span data-ttu-id="00c48-126">`SetUILocale` proporciona una oportunidad para que el host ejecute cualquier mecanismo que pueda tener para la sincronización de configuraciones regionales.</span><span class="sxs-lookup"><span data-stu-id="00c48-126">`SetUILocale` provides an opportunity for the host to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00c48-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="00c48-127">Requirements</span></span>  

 <span data-ttu-id="00c48-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00c48-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00c48-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="00c48-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="00c48-130">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="00c48-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="00c48-131">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00c48-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00c48-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="00c48-132">See also</span></span>

- [<span data-ttu-id="00c48-133">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="00c48-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="00c48-134">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="00c48-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="00c48-135">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="00c48-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="00c48-136">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="00c48-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
