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
ms.openlocfilehash: a4e8211f091b2a3a4f24d8350f6d7dbe7d7920af
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842397"
---
# <a name="ihosttaskstart-method"></a><span data-ttu-id="6dc56-102">IHostTask::Start (Método)</span><span class="sxs-lookup"><span data-stu-id="6dc56-102">IHostTask::Start Method</span></span>
<span data-ttu-id="6dc56-103">Solicita que el host mueva la tarea representada por la instancia actual de [IHostTask](ihosttask-interface.md) de un estado suspendido a activo, en el que se puede ejecutar el código.</span><span class="sxs-lookup"><span data-stu-id="6dc56-103">Requests that the host move the task represented by the current [IHostTask](ihosttask-interface.md) instance from a suspended to a live state, in which code can be executed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6dc56-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6dc56-104">Syntax</span></span>  
  
```cpp  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="6dc56-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6dc56-105">Return Value</span></span>  
  
|<span data-ttu-id="6dc56-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6dc56-106">HRESULT</span></span>|<span data-ttu-id="6dc56-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="6dc56-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6dc56-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="6dc56-108">S_OK</span></span>|<span data-ttu-id="6dc56-109">El inicio se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="6dc56-109">Start returned successfully.</span></span>|  
|<span data-ttu-id="6dc56-110">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6dc56-110">E_FAIL</span></span>|<span data-ttu-id="6dc56-111">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="6dc56-111">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6dc56-112">Cuando un método devuelve E_FAIL, el Common Language Runtime (CLR) ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="6dc56-112">When a method returns E_FAIL, the common language runtime (CLR) is no longer usable within the process.</span></span> <span data-ttu-id="6dc56-113">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6dc56-113">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6dc56-114">Notas</span><span class="sxs-lookup"><span data-stu-id="6dc56-114">Remarks</span></span>  
 <span data-ttu-id="6dc56-115">`Start`siempre devuelve un valor HRESULT de S_OK, excepto en los casos en los que se ha producido un error catastrófico.</span><span class="sxs-lookup"><span data-stu-id="6dc56-115">`Start` always returns an HRESULT value of S_OK, except in cases where a catastrophic failure has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6dc56-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6dc56-116">Requirements</span></span>  
 <span data-ttu-id="6dc56-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6dc56-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6dc56-118">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="6dc56-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6dc56-119">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6dc56-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6dc56-120">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6dc56-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dc56-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="6dc56-121">See also</span></span>

- [<span data-ttu-id="6dc56-122">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6dc56-122">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="6dc56-123">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6dc56-123">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="6dc56-124">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6dc56-124">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="6dc56-125">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6dc56-125">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
