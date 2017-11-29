---
title: "IHostTask::Start (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTask.Start
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTask::Start
helpviewer_keywords:
- IHostTask::Start method [.NET Framework hosting]
- Start method, IHostTask interface [.NET Framework hosting]
ms.assetid: b18742b0-d8c4-401c-ae89-e6eccdaa81d0
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f1a289099245228b8806639cb98f579bc56317b0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskstart-method"></a><span data-ttu-id="f64cf-102">IHostTask::Start (Método)</span><span class="sxs-lookup"><span data-stu-id="f64cf-102">IHostTask::Start Method</span></span>
<span data-ttu-id="f64cf-103">Solicita que el host mueva la tarea representada por el actual [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instancia de suspendido al estado activo, en el que se puede ejecutar código.</span><span class="sxs-lookup"><span data-stu-id="f64cf-103">Requests that the host move the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance from a suspended to a live state, in which code can be executed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f64cf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f64cf-104">Syntax</span></span>  
  
```  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f64cf-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f64cf-105">Return Value</span></span>  
  
|<span data-ttu-id="f64cf-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f64cf-106">HRESULT</span></span>|<span data-ttu-id="f64cf-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f64cf-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f64cf-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="f64cf-108">S_OK</span></span>|<span data-ttu-id="f64cf-109">Start se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="f64cf-109">Start returned successfully.</span></span>|  
|<span data-ttu-id="f64cf-110">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f64cf-110">E_FAIL</span></span>|<span data-ttu-id="f64cf-111">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="f64cf-111">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f64cf-112">Cuando un método devuelve E_FAIL, common language runtime (CLR) ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="f64cf-112">When a method returns E_FAIL, the common language runtime (CLR) is no longer usable within the process.</span></span> <span data-ttu-id="f64cf-113">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f64cf-113">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f64cf-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f64cf-114">Remarks</span></span>  
 <span data-ttu-id="f64cf-115">`Start`siempre devuelve un valor HRESULT de S_OK, excepto en casos donde se ha producido un error catastrófico.</span><span class="sxs-lookup"><span data-stu-id="f64cf-115">`Start` always returns an HRESULT value of S_OK, except in cases where a catastrophic failure has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f64cf-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f64cf-116">Requirements</span></span>  
 <span data-ttu-id="f64cf-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f64cf-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f64cf-118">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f64cf-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f64cf-119">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f64cf-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f64cf-120">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f64cf-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f64cf-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="f64cf-121">See Also</span></span>  
 [<span data-ttu-id="f64cf-122">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f64cf-122">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="f64cf-123">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f64cf-123">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="f64cf-124">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f64cf-124">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="f64cf-125">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f64cf-125">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
