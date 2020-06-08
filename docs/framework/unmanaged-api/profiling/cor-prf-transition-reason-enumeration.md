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
ms.openlocfilehash: e890c62a54654e86bb4a825613807efe142c8d5a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500746"
---
# <a name="cor_prf_transition_reason-enumeration"></a><span data-ttu-id="4bb4c-102">COR_PRF_TRANSITION_REASON (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="4bb4c-102">COR_PRF_TRANSITION_REASON Enumeration</span></span>
<span data-ttu-id="4bb4c-103">Indica el motivo para una transición desde código administrado a no administrado, y o viceversa.</span><span class="sxs-lookup"><span data-stu-id="4bb4c-103">Indicates the reason for a transition from managed to unmanaged code, or vice versa.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bb4c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4bb4c-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_TRANSITION_CALL,  
    COR_PRF_TRANSITION_RETURN  
} COR_PRF_TRANSITION_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="4bb4c-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="4bb4c-105">Members</span></span>  
  
|<span data-ttu-id="4bb4c-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="4bb4c-106">Member</span></span>|<span data-ttu-id="4bb4c-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="4bb4c-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_TRANSITION_CALL`|<span data-ttu-id="4bb4c-108">La transición se debe a una llamada a una función.</span><span class="sxs-lookup"><span data-stu-id="4bb4c-108">The transition is due to a call into a function.</span></span>|  
|`COR_PRF_TRANSITION_RETURN`|<span data-ttu-id="4bb4c-109">La transición se debe a un valor devuelto de una función.</span><span class="sxs-lookup"><span data-stu-id="4bb4c-109">The transition is due to a return from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4bb4c-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4bb4c-110">Remarks</span></span>  
 <span data-ttu-id="4bb4c-111">Cuando se produce una transición, el generador de perfiles recibe una devolución de llamada [ICorProfilerCallback:: ManagedToUnmanagedTransition (](icorprofilercallback-managedtounmanagedtransition-method.md) o [ICorProfilerCallback:: UnmanagedToManagedTransition (](icorprofilercallback-unmanagedtomanagedtransition-method.md) , que proporciona un valor de la `COR_PRF_TRANSITION_REASON` enumeración para indicar el motivo de la transición.</span><span class="sxs-lookup"><span data-stu-id="4bb4c-111">When a transition occurs, the profiler receives an [ICorProfilerCallback::ManagedToUnmanagedTransition](icorprofilercallback-managedtounmanagedtransition-method.md) or [ICorProfilerCallback::UnmanagedToManagedTransition](icorprofilercallback-unmanagedtomanagedtransition-method.md) callback, either of which provides a value of the `COR_PRF_TRANSITION_REASON` enumeration to indicate the reason for the transition.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bb4c-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4bb4c-112">Requirements</span></span>  
 <span data-ttu-id="4bb4c-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4bb4c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4bb4c-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4bb4c-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4bb4c-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4bb4c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4bb4c-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4bb4c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
