---
title: COR_PRF_TRANSITION_REASON (Enumeración)
ms.date: 03/30/2017
api_name:
- COR_PRF_TRANSITION_REASON
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_TRANSITION_REASON
helpviewer_keywords:
- COR_PRF_TRANSITION_REASON enumeration [.NET Framework profiling]
ms.assetid: da941118-01b7-4197-ae5b-9f2f8adcd623
topic_type:
- apiref
ms.openlocfilehash: 747313f217092652d5a9404fbf81383fa0828ee9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696666"
---
# <a name="cor_prf_transition_reason-enumeration"></a><span data-ttu-id="f6fe1-102">COR_PRF_TRANSITION_REASON (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="f6fe1-102">COR_PRF_TRANSITION_REASON Enumeration</span></span>

<span data-ttu-id="f6fe1-103">Indica el motivo para una transición desde código administrado a no administrado, y o viceversa.</span><span class="sxs-lookup"><span data-stu-id="f6fe1-103">Indicates the reason for a transition from managed to unmanaged code, or vice versa.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6fe1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f6fe1-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_TRANSITION_CALL,  
    COR_PRF_TRANSITION_RETURN  
} COR_PRF_TRANSITION_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="f6fe1-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="f6fe1-105">Members</span></span>  
  
|<span data-ttu-id="f6fe1-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="f6fe1-106">Member</span></span>|<span data-ttu-id="f6fe1-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f6fe1-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_TRANSITION_CALL`|<span data-ttu-id="f6fe1-108">La transición se debe a una llamada a una función.</span><span class="sxs-lookup"><span data-stu-id="f6fe1-108">The transition is due to a call into a function.</span></span>|  
|`COR_PRF_TRANSITION_RETURN`|<span data-ttu-id="f6fe1-109">La transición se debe a un valor devuelto de una función.</span><span class="sxs-lookup"><span data-stu-id="f6fe1-109">The transition is due to a return from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6fe1-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f6fe1-110">Remarks</span></span>  

 <span data-ttu-id="f6fe1-111">Cuando se produce una transición, el generador de perfiles recibe una devolución de llamada [ICorProfilerCallback:: ManagedToUnmanagedTransition (](icorprofilercallback-managedtounmanagedtransition-method.md) o [ICorProfilerCallback:: UnmanagedToManagedTransition (](icorprofilercallback-unmanagedtomanagedtransition-method.md) , que proporciona un valor de la `COR_PRF_TRANSITION_REASON` enumeración para indicar el motivo de la transición.</span><span class="sxs-lookup"><span data-stu-id="f6fe1-111">When a transition occurs, the profiler receives an [ICorProfilerCallback::ManagedToUnmanagedTransition](icorprofilercallback-managedtounmanagedtransition-method.md) or [ICorProfilerCallback::UnmanagedToManagedTransition](icorprofilercallback-unmanagedtomanagedtransition-method.md) callback, either of which provides a value of the `COR_PRF_TRANSITION_REASON` enumeration to indicate the reason for the transition.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6fe1-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f6fe1-112">Requirements</span></span>  

 <span data-ttu-id="f6fe1-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6fe1-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6fe1-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f6fe1-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f6fe1-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6fe1-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6fe1-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6fe1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
