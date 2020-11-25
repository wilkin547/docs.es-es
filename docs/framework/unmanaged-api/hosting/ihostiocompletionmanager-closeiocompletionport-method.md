---
title: IHostIoCompletionManager::CloseIoCompletionPort (Método)
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.CloseIoCompletionPort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::CloseIoCompletionPort
helpviewer_keywords:
- IHostIoCompletionManager::CloseIoCompletionPort method [.NET Framework hosting]
- CloseIoCompletionPort method [.NET Framework hosting]
ms.assetid: e86ad7be-3758-498a-a972-5522d69dfbb3
topic_type:
- apiref
ms.openlocfilehash: a45f8ab6372776bece09e408bc9887bfaddb0955
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727372"
---
# <a name="ihostiocompletionmanagercloseiocompletionport-method"></a><span data-ttu-id="0a43f-102">IHostIoCompletionManager::CloseIoCompletionPort (Método)</span><span class="sxs-lookup"><span data-stu-id="0a43f-102">IHostIoCompletionManager::CloseIoCompletionPort Method</span></span>

<span data-ttu-id="0a43f-103">Solicita que el host cierre un puerto que se abrió a través de una llamada anterior a [CreateIoCompletionPort](ihostiocompletionmanager-createiocompletionport-method.md).</span><span class="sxs-lookup"><span data-stu-id="0a43f-103">Requests that the host close a port that was opened through an earlier call to [CreateIoCompletionPort](ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a43f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0a43f-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseIoCompletionPort (  
    [in] HANDLE hPort  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a43f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0a43f-105">Parameters</span></span>  

 `hPort`  
 <span data-ttu-id="0a43f-106">de Identificador del puerto que se va a cerrar.</span><span class="sxs-lookup"><span data-stu-id="0a43f-106">[in] The handle of the port to close.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0a43f-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0a43f-107">Return Value</span></span>  
  
|<span data-ttu-id="0a43f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0a43f-108">HRESULT</span></span>|<span data-ttu-id="0a43f-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="0a43f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0a43f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0a43f-110">S_OK</span></span>|<span data-ttu-id="0a43f-111">`CloseIoCompletionPort` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="0a43f-111">`CloseIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="0a43f-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0a43f-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0a43f-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="0a43f-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0a43f-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0a43f-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0a43f-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0a43f-115">The call timed out.</span></span>|  
|<span data-ttu-id="0a43f-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0a43f-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0a43f-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="0a43f-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0a43f-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0a43f-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0a43f-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="0a43f-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0a43f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0a43f-120">E_FAIL</span></span>|<span data-ttu-id="0a43f-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="0a43f-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0a43f-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="0a43f-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0a43f-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0a43f-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0a43f-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="0a43f-124">E_INVALIDARG</span></span>|<span data-ttu-id="0a43f-125">Se pasó un identificador de puerto no válido.</span><span class="sxs-lookup"><span data-stu-id="0a43f-125">An invalid port handle was passed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0a43f-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0a43f-126">Remarks</span></span>  

 <span data-ttu-id="0a43f-127">`hPort` debe ser un identificador de un puerto creado por una llamada anterior a `CreateIoCompletionPort` .</span><span class="sxs-lookup"><span data-stu-id="0a43f-127">`hPort` must be a handle to a port that was created by an earlier call to `CreateIoCompletionPort`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a43f-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0a43f-128">Requirements</span></span>  

 <span data-ttu-id="0a43f-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a43f-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a43f-130">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0a43f-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0a43f-131">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0a43f-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0a43f-132">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a43f-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a43f-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0a43f-133">See also</span></span>

- [<span data-ttu-id="0a43f-134">ICLRIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0a43f-134">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="0a43f-135">IHostIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0a43f-135">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
