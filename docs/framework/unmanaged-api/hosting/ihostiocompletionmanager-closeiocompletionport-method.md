---
description: 'Más información sobre: IHostIoCompletionManager:: CloseIoCompletionPort ((método)'
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
ms.openlocfilehash: 987b9f4e0fa22fa977fa1b14c77c8c0381e3e399
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728514"
---
# <a name="ihostiocompletionmanagercloseiocompletionport-method"></a><span data-ttu-id="99ad0-103">IHostIoCompletionManager::CloseIoCompletionPort (Método)</span><span class="sxs-lookup"><span data-stu-id="99ad0-103">IHostIoCompletionManager::CloseIoCompletionPort Method</span></span>

<span data-ttu-id="99ad0-104">Solicita que el host cierre un puerto que se abrió a través de una llamada anterior a [CreateIoCompletionPort](ihostiocompletionmanager-createiocompletionport-method.md).</span><span class="sxs-lookup"><span data-stu-id="99ad0-104">Requests that the host close a port that was opened through an earlier call to [CreateIoCompletionPort](ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99ad0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="99ad0-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseIoCompletionPort (  
    [in] HANDLE hPort  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99ad0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="99ad0-106">Parameters</span></span>  

 `hPort`  
 <span data-ttu-id="99ad0-107">de Identificador del puerto que se va a cerrar.</span><span class="sxs-lookup"><span data-stu-id="99ad0-107">[in] The handle of the port to close.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="99ad0-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="99ad0-108">Return Value</span></span>  
  
|<span data-ttu-id="99ad0-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="99ad0-109">HRESULT</span></span>|<span data-ttu-id="99ad0-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="99ad0-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="99ad0-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="99ad0-111">S_OK</span></span>|<span data-ttu-id="99ad0-112">`CloseIoCompletionPort` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="99ad0-112">`CloseIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="99ad0-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="99ad0-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="99ad0-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="99ad0-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="99ad0-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="99ad0-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="99ad0-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="99ad0-116">The call timed out.</span></span>|  
|<span data-ttu-id="99ad0-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="99ad0-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="99ad0-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="99ad0-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="99ad0-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="99ad0-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="99ad0-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="99ad0-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="99ad0-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="99ad0-121">E_FAIL</span></span>|<span data-ttu-id="99ad0-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="99ad0-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="99ad0-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="99ad0-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="99ad0-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="99ad0-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="99ad0-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="99ad0-125">E_INVALIDARG</span></span>|<span data-ttu-id="99ad0-126">Se pasó un identificador de puerto no válido.</span><span class="sxs-lookup"><span data-stu-id="99ad0-126">An invalid port handle was passed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99ad0-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="99ad0-127">Remarks</span></span>  

 <span data-ttu-id="99ad0-128">`hPort` debe ser un identificador de un puerto creado por una llamada anterior a `CreateIoCompletionPort` .</span><span class="sxs-lookup"><span data-stu-id="99ad0-128">`hPort` must be a handle to a port that was created by an earlier call to `CreateIoCompletionPort`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99ad0-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="99ad0-129">Requirements</span></span>  

 <span data-ttu-id="99ad0-130">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99ad0-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99ad0-131">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="99ad0-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="99ad0-132">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="99ad0-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="99ad0-133">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99ad0-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99ad0-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="99ad0-134">See also</span></span>

- [<span data-ttu-id="99ad0-135">ICLRIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="99ad0-135">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="99ad0-136">IHostIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="99ad0-136">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
