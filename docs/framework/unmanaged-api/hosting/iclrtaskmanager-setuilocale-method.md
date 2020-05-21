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
ms.openlocfilehash: e6ab7c7af1cf9f30f6708c4e970db619ca071343
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762786"
---
# <a name="iclrtaskmanagersetuilocale-method"></a><span data-ttu-id="30845-102">ICLRTaskManager::SetUILocale (Método)</span><span class="sxs-lookup"><span data-stu-id="30845-102">ICLRTaskManager::SetUILocale Method</span></span>
<span data-ttu-id="30845-103">Notifica a la Common Language Runtime (CLR) que el host ha modificado la configuración regional de la interfaz de usuario (UI), o la referencia cultural, en la tarea que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="30845-103">Notifies the common language runtime (CLR) that the host has modified the user interface (UI) locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30845-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="30845-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30845-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="30845-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="30845-106">de Valor del identificador de configuración regional que se asigna a la referencia cultural geográfica recién asignada y al idioma de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="30845-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language for the user interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="30845-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="30845-107">Return Value</span></span>  
  
|<span data-ttu-id="30845-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="30845-108">HRESULT</span></span>|<span data-ttu-id="30845-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="30845-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="30845-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="30845-110">S_OK</span></span>|<span data-ttu-id="30845-111">`SetUILocale`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="30845-111">`SetUILocale` returned successfully.</span></span>|  
|<span data-ttu-id="30845-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="30845-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="30845-113">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="30845-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="30845-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="30845-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="30845-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="30845-115">The call timed out.</span></span>|  
|<span data-ttu-id="30845-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="30845-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="30845-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="30845-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="30845-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="30845-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="30845-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="30845-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="30845-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="30845-120">E_FAIL</span></span>|<span data-ttu-id="30845-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="30845-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="30845-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="30845-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="30845-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="30845-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30845-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="30845-124">Remarks</span></span>  
 <span data-ttu-id="30845-125">`SetUILocale`proporciona una oportunidad para que el host ejecute cualquier mecanismo que pueda tener para la sincronización de configuraciones regionales.</span><span class="sxs-lookup"><span data-stu-id="30845-125">`SetUILocale` provides an opportunity for the host to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30845-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="30845-126">Requirements</span></span>  
 <span data-ttu-id="30845-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30845-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30845-128">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="30845-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="30845-129">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="30845-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="30845-130">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30845-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30845-131">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="30845-131">See also</span></span>

- [<span data-ttu-id="30845-132">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="30845-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="30845-133">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="30845-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="30845-134">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="30845-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="30845-135">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="30845-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
