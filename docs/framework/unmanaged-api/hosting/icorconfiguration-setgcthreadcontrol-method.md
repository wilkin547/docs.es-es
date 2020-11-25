---
title: ICorConfiguration::SetGCThreadControl (Método)
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetGCThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCThreadControl
helpviewer_keywords:
- ICorConfiguration::SetGCThreadControl method [.NET Framework hosting]
- SetGCThreadControl method [.NET Framework hosting]
ms.assetid: 72e38e61-3d56-4ae3-b8f6-0ab7922aaf11
topic_type:
- apiref
ms.openlocfilehash: 28b012bbe3f8c11ecd0afb8b5905336bd99c349c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724031"
---
# <a name="icorconfigurationsetgcthreadcontrol-method"></a><span data-ttu-id="2445b-102">ICorConfiguration::SetGCThreadControl (Método)</span><span class="sxs-lookup"><span data-stu-id="2445b-102">ICorConfiguration::SetGCThreadControl Method</span></span>

<span data-ttu-id="2445b-103">Establece la interfaz de devolución de llamada para programar subprocesos para tareas no en tiempo de ejecución que, de lo contrario, se bloquearían para una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="2445b-103">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2445b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2445b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCThreadControl (  
    [in] IGCThreadControl* pGCThreadControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2445b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2445b-105">Parameters</span></span>  

 `pGCThreadControl`  
 <span data-ttu-id="2445b-106">de Un puntero a un objeto [IGCThreadControl](igcthreadcontrol-interface.md) que notifica al host la suspensión de subprocesos para tareas que no son de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2445b-106">[in] A pointer to an [IGCThreadControl](igcthreadcontrol-interface.md) object that notifies the host about the suspension of threads for non-runtime tasks.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2445b-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2445b-107">Remarks</span></span>  

 <span data-ttu-id="2445b-108">El host puede elegir dentro de la devolución de llamada [IGCThreadControl:: ThreadIsBlockingForSuspension (](igcthreadcontrol-threadisblockingforsuspension-method.md) si se va a volver a programar un subproceso.</span><span class="sxs-lookup"><span data-stu-id="2445b-108">The host may choose within the [IGCThreadControl::ThreadIsBlockingForSuspension](igcthreadcontrol-threadisblockingforsuspension-method.md) callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2445b-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2445b-109">Requirements</span></span>  

 <span data-ttu-id="2445b-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2445b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2445b-111">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2445b-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2445b-112">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2445b-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2445b-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2445b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2445b-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2445b-114">See also</span></span>

- [<span data-ttu-id="2445b-115">ICorConfiguration (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2445b-115">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)
