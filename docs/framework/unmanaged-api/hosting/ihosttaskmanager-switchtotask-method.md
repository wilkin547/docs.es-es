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
ms.openlocfilehash: a55b43f3629cebb0ba1d3a7ac1802126874418d8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122114"
---
# <a name="ihosttaskmanagerswitchtotask-method"></a><span data-ttu-id="f5a89-102">IHostTaskManager::SwitchToTask (Método)</span><span class="sxs-lookup"><span data-stu-id="f5a89-102">IHostTaskManager::SwitchToTask Method</span></span>
<span data-ttu-id="f5a89-103">Notifica al host que debe desactivar la tarea actual.</span><span class="sxs-lookup"><span data-stu-id="f5a89-103">Notifies the host that it should switch out the current task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5a89-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f5a89-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchToTask (  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5a89-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f5a89-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="f5a89-106">de Uno de los valores de enumeración de [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) , que indica la acción que debe realizar el host si se bloquea la operación solicitada.</span><span class="sxs-lookup"><span data-stu-id="f5a89-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) enumeration values, indicating the action the host should take if the requested operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f5a89-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f5a89-107">Return Value</span></span>  
  
|<span data-ttu-id="f5a89-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f5a89-108">HRESULT</span></span>|<span data-ttu-id="f5a89-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="f5a89-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f5a89-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f5a89-110">S_OK</span></span>|<span data-ttu-id="f5a89-111">`SwitchToTask` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="f5a89-111">`SwitchToTask` returned successfully.</span></span>|  
|<span data-ttu-id="f5a89-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f5a89-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f5a89-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="f5a89-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f5a89-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f5a89-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f5a89-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f5a89-115">The call timed out.</span></span>|  
|<span data-ttu-id="f5a89-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f5a89-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f5a89-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="f5a89-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f5a89-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f5a89-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f5a89-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="f5a89-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f5a89-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f5a89-120">E_FAIL</span></span>|<span data-ttu-id="f5a89-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="f5a89-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f5a89-122">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="f5a89-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f5a89-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f5a89-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5a89-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f5a89-124">Remarks</span></span>  
 <span data-ttu-id="f5a89-125">El host puede cambiar en otra tarea según sea necesario o si es necesario.</span><span class="sxs-lookup"><span data-stu-id="f5a89-125">The host can switch in another task as desired or needed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f5a89-126">`SwitchToTask` no especifica a qué tarea debe cambiar el host; especifica solo la tarea de la que debe cambiar.</span><span class="sxs-lookup"><span data-stu-id="f5a89-126">`SwitchToTask` does not specify which task the host should switch to; it specifies only the task that it should switch from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5a89-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f5a89-127">Requirements</span></span>  
 <span data-ttu-id="f5a89-128">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5a89-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5a89-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f5a89-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f5a89-130">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f5a89-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f5a89-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5a89-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5a89-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5a89-132">See also</span></span>

- [<span data-ttu-id="f5a89-133">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f5a89-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="f5a89-134">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f5a89-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="f5a89-135">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f5a89-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="f5a89-136">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f5a89-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
