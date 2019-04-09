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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59101632"
---
# <a name="ihosttaskstart-method"></a><span data-ttu-id="f02ad-102">IHostTask::Start (Método)</span><span class="sxs-lookup"><span data-stu-id="f02ad-102">IHostTask::Start Method</span></span>
<span data-ttu-id="f02ad-103">Solicita que el host mueva la tarea representada por el actual [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instancia de suspendido al estado activo, en el que se puede ejecutar el código.</span><span class="sxs-lookup"><span data-stu-id="f02ad-103">Requests that the host move the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance from a suspended to a live state, in which code can be executed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f02ad-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f02ad-104">Syntax</span></span>  
  
```  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f02ad-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f02ad-105">Return Value</span></span>  
  
|<span data-ttu-id="f02ad-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f02ad-106">HRESULT</span></span>|<span data-ttu-id="f02ad-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f02ad-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f02ad-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="f02ad-108">S_OK</span></span>|<span data-ttu-id="f02ad-109">Start se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="f02ad-109">Start returned successfully.</span></span>|  
|<span data-ttu-id="f02ad-110">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f02ad-110">E_FAIL</span></span>|<span data-ttu-id="f02ad-111">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="f02ad-111">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f02ad-112">Cuando un método devuelve E_FAIL, common language runtime (CLR) ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="f02ad-112">When a method returns E_FAIL, the common language runtime (CLR) is no longer usable within the process.</span></span> <span data-ttu-id="f02ad-113">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f02ad-113">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f02ad-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f02ad-114">Remarks</span></span>  
 `Start` <span data-ttu-id="f02ad-115">siempre devuelve un valor HRESULT de S_OK, excepto en casos donde se ha producido un error catastrófico.</span><span class="sxs-lookup"><span data-stu-id="f02ad-115">always returns an HRESULT value of S_OK, except in cases where a catastrophic failure has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f02ad-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f02ad-116">Requirements</span></span>  
 <span data-ttu-id="f02ad-117">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f02ad-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f02ad-118">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f02ad-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f02ad-119">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f02ad-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="f02ad-120">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f02ad-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f02ad-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="f02ad-121">See also</span></span>

- [<span data-ttu-id="f02ad-122">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f02ad-122">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="f02ad-123">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f02ad-123">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="f02ad-124">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f02ad-124">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="f02ad-125">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f02ad-125">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
