---
description: 'Más información acerca de: IHostTask:: Start (método)'
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
ms.openlocfilehash: 48352a3df49ba2ef3e008ed211da19f54deb82f6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784631"
---
# <a name="ihosttaskstart-method"></a><span data-ttu-id="4bc6d-103">IHostTask::Start (Método)</span><span class="sxs-lookup"><span data-stu-id="4bc6d-103">IHostTask::Start Method</span></span>

<span data-ttu-id="4bc6d-104">Solicita que el host mueva la tarea representada por la instancia actual de [IHostTask](ihosttask-interface.md) de un estado suspendido a activo, en el que se puede ejecutar el código.</span><span class="sxs-lookup"><span data-stu-id="4bc6d-104">Requests that the host move the task represented by the current [IHostTask](ihosttask-interface.md) instance from a suspended to a live state, in which code can be executed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bc6d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4bc6d-105">Syntax</span></span>  
  
```cpp  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="4bc6d-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4bc6d-106">Return Value</span></span>  
  
|<span data-ttu-id="4bc6d-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4bc6d-107">HRESULT</span></span>|<span data-ttu-id="4bc6d-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="4bc6d-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4bc6d-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="4bc6d-109">S_OK</span></span>|<span data-ttu-id="4bc6d-110">El inicio se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="4bc6d-110">Start returned successfully.</span></span>|  
|<span data-ttu-id="4bc6d-111">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4bc6d-111">E_FAIL</span></span>|<span data-ttu-id="4bc6d-112">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="4bc6d-112">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4bc6d-113">Cuando un método devuelve E_FAIL, el Common Language Runtime (CLR) ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="4bc6d-113">When a method returns E_FAIL, the common language runtime (CLR) is no longer usable within the process.</span></span> <span data-ttu-id="4bc6d-114">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4bc6d-114">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4bc6d-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4bc6d-115">Remarks</span></span>  

 <span data-ttu-id="4bc6d-116">`Start` siempre devuelve un valor HRESULT de S_OK, excepto en los casos en los que se ha producido un error catastrófico.</span><span class="sxs-lookup"><span data-stu-id="4bc6d-116">`Start` always returns an HRESULT value of S_OK, except in cases where a catastrophic failure has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bc6d-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4bc6d-117">Requirements</span></span>  

 <span data-ttu-id="4bc6d-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4bc6d-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4bc6d-119">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4bc6d-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4bc6d-120">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4bc6d-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4bc6d-121">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4bc6d-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bc6d-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="4bc6d-122">See also</span></span>

- [<span data-ttu-id="4bc6d-123">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4bc6d-123">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="4bc6d-124">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4bc6d-124">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="4bc6d-125">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4bc6d-125">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="4bc6d-126">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4bc6d-126">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
