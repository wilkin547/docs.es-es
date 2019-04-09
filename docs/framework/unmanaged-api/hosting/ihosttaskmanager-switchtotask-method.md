---
title: IHostTaskManager::SwitchToTask (Método)
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SwitchToTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SwitchToTask
helpviewer_keywords:
- IHostTaskManager::SwitchToTask method [.NET Framework hosting]
- SwitchToTask method [.NET Framework hosting]
ms.assetid: 35d0c27e-4b14-49ce-810d-7ab2120177e8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a50c9f7fc5921d3e5c21dd3566de81ac2249f3dd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59110565"
---
# <a name="ihosttaskmanagerswitchtotask-method"></a><span data-ttu-id="9dcf2-102">IHostTaskManager::SwitchToTask (Método)</span><span class="sxs-lookup"><span data-stu-id="9dcf2-102">IHostTaskManager::SwitchToTask Method</span></span>
<span data-ttu-id="9dcf2-103">Notifica al host que debe desactivar la tarea actual.</span><span class="sxs-lookup"><span data-stu-id="9dcf2-103">Notifies the host that it should switch out the current task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dcf2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9dcf2-104">Syntax</span></span>  
  
```  
HRESULT SwitchToTask (  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9dcf2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9dcf2-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="9dcf2-106">[in] Uno de los [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) valores de enumeración, que indica la acción que debe realizar el host si bloquea la operación solicitada.</span><span class="sxs-lookup"><span data-stu-id="9dcf2-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) enumeration values, indicating the action the host should take if the requested operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9dcf2-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9dcf2-107">Return Value</span></span>  
  
|<span data-ttu-id="9dcf2-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9dcf2-108">HRESULT</span></span>|<span data-ttu-id="9dcf2-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="9dcf2-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9dcf2-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9dcf2-110">S_OK</span></span>|`SwitchToTask` <span data-ttu-id="9dcf2-111">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="9dcf2-111">returned successfully.</span></span>|  
|<span data-ttu-id="9dcf2-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9dcf2-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9dcf2-113">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="9dcf2-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9dcf2-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9dcf2-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9dcf2-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="9dcf2-115">The call timed out.</span></span>|  
|<span data-ttu-id="9dcf2-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9dcf2-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9dcf2-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="9dcf2-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9dcf2-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9dcf2-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9dcf2-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="9dcf2-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9dcf2-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9dcf2-120">E_FAIL</span></span>|<span data-ttu-id="9dcf2-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="9dcf2-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9dcf2-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="9dcf2-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9dcf2-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9dcf2-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9dcf2-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9dcf2-124">Remarks</span></span>  
 <span data-ttu-id="9dcf2-125">El host puede cambiar a otra tarea si fuera necesario.</span><span class="sxs-lookup"><span data-stu-id="9dcf2-125">The host can switch in another task as desired or needed.</span></span>  
  
> [!NOTE]
>  `SwitchToTask` <span data-ttu-id="9dcf2-126">no especifica qué tareas debe cambiar el host especifica solo la tarea que debe cambiar de.</span><span class="sxs-lookup"><span data-stu-id="9dcf2-126">does not specify which task the host should switch to; it specifies only the task that it should switch from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9dcf2-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9dcf2-127">Requirements</span></span>  
 <span data-ttu-id="9dcf2-128">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9dcf2-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9dcf2-129">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9dcf2-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9dcf2-130">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9dcf2-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="9dcf2-131">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="9dcf2-131">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9dcf2-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="9dcf2-132">See also</span></span>

- [<span data-ttu-id="9dcf2-133">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9dcf2-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="9dcf2-134">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9dcf2-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="9dcf2-135">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9dcf2-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="9dcf2-136">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9dcf2-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
