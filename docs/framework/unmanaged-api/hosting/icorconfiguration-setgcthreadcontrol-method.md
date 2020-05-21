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
ms.openlocfilehash: 7874424150e0f4e1818ad9c72e31fd584e016829
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762401"
---
# <a name="icorconfigurationsetgcthreadcontrol-method"></a><span data-ttu-id="0e778-102">ICorConfiguration::SetGCThreadControl (Método)</span><span class="sxs-lookup"><span data-stu-id="0e778-102">ICorConfiguration::SetGCThreadControl Method</span></span>
<span data-ttu-id="0e778-103">Establece la interfaz de devolución de llamada para programar subprocesos para tareas no en tiempo de ejecución que, de lo contrario, se bloquearían para una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="0e778-103">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e778-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0e778-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCThreadControl (  
    [in] IGCThreadControl* pGCThreadControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e778-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0e778-105">Parameters</span></span>  
 `pGCThreadControl`  
 <span data-ttu-id="0e778-106">de Un puntero a un objeto [IGCThreadControl](igcthreadcontrol-interface.md) que notifica al host la suspensión de subprocesos para tareas que no son de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0e778-106">[in] A pointer to an [IGCThreadControl](igcthreadcontrol-interface.md) object that notifies the host about the suspension of threads for non-runtime tasks.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e778-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0e778-107">Remarks</span></span>  
 <span data-ttu-id="0e778-108">El host puede elegir dentro de la devolución de llamada [IGCThreadControl:: ThreadIsBlockingForSuspension (](igcthreadcontrol-threadisblockingforsuspension-method.md) si se va a volver a programar un subproceso.</span><span class="sxs-lookup"><span data-stu-id="0e778-108">The host may choose within the [IGCThreadControl::ThreadIsBlockingForSuspension](igcthreadcontrol-threadisblockingforsuspension-method.md) callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e778-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0e778-109">Requirements</span></span>  
 <span data-ttu-id="0e778-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e778-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e778-111">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0e778-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0e778-112">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0e778-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0e778-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e778-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e778-114">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="0e778-114">See also</span></span>

- [<span data-ttu-id="0e778-115">ICorConfiguration (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0e778-115">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)
