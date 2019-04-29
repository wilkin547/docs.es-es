---
title: IHostIoCompletionManager::SetCLRIoCompletionManager (Método)
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.SetCLRIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetCLRIoCompletionManager
helpviewer_keywords:
- IHostIoCompletionManager::SetCLRIoCompletionManager method [.NET Framework hosting]
- SetCLRIoCompletionManager method [.NET Framework hosting]
ms.assetid: 4254bb01-3a14-4f34-a3be-60ff1f5072b5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cd48664c78e3f5772cdfa655ebbc7cfa716f4950
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796849"
---
# <a name="ihostiocompletionmanagersetclriocompletionmanager-method"></a><span data-ttu-id="a858c-102">IHostIoCompletionManager::SetCLRIoCompletionManager (Método)</span><span class="sxs-lookup"><span data-stu-id="a858c-102">IHostIoCompletionManager::SetCLRIoCompletionManager Method</span></span>
<span data-ttu-id="a858c-103">Proporciona el host con un puntero de interfaz a la [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) instancia implementada por common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="a858c-103">Provides the host with an interface pointer to the [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a858c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a858c-104">Syntax</span></span>  
  
```  
HRESULT SetCLRIoCompletionManager (  
    [in] ICLRIoCompletionManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a858c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a858c-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="a858c-106">[in] Un puntero de interfaz a un `ICLRIoCompletionManager` instancia proporcionada por CLR.</span><span class="sxs-lookup"><span data-stu-id="a858c-106">[in] An interface pointer to an `ICLRIoCompletionManager` instance provided by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a858c-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a858c-107">Return Value</span></span>  
  
|<span data-ttu-id="a858c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a858c-108">HRESULT</span></span>|<span data-ttu-id="a858c-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="a858c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a858c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a858c-110">S_OK</span></span>|<span data-ttu-id="a858c-111">`SetCLRIoCompletionManager` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="a858c-111">`SetCLRIoCompletionManager` returned successfully.</span></span>|  
|<span data-ttu-id="a858c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a858c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a858c-113">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="a858c-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a858c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a858c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a858c-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="a858c-115">The call timed out.</span></span>|  
|<span data-ttu-id="a858c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a858c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a858c-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="a858c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a858c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a858c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a858c-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="a858c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a858c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a858c-120">E_FAIL</span></span>|<span data-ttu-id="a858c-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="a858c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a858c-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="a858c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a858c-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a858c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a858c-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a858c-124">Remarks</span></span>  
 <span data-ttu-id="a858c-125">Después de haber llamado CLR `SetCLRIoCompletionManager`, el host debe llamar a [ICLRIoCompletionManager:: OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) para notificar al CLR cuando se ha completado una solicitud de E/S.</span><span class="sxs-lookup"><span data-stu-id="a858c-125">After the CLR has called `SetCLRIoCompletionManager`, the host must call [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) to notify the CLR when an I/O request has been completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a858c-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a858c-126">Requirements</span></span>  
 <span data-ttu-id="a858c-127">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a858c-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a858c-128">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a858c-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a858c-129">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a858c-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a858c-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a858c-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a858c-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="a858c-131">See also</span></span>

- [<span data-ttu-id="a858c-132">ICLRIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a858c-132">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="a858c-133">IHostIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a858c-133">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
