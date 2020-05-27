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
ms.openlocfilehash: b3d77e30cd48310c392d38dc29f62fab565c8b42
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842470"
---
# <a name="ihostthreadpoolmanagerqueueuserworkitem-method"></a><span data-ttu-id="a8703-102">IHostThreadPoolManager::QueueUserWorkItem (Método)</span><span class="sxs-lookup"><span data-stu-id="a8703-102">IHostThreadPoolManager::QueueUserWorkItem Method</span></span>
<span data-ttu-id="a8703-103">Pone en cola una función para su ejecución y especifica un objeto que contiene los datos que va a usar esa función.</span><span class="sxs-lookup"><span data-stu-id="a8703-103">Queues a function for execution, and specifies an object containing data to be used by that function.</span></span> <span data-ttu-id="a8703-104">La función se ejecuta cuando un subproceso está disponible.</span><span class="sxs-lookup"><span data-stu-id="a8703-104">The function executes when a thread becomes available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8703-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a8703-105">Syntax</span></span>  
  
```cpp  
HRESULT QueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID Context,  
    [in] ULONG Flags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8703-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a8703-106">Parameters</span></span>  
 `Function`  
 <span data-ttu-id="a8703-107">de Puntero a función que representa la función que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="a8703-107">[in] A function pointer that represents the function to execute.</span></span>  
  
 `Context`  
 <span data-ttu-id="a8703-108">de Objeto que contiene los datos que va a usar `Function` .</span><span class="sxs-lookup"><span data-stu-id="a8703-108">[in] An object that contains data to be used by `Function`.</span></span>  
  
 `Flags`  
 <span data-ttu-id="a8703-109">de Uno de los valores de flags, tal y como se define para el `QueueUserWorkItem` método Win32, que controla la ejecución.</span><span class="sxs-lookup"><span data-stu-id="a8703-109">[in] One of the flags values, as defined for the Win32 `QueueUserWorkItem` method, that control execution.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a8703-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a8703-110">Return Value</span></span>  
  
|<span data-ttu-id="a8703-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a8703-111">HRESULT</span></span>|<span data-ttu-id="a8703-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8703-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a8703-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="a8703-113">S_OK</span></span>|<span data-ttu-id="a8703-114">`QueueUserWorkItem`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="a8703-114">`QueueUserWorkItem` returned successfully.</span></span>|  
|<span data-ttu-id="a8703-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a8703-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a8703-116">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="a8703-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a8703-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a8703-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a8703-118">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a8703-118">The call timed out.</span></span>|  
|<span data-ttu-id="a8703-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a8703-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a8703-120">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="a8703-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a8703-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a8703-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a8703-122">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="a8703-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a8703-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a8703-123">E_FAIL</span></span>|<span data-ttu-id="a8703-124">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="a8703-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a8703-125">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="a8703-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a8703-126">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a8703-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8703-127">Notas</span><span class="sxs-lookup"><span data-stu-id="a8703-127">Remarks</span></span>  
 <span data-ttu-id="a8703-128">`QueueUserWorkItem`pone en cola un elemento de trabajo en un subproceso de trabajo en el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="a8703-128">`QueueUserWorkItem` queues a work item to a worker thread in the thread pool.</span></span> <span data-ttu-id="a8703-129">Su firma y sus tipos de parámetros son idénticos a los de la función de Win32 correspondiente, que tiene el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="a8703-129">Its signature and parameter types are identical to those of the corresponding Win32 function, which has the same name.</span></span> <span data-ttu-id="a8703-130">Para obtener más información, vea la documentación de la plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="a8703-130">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8703-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a8703-131">Requirements</span></span>  
 <span data-ttu-id="a8703-132">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8703-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8703-133">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a8703-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a8703-134">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a8703-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a8703-135">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8703-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8703-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8703-136">See also</span></span>

- <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="a8703-137">IHostThreadPoolManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a8703-137">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
