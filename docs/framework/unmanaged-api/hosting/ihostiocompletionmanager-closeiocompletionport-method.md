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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 281284ca432efc86964a2e3e37fa89d1506aa350
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54698679"
---
# <a name="ihostiocompletionmanagercloseiocompletionport-method"></a><span data-ttu-id="dfe07-102">IHostIoCompletionManager::CloseIoCompletionPort (Método)</span><span class="sxs-lookup"><span data-stu-id="dfe07-102">IHostIoCompletionManager::CloseIoCompletionPort Method</span></span>
<span data-ttu-id="dfe07-103">Solicita que el host cierre un puerto que se abrió a través de una llamada anterior a [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span><span class="sxs-lookup"><span data-stu-id="dfe07-103">Requests that the host close a port that was opened through an earlier call to [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfe07-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dfe07-104">Syntax</span></span>  
  
```  
HRESULT CloseIoCompletionPort (  
    [in] HANDLE hPort  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dfe07-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dfe07-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="dfe07-106">[in] El identificador del puerto que se va a cerrar.</span><span class="sxs-lookup"><span data-stu-id="dfe07-106">[in] The handle of the port to close.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dfe07-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="dfe07-107">Return Value</span></span>  
  
|<span data-ttu-id="dfe07-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dfe07-108">HRESULT</span></span>|<span data-ttu-id="dfe07-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="dfe07-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dfe07-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="dfe07-110">S_OK</span></span>|<span data-ttu-id="dfe07-111">`CloseIoCompletionPort` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="dfe07-111">`CloseIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="dfe07-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dfe07-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dfe07-113">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="dfe07-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dfe07-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dfe07-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dfe07-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="dfe07-115">The call timed out.</span></span>|  
|<span data-ttu-id="dfe07-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dfe07-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dfe07-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="dfe07-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dfe07-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dfe07-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dfe07-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="dfe07-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dfe07-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dfe07-120">E_FAIL</span></span>|<span data-ttu-id="dfe07-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="dfe07-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dfe07-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="dfe07-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dfe07-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="dfe07-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="dfe07-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="dfe07-124">E_INVALIDARG</span></span>|<span data-ttu-id="dfe07-125">Se pasó un identificador de puerto no válido.</span><span class="sxs-lookup"><span data-stu-id="dfe07-125">An invalid port handle was passed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dfe07-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dfe07-126">Remarks</span></span>  
 <span data-ttu-id="dfe07-127">`hPort` debe ser un identificador a un puerto que se creó mediante una llamada anterior a `CreateIoCompletionPort`.</span><span class="sxs-lookup"><span data-stu-id="dfe07-127">`hPort` must be a handle to a port that was created by an earlier call to `CreateIoCompletionPort`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dfe07-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dfe07-128">Requirements</span></span>  
 <span data-ttu-id="dfe07-129">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dfe07-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfe07-130">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dfe07-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dfe07-131">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dfe07-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dfe07-132">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfe07-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfe07-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="dfe07-133">See also</span></span>
- [<span data-ttu-id="dfe07-134">ICLRIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dfe07-134">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="dfe07-135">IHostIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dfe07-135">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
