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
ms.openlocfilehash: 4143c3d25dd5262a10b53708a249910cc79f5314
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720443"
---
# <a name="ihosttaskstart-method"></a><span data-ttu-id="a5138-102">IHostTask::Start (Método)</span><span class="sxs-lookup"><span data-stu-id="a5138-102">IHostTask::Start Method</span></span>

<span data-ttu-id="a5138-103">Solicita que el host mueva la tarea representada por la instancia actual de [IHostTask](ihosttask-interface.md) de un estado suspendido a activo, en el que se puede ejecutar el código.</span><span class="sxs-lookup"><span data-stu-id="a5138-103">Requests that the host move the task represented by the current [IHostTask](ihosttask-interface.md) instance from a suspended to a live state, in which code can be executed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5138-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a5138-104">Syntax</span></span>  
  
```cpp  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a5138-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a5138-105">Return Value</span></span>  
  
|<span data-ttu-id="a5138-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a5138-106">HRESULT</span></span>|<span data-ttu-id="a5138-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a5138-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a5138-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="a5138-108">S_OK</span></span>|<span data-ttu-id="a5138-109">El inicio se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="a5138-109">Start returned successfully.</span></span>|  
|<span data-ttu-id="a5138-110">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a5138-110">E_FAIL</span></span>|<span data-ttu-id="a5138-111">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="a5138-111">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a5138-112">Cuando un método devuelve E_FAIL, el Common Language Runtime (CLR) ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="a5138-112">When a method returns E_FAIL, the common language runtime (CLR) is no longer usable within the process.</span></span> <span data-ttu-id="a5138-113">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a5138-113">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5138-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a5138-114">Remarks</span></span>  

 <span data-ttu-id="a5138-115">`Start` siempre devuelve un valor HRESULT de S_OK, excepto en los casos en los que se ha producido un error catastrófico.</span><span class="sxs-lookup"><span data-stu-id="a5138-115">`Start` always returns an HRESULT value of S_OK, except in cases where a catastrophic failure has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5138-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a5138-116">Requirements</span></span>  

 <span data-ttu-id="a5138-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5138-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5138-118">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a5138-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a5138-119">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a5138-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a5138-120">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5138-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5138-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a5138-121">See also</span></span>

- [<span data-ttu-id="a5138-122">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a5138-122">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="a5138-123">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a5138-123">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="a5138-124">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a5138-124">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="a5138-125">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a5138-125">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
