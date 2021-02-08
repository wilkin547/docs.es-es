---
description: 'Más información acerca de: IHostTaskManager:: Switchtotask ((método)'
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
ms.openlocfilehash: 6333dcdf7e1bbe6bde575f53f4743a1300c770f3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789364"
---
# <a name="ihosttaskmanagerswitchtotask-method"></a><span data-ttu-id="1d170-103">IHostTaskManager::SwitchToTask (Método)</span><span class="sxs-lookup"><span data-stu-id="1d170-103">IHostTaskManager::SwitchToTask Method</span></span>

<span data-ttu-id="1d170-104">Notifica al host que debe desactivar la tarea actual.</span><span class="sxs-lookup"><span data-stu-id="1d170-104">Notifies the host that it should switch out the current task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d170-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1d170-105">Syntax</span></span>  
  
```cpp  
HRESULT SwitchToTask (  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d170-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1d170-106">Parameters</span></span>  

 `option`  
 <span data-ttu-id="1d170-107">de Uno de los valores de enumeración de [WAIT_OPTION](wait-option-enumeration.md) , que indica la acción que debe realizar el host si se bloquea la operación solicitada.</span><span class="sxs-lookup"><span data-stu-id="1d170-107">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) enumeration values, indicating the action the host should take if the requested operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1d170-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1d170-108">Return Value</span></span>  
  
|<span data-ttu-id="1d170-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1d170-109">HRESULT</span></span>|<span data-ttu-id="1d170-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="1d170-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1d170-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="1d170-111">S_OK</span></span>|<span data-ttu-id="1d170-112">`SwitchToTask` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="1d170-112">`SwitchToTask` returned successfully.</span></span>|  
|<span data-ttu-id="1d170-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1d170-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1d170-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="1d170-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1d170-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1d170-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1d170-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="1d170-116">The call timed out.</span></span>|  
|<span data-ttu-id="1d170-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1d170-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1d170-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="1d170-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1d170-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1d170-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1d170-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="1d170-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1d170-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1d170-121">E_FAIL</span></span>|<span data-ttu-id="1d170-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="1d170-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1d170-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="1d170-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1d170-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1d170-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1d170-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1d170-125">Remarks</span></span>  

 <span data-ttu-id="1d170-126">El host puede cambiar en otra tarea según sea necesario o si es necesario.</span><span class="sxs-lookup"><span data-stu-id="1d170-126">The host can switch in another task as desired or needed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1d170-127">`SwitchToTask` no especifica a qué tarea debe cambiar el host; especifica solo la tarea de la que debe cambiar.</span><span class="sxs-lookup"><span data-stu-id="1d170-127">`SwitchToTask` does not specify which task the host should switch to; it specifies only the task that it should switch from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d170-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1d170-128">Requirements</span></span>  

 <span data-ttu-id="1d170-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d170-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d170-130">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1d170-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1d170-131">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1d170-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1d170-132">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d170-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d170-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d170-133">See also</span></span>

- [<span data-ttu-id="1d170-134">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1d170-134">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="1d170-135">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1d170-135">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="1d170-136">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1d170-136">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="1d170-137">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1d170-137">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
