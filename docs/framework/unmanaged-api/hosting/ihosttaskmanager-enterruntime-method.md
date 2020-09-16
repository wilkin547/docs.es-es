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
ms.openlocfilehash: 1591a055200618f3e4951b5f6cf860dd3e71b44b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554363"
---
# <a name="ihosttaskmanagerenterruntime-method"></a><span data-ttu-id="b2587-102">IHostTaskManager::EnterRuntime (Método)</span><span class="sxs-lookup"><span data-stu-id="b2587-102">IHostTaskManager::EnterRuntime Method</span></span>
<span data-ttu-id="b2587-103">Notifica al host que una llamada a un método no administrado, como un método de invocación de plataforma, devuelve el control de ejecución al Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="b2587-103">Notifies the host that a call to an unmanaged method, such as a platform invoke method, is returning execution control to the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2587-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b2587-104">Syntax</span></span>  
  
```cpp  
HRESULT EnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="b2587-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b2587-105">Return Value</span></span>  
  
|<span data-ttu-id="b2587-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b2587-106">HRESULT</span></span>|<span data-ttu-id="b2587-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b2587-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b2587-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="b2587-108">S_OK</span></span>|<span data-ttu-id="b2587-109">`EnterRuntime` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="b2587-109">`EnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="b2587-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b2587-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b2587-111">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="b2587-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b2587-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b2587-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b2587-113">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b2587-113">The call timed out.</span></span>|  
|<span data-ttu-id="b2587-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b2587-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b2587-115">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="b2587-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b2587-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b2587-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b2587-117">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="b2587-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b2587-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b2587-118">E_FAIL</span></span>|<span data-ttu-id="b2587-119">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="b2587-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b2587-120">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="b2587-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b2587-121">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b2587-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b2587-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="b2587-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="b2587-123">No había suficiente memoria disponible para completar la asignación solicitada.</span><span class="sxs-lookup"><span data-stu-id="b2587-123">Not enough memory was available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2587-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b2587-124">Remarks</span></span>  
 <span data-ttu-id="b2587-125">`EnterRuntime` se llama a para notificar al host que una función no administrada, para la que se realizó una llamada anterior al método [LeaveRuntime (](ihosttaskmanager-leaveruntime-method.md) , ha terminado de ejecutarse y devuelve el control de ejecución al tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b2587-125">`EnterRuntime` is called to notify the host that an unmanaged function, for which an earlier call to the [LeaveRuntime](ihosttaskmanager-leaveruntime-method.md) method was made, has finished executing, and is returning execution control to the runtime.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b2587-126">Se llama a [ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md) para notificar al host que una función no administrada, para la que se realizó una llamada anterior a `LeaveRuntime` , está realizando una llamada a código administrado.</span><span class="sxs-lookup"><span data-stu-id="b2587-126">[ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md) is called to notify the host that an unmanaged function, for which an earlier call to `LeaveRuntime` was made, is making a call into managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2587-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b2587-127">Requirements</span></span>  
 <span data-ttu-id="b2587-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2587-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2587-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b2587-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b2587-130">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b2587-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b2587-131">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2587-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2587-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2587-132">See also</span></span>

- <span data-ttu-id="b2587-133">[Interoperabilidad COM avanzada](/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b2587-133">[Advanced COM Interoperability](/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span></span>
- [<span data-ttu-id="b2587-134">Cómo: llamar a archivos DLL nativos desde el código administrado mediante PInvoke</span><span class="sxs-lookup"><span data-stu-id="b2587-134">How to: Call Native DLLs from Managed Code Using PInvoke</span></span>](/cpp/dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke)
- [<span data-ttu-id="b2587-135">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b2587-135">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="b2587-136">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b2587-136">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="b2587-137">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b2587-137">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="b2587-138">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b2587-138">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="b2587-139">Método LeaveRuntime</span><span class="sxs-lookup"><span data-stu-id="b2587-139">LeaveRuntime Method</span></span>](ihosttaskmanager-leaveruntime-method.md)
