---
title: IHostTaskManager::EnterRuntime (Método)
ms.date: 03/30/2017
api_name:
- IHostTaskManager.EnterRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::EnterRuntime
helpviewer_keywords:
- IHostTaskManager::EnterRuntime method [.NET Framework hosting]
- EnterRuntime method [.NET Framework hosting]
ms.assetid: 1aa7a4b1-636a-4f5e-b834-b406d72f7120
topic_type:
- apiref
ms.openlocfilehash: a3af57859c5284ff45681ffc2b5aa3ea3cf8fad6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133058"
---
# <a name="ihosttaskmanagerenterruntime-method"></a><span data-ttu-id="40ff0-102">IHostTaskManager::EnterRuntime (Método)</span><span class="sxs-lookup"><span data-stu-id="40ff0-102">IHostTaskManager::EnterRuntime Method</span></span>
<span data-ttu-id="40ff0-103">Notifica al host que una llamada a un método no administrado, como un método de invocación de plataforma, devuelve el control de ejecución al Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="40ff0-103">Notifies the host that a call to an unmanaged method, such as a platform invoke method, is returning execution control to the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40ff0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="40ff0-104">Syntax</span></span>  
  
```cpp  
HRESULT EnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="40ff0-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="40ff0-105">Return Value</span></span>  
  
|<span data-ttu-id="40ff0-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="40ff0-106">HRESULT</span></span>|<span data-ttu-id="40ff0-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="40ff0-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="40ff0-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="40ff0-108">S_OK</span></span>|<span data-ttu-id="40ff0-109">`EnterRuntime` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="40ff0-109">`EnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="40ff0-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="40ff0-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="40ff0-111">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="40ff0-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="40ff0-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="40ff0-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="40ff0-113">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="40ff0-113">The call timed out.</span></span>|  
|<span data-ttu-id="40ff0-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="40ff0-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="40ff0-115">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="40ff0-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="40ff0-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="40ff0-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="40ff0-117">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="40ff0-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="40ff0-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="40ff0-118">E_FAIL</span></span>|<span data-ttu-id="40ff0-119">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="40ff0-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="40ff0-120">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="40ff0-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="40ff0-121">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="40ff0-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="40ff0-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="40ff0-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="40ff0-123">No había suficiente memoria disponible para completar la asignación solicitada.</span><span class="sxs-lookup"><span data-stu-id="40ff0-123">Not enough memory was available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40ff0-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="40ff0-124">Remarks</span></span>  
 <span data-ttu-id="40ff0-125">`EnterRuntime` se llama para notificar al host que una función no administrada, para la que se realizó una llamada anterior al método [LeaveRuntime (](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md) , ha terminado de ejecutarse y devuelve el control de ejecución al tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="40ff0-125">`EnterRuntime` is called to notify the host that an unmanaged function, for which an earlier call to the [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md) method was made, has finished executing, and is returning execution control to the runtime.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="40ff0-126">Se llama a [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md) para notificar al host que una función no administrada, para la que se realizó una llamada anterior a `LeaveRuntime`, está realizando una llamada a código administrado.</span><span class="sxs-lookup"><span data-stu-id="40ff0-126">[ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md) is called to notify the host that an unmanaged function, for which an earlier call to `LeaveRuntime` was made, is making a call into managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40ff0-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="40ff0-127">Requirements</span></span>  
 <span data-ttu-id="40ff0-128">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40ff0-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40ff0-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="40ff0-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="40ff0-130">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="40ff0-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="40ff0-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40ff0-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40ff0-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="40ff0-132">See also</span></span>

- [<span data-ttu-id="40ff0-133">Interoperabilidad COM avanzada</span><span class="sxs-lookup"><span data-stu-id="40ff0-133">Advanced COM Interoperability</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx)
- [<span data-ttu-id="40ff0-134">Cómo: Llamar a archivos DLL nativos desde el código administrado mediante PInvoke</span><span class="sxs-lookup"><span data-stu-id="40ff0-134">How to: Call Native DLLs from Managed Code Using PInvoke</span></span>](/cpp/dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke)
- [<span data-ttu-id="40ff0-135">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="40ff0-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="40ff0-136">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="40ff0-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="40ff0-137">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="40ff0-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="40ff0-138">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="40ff0-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="40ff0-139">LeaveRuntime (método)</span><span class="sxs-lookup"><span data-stu-id="40ff0-139">LeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)
