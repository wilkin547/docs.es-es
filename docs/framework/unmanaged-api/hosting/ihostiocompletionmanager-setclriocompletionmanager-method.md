---
description: 'Más información sobre: IHostIoCompletionManager:: SetCLRIoCompletionManager ((método)'
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
ms.openlocfilehash: 1075c33d6de4f5edf34364d67cbc0a21c4f19802
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708299"
---
# <a name="ihostiocompletionmanagersetclriocompletionmanager-method"></a><span data-ttu-id="1bdf9-103">IHostIoCompletionManager::SetCLRIoCompletionManager (Método)</span><span class="sxs-lookup"><span data-stu-id="1bdf9-103">IHostIoCompletionManager::SetCLRIoCompletionManager Method</span></span>

<span data-ttu-id="1bdf9-104">Proporciona al host un puntero de interfaz a la instancia de [ICLRIoCompletionManager](iclriocompletionmanager-interface.md) implementada por el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="1bdf9-104">Provides the host with an interface pointer to the [ICLRIoCompletionManager](iclriocompletionmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bdf9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1bdf9-105">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRIoCompletionManager (  
    [in] ICLRIoCompletionManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1bdf9-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1bdf9-106">Parameters</span></span>  

 `pManager`  
 <span data-ttu-id="1bdf9-107">de Puntero de interfaz a una `ICLRIoCompletionManager` instancia de proporcionada por el CLR.</span><span class="sxs-lookup"><span data-stu-id="1bdf9-107">[in] An interface pointer to an `ICLRIoCompletionManager` instance provided by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1bdf9-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1bdf9-108">Return Value</span></span>  
  
|<span data-ttu-id="1bdf9-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1bdf9-109">HRESULT</span></span>|<span data-ttu-id="1bdf9-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="1bdf9-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1bdf9-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="1bdf9-111">S_OK</span></span>|<span data-ttu-id="1bdf9-112">`SetCLRIoCompletionManager` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="1bdf9-112">`SetCLRIoCompletionManager` returned successfully.</span></span>|  
|<span data-ttu-id="1bdf9-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1bdf9-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1bdf9-114">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="1bdf9-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1bdf9-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1bdf9-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1bdf9-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="1bdf9-116">The call timed out.</span></span>|  
|<span data-ttu-id="1bdf9-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1bdf9-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1bdf9-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="1bdf9-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1bdf9-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1bdf9-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1bdf9-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="1bdf9-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1bdf9-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1bdf9-121">E_FAIL</span></span>|<span data-ttu-id="1bdf9-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="1bdf9-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1bdf9-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="1bdf9-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1bdf9-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1bdf9-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1bdf9-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1bdf9-125">Remarks</span></span>  

 <span data-ttu-id="1bdf9-126">Después de llamar a CLR `SetCLRIoCompletionManager` , el host debe llamar a [ICLRIoCompletionManager:: alcomplete](iclriocompletionmanager-oncomplete-method.md) para notificar a CLR cuando se ha completado una solicitud de e/s.</span><span class="sxs-lookup"><span data-stu-id="1bdf9-126">After the CLR has called `SetCLRIoCompletionManager`, the host must call [ICLRIoCompletionManager::OnComplete](iclriocompletionmanager-oncomplete-method.md) to notify the CLR when an I/O request has been completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bdf9-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1bdf9-127">Requirements</span></span>  

 <span data-ttu-id="1bdf9-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1bdf9-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bdf9-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1bdf9-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1bdf9-130">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1bdf9-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1bdf9-131">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1bdf9-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bdf9-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="1bdf9-132">See also</span></span>

- [<span data-ttu-id="1bdf9-133">ICLRIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1bdf9-133">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="1bdf9-134">IHostIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1bdf9-134">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
