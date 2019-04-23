---
title: IHostThreadPoolManager::QueueUserWorkItem (Método)
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.QueueUserWorkItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::QueueUserWorkItem
helpviewer_keywords:
- IHostThreadPoolManager::QueueUserWorkItem method [.NET Framework hosting]
- QueueUserWorkItem method [.NET Framework hosting]
ms.assetid: 41602053-8670-4827-9d61-cbfcba509b9c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1c548ae7f8d605ff84da2046d057e436c8e95721
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59082119"
---
# <a name="ihostthreadpoolmanagerqueueuserworkitem-method"></a><span data-ttu-id="7e8b0-102">IHostThreadPoolManager::QueueUserWorkItem (Método)</span><span class="sxs-lookup"><span data-stu-id="7e8b0-102">IHostThreadPoolManager::QueueUserWorkItem Method</span></span>
<span data-ttu-id="7e8b0-103">Pone en cola una función para su ejecución y especifica un objeto que contiene los datos que va a usar esa función.</span><span class="sxs-lookup"><span data-stu-id="7e8b0-103">Queues a function for execution, and specifies an object containing data to be used by that function.</span></span> <span data-ttu-id="7e8b0-104">La función se ejecuta cuando un subproceso esté disponible.</span><span class="sxs-lookup"><span data-stu-id="7e8b0-104">The function executes when a thread becomes available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e8b0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7e8b0-105">Syntax</span></span>  
  
```  
HRESULT QueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID Context,  
    [in] ULONG Flags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e8b0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7e8b0-106">Parameters</span></span>  
 `Function`  
 <span data-ttu-id="7e8b0-107">[in] Un puntero a función que representa la función para ejecutar.</span><span class="sxs-lookup"><span data-stu-id="7e8b0-107">[in] A function pointer that represents the function to execute.</span></span>  
  
 `Context`  
 <span data-ttu-id="7e8b0-108">[in] Un objeto que contiene los datos que va a usar `Function`.</span><span class="sxs-lookup"><span data-stu-id="7e8b0-108">[in] An object that contains data to be used by `Function`.</span></span>  
  
 `Flags`  
 <span data-ttu-id="7e8b0-109">[in] Uno de los indicadores de valores, como se define para Win32 `QueueUserWorkItem` método, que controlan la ejecución.</span><span class="sxs-lookup"><span data-stu-id="7e8b0-109">[in] One of the flags values, as defined for the Win32 `QueueUserWorkItem` method, that control execution.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7e8b0-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7e8b0-110">Return Value</span></span>  
  
|<span data-ttu-id="7e8b0-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7e8b0-111">HRESULT</span></span>|<span data-ttu-id="7e8b0-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="7e8b0-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7e8b0-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="7e8b0-113">S_OK</span></span>|<span data-ttu-id="7e8b0-114">`QueueUserWorkItem` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="7e8b0-114">`QueueUserWorkItem` returned successfully.</span></span>|  
|<span data-ttu-id="7e8b0-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7e8b0-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7e8b0-116">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="7e8b0-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7e8b0-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7e8b0-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7e8b0-118">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="7e8b0-118">The call timed out.</span></span>|  
|<span data-ttu-id="7e8b0-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7e8b0-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7e8b0-120">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="7e8b0-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7e8b0-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7e8b0-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7e8b0-122">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="7e8b0-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7e8b0-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7e8b0-123">E_FAIL</span></span>|<span data-ttu-id="7e8b0-124">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="7e8b0-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7e8b0-125">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="7e8b0-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7e8b0-126">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7e8b0-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e8b0-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7e8b0-127">Remarks</span></span>  
 <span data-ttu-id="7e8b0-128">`QueueUserWorkItem` pone en cola un elemento de trabajo a un subproceso de trabajo en el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="7e8b0-128">`QueueUserWorkItem` queues a work item to a worker thread in the thread pool.</span></span> <span data-ttu-id="7e8b0-129">Sus tipos de firma y los parámetros son idénticos a los de la función de Win32 correspondiente, que tiene el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="7e8b0-129">Its signature and parameter types are identical to those of the corresponding Win32 function, which has the same name.</span></span> <span data-ttu-id="7e8b0-130">Para obtener más información, consulte la documentación de la plataforma de Windows.</span><span class="sxs-lookup"><span data-stu-id="7e8b0-130">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e8b0-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7e8b0-131">Requirements</span></span>  
 <span data-ttu-id="7e8b0-132">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e8b0-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e8b0-133">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7e8b0-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7e8b0-134">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7e8b0-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7e8b0-135">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e8b0-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e8b0-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e8b0-136">See also</span></span>

- <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="7e8b0-137">IHostThreadPoolManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7e8b0-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
