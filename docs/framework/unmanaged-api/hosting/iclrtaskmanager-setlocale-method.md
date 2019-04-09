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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ae097320ad7cd6e7c840122bf3f315812e9b2acd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199211"
---
# <a name="iclrtaskmanagersetlocale-method"></a><span data-ttu-id="85ee4-102">ICLRTaskManager::SetLocale (Método)</span><span class="sxs-lookup"><span data-stu-id="85ee4-102">ICLRTaskManager::SetLocale Method</span></span>
<span data-ttu-id="85ee4-103">Notifica a common language runtime (CLR) que el host ha modificado el valor de identificador de configuración regional (que se asigna a la referencia cultural geográfica y el idioma) en la tarea está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="85ee4-103">Notifies the common language runtime (CLR) that the host has modified the value of the locale identifier (which maps to the geographical culture and language) on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85ee4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="85ee4-104">Syntax</span></span>  
  
```  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85ee4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="85ee4-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="85ee4-106">[in] El valor de identificador de configuración regional que se asigna a la cultura geográfica recién asignado y el idioma.</span><span class="sxs-lookup"><span data-stu-id="85ee4-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="85ee4-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="85ee4-107">Return Value</span></span>  
  
|<span data-ttu-id="85ee4-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="85ee4-108">HRESULT</span></span>|<span data-ttu-id="85ee4-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="85ee4-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="85ee4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="85ee4-110">S_OK</span></span>|<span data-ttu-id="85ee4-111">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="85ee4-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="85ee4-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="85ee4-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="85ee4-113">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="85ee4-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="85ee4-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="85ee4-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="85ee4-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="85ee4-115">The call timed out.</span></span>|  
|<span data-ttu-id="85ee4-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="85ee4-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="85ee4-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="85ee4-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="85ee4-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="85ee4-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="85ee4-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="85ee4-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="85ee4-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="85ee4-120">E_FAIL</span></span>|<span data-ttu-id="85ee4-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="85ee4-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="85ee4-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="85ee4-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="85ee4-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="85ee4-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85ee4-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="85ee4-124">Remarks</span></span>  
 `SetLocale` <span data-ttu-id="85ee4-125">proporciona al host una oportunidad de ejecutarse los mecanismos que sean necesarios para la sincronización de configuraciones regionales.</span><span class="sxs-lookup"><span data-stu-id="85ee4-125">gives the host an opportunity to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85ee4-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="85ee4-126">Requirements</span></span>  
 <span data-ttu-id="85ee4-127">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85ee4-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85ee4-128">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="85ee4-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="85ee4-129">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="85ee4-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="85ee4-130">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="85ee4-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="85ee4-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="85ee4-131">See also</span></span>

- [<span data-ttu-id="85ee4-132">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="85ee4-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="85ee4-133">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="85ee4-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="85ee4-134">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="85ee4-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="85ee4-135">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="85ee4-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
