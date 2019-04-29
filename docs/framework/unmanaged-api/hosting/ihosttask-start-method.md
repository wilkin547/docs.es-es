---
title: IHostTask::Start (Método)
ms.date: 03/30/2017
api_name:
- IHostTask.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Start
helpviewer_keywords:
- IHostTask::Start method [.NET Framework hosting]
- Start method, IHostTask interface [.NET Framework hosting]
ms.assetid: b18742b0-d8c4-401c-ae89-e6eccdaa81d0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d45c5b09358430535438734b38e5dce5d1bcdd3e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789505"
---
# <a name="ihosttaskstart-method"></a><span data-ttu-id="71759-102">IHostTask::Start (Método)</span><span class="sxs-lookup"><span data-stu-id="71759-102">IHostTask::Start Method</span></span>
<span data-ttu-id="71759-103">Solicita que el host mueva la tarea representada por el actual [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instancia de suspendido al estado activo, en el que se puede ejecutar el código.</span><span class="sxs-lookup"><span data-stu-id="71759-103">Requests that the host move the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance from a suspended to a live state, in which code can be executed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71759-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="71759-104">Syntax</span></span>  
  
```  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="71759-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="71759-105">Return Value</span></span>  
  
|<span data-ttu-id="71759-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="71759-106">HRESULT</span></span>|<span data-ttu-id="71759-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="71759-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="71759-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="71759-108">S_OK</span></span>|<span data-ttu-id="71759-109">Start se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="71759-109">Start returned successfully.</span></span>|  
|<span data-ttu-id="71759-110">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="71759-110">E_FAIL</span></span>|<span data-ttu-id="71759-111">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="71759-111">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="71759-112">Cuando un método devuelve E_FAIL, common language runtime (CLR) ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="71759-112">When a method returns E_FAIL, the common language runtime (CLR) is no longer usable within the process.</span></span> <span data-ttu-id="71759-113">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="71759-113">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71759-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="71759-114">Remarks</span></span>  
 <span data-ttu-id="71759-115">`Start` siempre devuelve un valor HRESULT de S_OK, excepto en casos donde se ha producido un error catastrófico.</span><span class="sxs-lookup"><span data-stu-id="71759-115">`Start` always returns an HRESULT value of S_OK, except in cases where a catastrophic failure has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71759-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="71759-116">Requirements</span></span>  
 <span data-ttu-id="71759-117">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71759-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71759-118">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="71759-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="71759-119">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="71759-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="71759-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71759-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71759-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="71759-121">See also</span></span>

- [<span data-ttu-id="71759-122">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="71759-122">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="71759-123">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="71759-123">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="71759-124">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="71759-124">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="71759-125">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="71759-125">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
