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
ms.openlocfilehash: fe93a3bab267ccca941974b734c86329ad0f4d03
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121337"
---
# <a name="ihosttaskstart-method"></a><span data-ttu-id="51f54-102">IHostTask::Start (Método)</span><span class="sxs-lookup"><span data-stu-id="51f54-102">IHostTask::Start Method</span></span>
<span data-ttu-id="51f54-103">Solicita que el host mueva la tarea representada por la instancia actual de [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) de un estado suspendido a activo, en el que se puede ejecutar el código.</span><span class="sxs-lookup"><span data-stu-id="51f54-103">Requests that the host move the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance from a suspended to a live state, in which code can be executed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51f54-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="51f54-104">Syntax</span></span>  
  
```cpp  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="51f54-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="51f54-105">Return Value</span></span>  
  
|<span data-ttu-id="51f54-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="51f54-106">HRESULT</span></span>|<span data-ttu-id="51f54-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="51f54-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="51f54-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="51f54-108">S_OK</span></span>|<span data-ttu-id="51f54-109">El inicio se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="51f54-109">Start returned successfully.</span></span>|  
|<span data-ttu-id="51f54-110">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="51f54-110">E_FAIL</span></span>|<span data-ttu-id="51f54-111">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="51f54-111">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="51f54-112">Cuando un método devuelve E_FAIL, el Common Language Runtime (CLR) ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="51f54-112">When a method returns E_FAIL, the common language runtime (CLR) is no longer usable within the process.</span></span> <span data-ttu-id="51f54-113">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="51f54-113">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51f54-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="51f54-114">Remarks</span></span>  
 <span data-ttu-id="51f54-115">`Start` siempre devuelve un valor HRESULT de S_OK, excepto en los casos en los que se ha producido un error catastrófico.</span><span class="sxs-lookup"><span data-stu-id="51f54-115">`Start` always returns an HRESULT value of S_OK, except in cases where a catastrophic failure has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51f54-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="51f54-116">Requirements</span></span>  
 <span data-ttu-id="51f54-117">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51f54-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51f54-118">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="51f54-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="51f54-119">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="51f54-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="51f54-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51f54-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51f54-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="51f54-121">See also</span></span>

- [<span data-ttu-id="51f54-122">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="51f54-122">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="51f54-123">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="51f54-123">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="51f54-124">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="51f54-124">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="51f54-125">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="51f54-125">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
