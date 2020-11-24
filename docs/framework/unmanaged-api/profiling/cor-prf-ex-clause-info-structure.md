---
title: COR_PRF_EX_CLAUSE_INFO (Estructura)
ms.date: 03/30/2017
api_name:
- COR_PRF_EX_CLAUSE_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_EX_CLAUSE_INFO
helpviewer_keywords:
- COR_PRF_EX_CLAUSE_INFO structure [.NET Framework profiling]
ms.assetid: 7d0d6fb7-bc9d-40f0-8163-c0d162eaba7d
topic_type:
- apiref
ms.openlocfilehash: e8dd9f21803021975f4651ba3e6e5f4d3da0ea82
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675001"
---
# <a name="cor_prf_ex_clause_info-structure"></a><span data-ttu-id="53a01-102">COR_PRF_EX_CLAUSE_INFO (Estructura)</span><span class="sxs-lookup"><span data-stu-id="53a01-102">COR_PRF_EX_CLAUSE_INFO Structure</span></span>

<span data-ttu-id="53a01-103">Almacena información sobre una instancia específica de cláusula de excepción y su marco asociado.</span><span class="sxs-lookup"><span data-stu-id="53a01-103">Stores information about a specific exception clause instance and its associated frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53a01-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="53a01-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_PRF_EX_CLAUSE_INFO {  
    COR_PRF_CLAUSE_TYPE clauseType;  
    UINT_PTR programCounter;  
    UINT_PTR framePointer;  
    UINT_PTR shadowStackPointer;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="53a01-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="53a01-105">Members</span></span>  
  
|<span data-ttu-id="53a01-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="53a01-106">Member</span></span>|<span data-ttu-id="53a01-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="53a01-107">Description</span></span>|  
|------------|-----------------|  
|`clauseType`|<span data-ttu-id="53a01-108">Un valor de la enumeración [COR_PRF_CLAUSE_TYPE](cor-prf-clause-type-enumeration.md) que especifica el tipo de cláusula de excepción que el código acaba de escribir o a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="53a01-108">A value of the [COR_PRF_CLAUSE_TYPE](cor-prf-clause-type-enumeration.md) enumeration that specifies the type of exception clause the code just entered or left.</span></span>|  
|`programCounter`|<span data-ttu-id="53a01-109">El punto de entrada nativo del controlador de la cláusula, por ejemplo, el contenido del registro de la EIP x86.</span><span class="sxs-lookup"><span data-stu-id="53a01-109">The native entry point of the clause handler — for example, the contents of the X86 EIP register.</span></span>|  
|`framePointer`|<span data-ttu-id="53a01-110">El puntero al marco lógico para el controlador de la cláusula, por ejemplo, el contenido del registro del EBP x86.</span><span class="sxs-lookup"><span data-stu-id="53a01-110">The pointer to the logical frame for the clause handler — for example, the contents of the X86 EBP register.</span></span>|  
|`shadowStackPointer`|<span data-ttu-id="53a01-111">Puntero a la pila de la sombra.</span><span class="sxs-lookup"><span data-stu-id="53a01-111">The pointer to the shadow stack.</span></span> <span data-ttu-id="53a01-112">Este valor es el contenido del registro de BSP y se aplica solo a IA64.</span><span class="sxs-lookup"><span data-stu-id="53a01-112">This value is the contents of the BSP register and applies only to IA64.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53a01-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="53a01-113">Remarks</span></span>  

 <span data-ttu-id="53a01-114">Cuando se recibe una notificación de excepción, se puede usar [ICorProfilerInfo2:: getnotifiedexceptionclauseinfo (](icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) para obtener la información de la dirección nativa y el marco de la cláusula de excepción ( `catch` / `finally` /Filter) que está a punto de ejecutarse o que se acaba de ejecutar.</span><span class="sxs-lookup"><span data-stu-id="53a01-114">When an exception notification is received, [ICorProfilerInfo2::GetNotifiedExceptionClauseInfo](icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) can be used to get the native address and frame information for the exception clause (`catch`/`finally`/filter) that is about to be run or has just been run.</span></span>  
  
 <span data-ttu-id="53a01-115">La ejecución de una cláusula de excepción implica estas devoluciones de llamada de Common Language Runtime (CLR):</span><span class="sxs-lookup"><span data-stu-id="53a01-115">Execution of an exception clause involves these callbacks from the common language runtime (CLR):</span></span>  
  
- [<span data-ttu-id="53a01-116">ICorProfilerCallback:: Exceptioncatcherenter (</span><span class="sxs-lookup"><span data-stu-id="53a01-116">ICorProfilerCallback::ExceptionCatcherEnter</span></span>](icorprofilercallback-exceptioncatcherenter-method.md)  
  
- [<span data-ttu-id="53a01-117">ICorProfilerCallback:: Exceptionunwindfinallyenter (</span><span class="sxs-lookup"><span data-stu-id="53a01-117">ICorProfilerCallback::ExceptionUnwindFinallyEnter</span></span>](icorprofilercallback-exceptionunwindfinallyenter-method.md)  
  
- [<span data-ttu-id="53a01-118">ICorProfilerCallback:: Exceptionsearchfilterenter (</span><span class="sxs-lookup"><span data-stu-id="53a01-118">ICorProfilerCallback::ExceptionSearchFilterEnter</span></span>](icorprofilercallback-exceptionsearchfilterenter-method.md)  
  
- [<span data-ttu-id="53a01-119">ICorProfilerCallback:: Exceptioncatcherleave (</span><span class="sxs-lookup"><span data-stu-id="53a01-119">ICorProfilerCallback::ExceptionCatcherLeave</span></span>](icorprofilercallback-exceptioncatcherleave-method.md)  
  
- [<span data-ttu-id="53a01-120">ICorProfilerCallback:: ExceptionUnwindFinallyLeave (</span><span class="sxs-lookup"><span data-stu-id="53a01-120">ICorProfilerCallback::ExceptionUnwindFinallyLeave</span></span>](icorprofilercallback-exceptionunwindfinallyleave-method.md)  
  
- [<span data-ttu-id="53a01-121">ICorProfilerCallback:: Exceptionsearchfilterleave (</span><span class="sxs-lookup"><span data-stu-id="53a01-121">ICorProfilerCallback::ExceptionSearchFilterLeave</span></span>](icorprofilercallback-exceptionsearchfilterleave-method.md)  
  
## <a name="requirements"></a><span data-ttu-id="53a01-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="53a01-122">Requirements</span></span>  

 <span data-ttu-id="53a01-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53a01-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53a01-124">**Encabezado:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="53a01-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="53a01-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="53a01-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="53a01-126">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53a01-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53a01-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="53a01-127">See also</span></span>

- [<span data-ttu-id="53a01-128">Estructuras para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="53a01-128">Profiling Structures</span></span>](profiling-structures.md)
