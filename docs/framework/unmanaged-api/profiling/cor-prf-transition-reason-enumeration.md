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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c22e3c7c04a2b85723f1c0dba4543465faccab58
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745495"
---
# <a name="corprftransitionreason-enumeration"></a><span data-ttu-id="c1715-102">COR_PRF_TRANSITION_REASON (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="c1715-102">COR_PRF_TRANSITION_REASON Enumeration</span></span>
<span data-ttu-id="c1715-103">Indica el motivo para una transición desde código administrado a no administrado, y o viceversa.</span><span class="sxs-lookup"><span data-stu-id="c1715-103">Indicates the reason for a transition from managed to unmanaged code, or vice versa.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1715-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c1715-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_TRANSITION_CALL,  
    COR_PRF_TRANSITION_RETURN  
} COR_PRF_TRANSITION_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="c1715-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="c1715-105">Members</span></span>  
  
|<span data-ttu-id="c1715-106">Member</span><span class="sxs-lookup"><span data-stu-id="c1715-106">Member</span></span>|<span data-ttu-id="c1715-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c1715-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_TRANSITION_CALL`|<span data-ttu-id="c1715-108">La transición es debido a una llamada a una función.</span><span class="sxs-lookup"><span data-stu-id="c1715-108">The transition is due to a call into a function.</span></span>|  
|`COR_PRF_TRANSITION_RETURN`|<span data-ttu-id="c1715-109">La transición es debido a una devolución de una función.</span><span class="sxs-lookup"><span data-stu-id="c1715-109">The transition is due to a return from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1715-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c1715-110">Remarks</span></span>  
 <span data-ttu-id="c1715-111">Cuando se produce una transición, el generador de perfiles recibe una [ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md) o [UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md) devolución de llamada, cualquiera de los cuales Proporciona un valor de la `COR_PRF_TRANSITION_REASON` enumeración para indicar el motivo de la transición.</span><span class="sxs-lookup"><span data-stu-id="c1715-111">When a transition occurs, the profiler receives an [ICorProfilerCallback::ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md) or [ICorProfilerCallback::UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md) callback, either of which provides a value of the `COR_PRF_TRANSITION_REASON` enumeration to indicate the reason for the transition.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1715-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c1715-112">Requirements</span></span>  
 <span data-ttu-id="c1715-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1715-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1715-114">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c1715-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c1715-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c1715-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c1715-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1715-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
