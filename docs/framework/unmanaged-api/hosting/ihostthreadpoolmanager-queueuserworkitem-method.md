---
description: 'Más información acerca de: IHostThreadPoolManager:: QueueUserWorkItem (método)'
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
ms.openlocfilehash: edfbf5cfb34473a5fd920307981237fd5deab9aa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753788"
---
# <a name="ihostthreadpoolmanagerqueueuserworkitem-method"></a><span data-ttu-id="ebb58-103">IHostThreadPoolManager::QueueUserWorkItem (Método)</span><span class="sxs-lookup"><span data-stu-id="ebb58-103">IHostThreadPoolManager::QueueUserWorkItem Method</span></span>

<span data-ttu-id="ebb58-104">Pone en cola una función para su ejecución y especifica un objeto que contiene los datos que va a usar esa función.</span><span class="sxs-lookup"><span data-stu-id="ebb58-104">Queues a function for execution, and specifies an object containing data to be used by that function.</span></span> <span data-ttu-id="ebb58-105">La función se ejecuta cuando un subproceso está disponible.</span><span class="sxs-lookup"><span data-stu-id="ebb58-105">The function executes when a thread becomes available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebb58-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ebb58-106">Syntax</span></span>  
  
```cpp  
HRESULT QueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID Context,  
    [in] ULONG Flags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ebb58-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ebb58-107">Parameters</span></span>  

 `Function`  
 <span data-ttu-id="ebb58-108">de Puntero a función que representa la función que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="ebb58-108">[in] A function pointer that represents the function to execute.</span></span>  
  
 `Context`  
 <span data-ttu-id="ebb58-109">de Objeto que contiene los datos que va a usar `Function` .</span><span class="sxs-lookup"><span data-stu-id="ebb58-109">[in] An object that contains data to be used by `Function`.</span></span>  
  
 `Flags`  
 <span data-ttu-id="ebb58-110">de Uno de los valores de flags, tal y como se define para el `QueueUserWorkItem` método Win32, que controla la ejecución.</span><span class="sxs-lookup"><span data-stu-id="ebb58-110">[in] One of the flags values, as defined for the Win32 `QueueUserWorkItem` method, that control execution.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ebb58-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ebb58-111">Return Value</span></span>  
  
|<span data-ttu-id="ebb58-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ebb58-112">HRESULT</span></span>|<span data-ttu-id="ebb58-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="ebb58-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ebb58-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="ebb58-114">S_OK</span></span>|<span data-ttu-id="ebb58-115">`QueueUserWorkItem` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="ebb58-115">`QueueUserWorkItem` returned successfully.</span></span>|  
|<span data-ttu-id="ebb58-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ebb58-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ebb58-117">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="ebb58-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ebb58-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ebb58-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ebb58-119">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="ebb58-119">The call timed out.</span></span>|  
|<span data-ttu-id="ebb58-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ebb58-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ebb58-121">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="ebb58-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ebb58-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ebb58-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ebb58-123">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="ebb58-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ebb58-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ebb58-124">E_FAIL</span></span>|<span data-ttu-id="ebb58-125">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="ebb58-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ebb58-126">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="ebb58-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ebb58-127">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ebb58-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ebb58-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ebb58-128">Remarks</span></span>  

 <span data-ttu-id="ebb58-129">`QueueUserWorkItem` pone en cola un elemento de trabajo en un subproceso de trabajo en el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="ebb58-129">`QueueUserWorkItem` queues a work item to a worker thread in the thread pool.</span></span> <span data-ttu-id="ebb58-130">Su firma y sus tipos de parámetros son idénticos a los de la función de Win32 correspondiente, que tiene el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="ebb58-130">Its signature and parameter types are identical to those of the corresponding Win32 function, which has the same name.</span></span> <span data-ttu-id="ebb58-131">Para obtener más información, vea la documentación de la plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="ebb58-131">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebb58-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ebb58-132">Requirements</span></span>  

 <span data-ttu-id="ebb58-133">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ebb58-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebb58-134">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ebb58-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ebb58-135">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ebb58-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ebb58-136">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebb58-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebb58-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="ebb58-137">See also</span></span>

- <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="ebb58-138">IHostThreadPoolManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ebb58-138">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
