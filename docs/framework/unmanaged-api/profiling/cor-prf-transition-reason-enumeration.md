---
description: 'Más información acerca de: enumeración COR_PRF_TRANSITION_REASON'
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
ms.openlocfilehash: 8d0b7852f80f80a47f910e9f1240a5315772cd23
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789000"
---
# <a name="cor_prf_transition_reason-enumeration"></a><span data-ttu-id="a5610-103">COR_PRF_TRANSITION_REASON (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="a5610-103">COR_PRF_TRANSITION_REASON Enumeration</span></span>

<span data-ttu-id="a5610-104">Indica el motivo para una transición desde código administrado a no administrado, y o viceversa.</span><span class="sxs-lookup"><span data-stu-id="a5610-104">Indicates the reason for a transition from managed to unmanaged code, or vice versa.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5610-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a5610-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_TRANSITION_CALL,  
    COR_PRF_TRANSITION_RETURN  
} COR_PRF_TRANSITION_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="a5610-106">Members</span><span class="sxs-lookup"><span data-stu-id="a5610-106">Members</span></span>  
  
|<span data-ttu-id="a5610-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="a5610-107">Member</span></span>|<span data-ttu-id="a5610-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="a5610-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_TRANSITION_CALL`|<span data-ttu-id="a5610-109">La transición se debe a una llamada a una función.</span><span class="sxs-lookup"><span data-stu-id="a5610-109">The transition is due to a call into a function.</span></span>|  
|`COR_PRF_TRANSITION_RETURN`|<span data-ttu-id="a5610-110">La transición se debe a un valor devuelto de una función.</span><span class="sxs-lookup"><span data-stu-id="a5610-110">The transition is due to a return from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5610-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a5610-111">Remarks</span></span>  

 <span data-ttu-id="a5610-112">Cuando se produce una transición, el generador de perfiles recibe una devolución de llamada [ICorProfilerCallback:: ManagedToUnmanagedTransition (](icorprofilercallback-managedtounmanagedtransition-method.md) o [ICorProfilerCallback:: UnmanagedToManagedTransition (](icorprofilercallback-unmanagedtomanagedtransition-method.md) , que proporciona un valor de la `COR_PRF_TRANSITION_REASON` enumeración para indicar el motivo de la transición.</span><span class="sxs-lookup"><span data-stu-id="a5610-112">When a transition occurs, the profiler receives an [ICorProfilerCallback::ManagedToUnmanagedTransition](icorprofilercallback-managedtounmanagedtransition-method.md) or [ICorProfilerCallback::UnmanagedToManagedTransition](icorprofilercallback-unmanagedtomanagedtransition-method.md) callback, either of which provides a value of the `COR_PRF_TRANSITION_REASON` enumeration to indicate the reason for the transition.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5610-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a5610-113">Requirements</span></span>  

 <span data-ttu-id="a5610-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5610-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5610-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a5610-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a5610-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5610-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5610-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5610-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
