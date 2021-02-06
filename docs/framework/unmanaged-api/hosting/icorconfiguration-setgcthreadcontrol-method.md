---
description: 'Más información sobre: ICorConfiguration:: Setgcthreadcontrol ((método)'
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
ms.openlocfilehash: 8b9388bdefb9da2ce51b62ab68eeee54645e43ad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636649"
---
# <a name="icorconfigurationsetgcthreadcontrol-method"></a><span data-ttu-id="72804-103">ICorConfiguration::SetGCThreadControl (Método)</span><span class="sxs-lookup"><span data-stu-id="72804-103">ICorConfiguration::SetGCThreadControl Method</span></span>

<span data-ttu-id="72804-104">Establece la interfaz de devolución de llamada para programar subprocesos para tareas no en tiempo de ejecución que, de lo contrario, se bloquearían para una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="72804-104">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72804-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="72804-105">Syntax</span></span>  
  
```cpp  
HRESULT SetGCThreadControl (  
    [in] IGCThreadControl* pGCThreadControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72804-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="72804-106">Parameters</span></span>  

 `pGCThreadControl`  
 <span data-ttu-id="72804-107">de Un puntero a un objeto [IGCThreadControl](igcthreadcontrol-interface.md) que notifica al host la suspensión de subprocesos para tareas que no son de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="72804-107">[in] A pointer to an [IGCThreadControl](igcthreadcontrol-interface.md) object that notifies the host about the suspension of threads for non-runtime tasks.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72804-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="72804-108">Remarks</span></span>  

 <span data-ttu-id="72804-109">El host puede elegir dentro de la devolución de llamada [IGCThreadControl:: ThreadIsBlockingForSuspension (](igcthreadcontrol-threadisblockingforsuspension-method.md) si se va a volver a programar un subproceso.</span><span class="sxs-lookup"><span data-stu-id="72804-109">The host may choose within the [IGCThreadControl::ThreadIsBlockingForSuspension](igcthreadcontrol-threadisblockingforsuspension-method.md) callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72804-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="72804-110">Requirements</span></span>  

 <span data-ttu-id="72804-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72804-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72804-112">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="72804-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="72804-113">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="72804-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="72804-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72804-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72804-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="72804-115">See also</span></span>

- [<span data-ttu-id="72804-116">ICorConfiguration (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="72804-116">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)
