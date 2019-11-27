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
ms.openlocfilehash: df4bfe69b22439073342693a03376a0b506f9c70
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428373"
---
# <a name="cor_prf_ex_clause_info-structure"></a><span data-ttu-id="2561b-102">COR_PRF_EX_CLAUSE_INFO (Estructura)</span><span class="sxs-lookup"><span data-stu-id="2561b-102">COR_PRF_EX_CLAUSE_INFO Structure</span></span>
<span data-ttu-id="2561b-103">Almacena información sobre una instancia específica de cláusula de excepción y su marco asociado.</span><span class="sxs-lookup"><span data-stu-id="2561b-103">Stores information about a specific exception clause instance and its associated frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2561b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2561b-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_PRF_EX_CLAUSE_INFO {  
    COR_PRF_CLAUSE_TYPE clauseType;  
    UINT_PTR programCounter;  
    UINT_PTR framePointer;  
    UINT_PTR shadowStackPointer;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="2561b-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="2561b-105">Members</span></span>  
  
|<span data-ttu-id="2561b-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="2561b-106">Member</span></span>|<span data-ttu-id="2561b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="2561b-107">Description</span></span>|  
|------------|-----------------|  
|`clauseType`|<span data-ttu-id="2561b-108">Un valor de la enumeración [COR_PRF_CLAUSE_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md) que especifica el tipo de cláusula de excepción que el código acaba de escribir o a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="2561b-108">A value of the [COR_PRF_CLAUSE_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md) enumeration that specifies the type of exception clause the code just entered or left.</span></span>|  
|`programCounter`|<span data-ttu-id="2561b-109">El punto de entrada nativo del controlador de la cláusula, por ejemplo, el contenido del registro de la EIP x86.</span><span class="sxs-lookup"><span data-stu-id="2561b-109">The native entry point of the clause handler — for example, the contents of the X86 EIP register.</span></span>|  
|`framePointer`|<span data-ttu-id="2561b-110">El puntero al marco lógico para el controlador de la cláusula, por ejemplo, el contenido del registro del EBP x86.</span><span class="sxs-lookup"><span data-stu-id="2561b-110">The pointer to the logical frame for the clause handler — for example, the contents of the X86 EBP register.</span></span>|  
|`shadowStackPointer`|<span data-ttu-id="2561b-111">Puntero a la pila de la sombra.</span><span class="sxs-lookup"><span data-stu-id="2561b-111">The pointer to the shadow stack.</span></span> <span data-ttu-id="2561b-112">Este valor es el contenido del registro de BSP y se aplica solo a IA64.</span><span class="sxs-lookup"><span data-stu-id="2561b-112">This value is the contents of the BSP register and applies only to IA64.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2561b-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2561b-113">Remarks</span></span>  
 <span data-ttu-id="2561b-114">Cuando se recibe una notificación de excepción, se puede usar [ICorProfilerInfo2:: getnotifiedexceptionclauseinfo (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) para obtener la información de la dirección nativa y el marco de la cláusula de excepción (`catch`/`finally`/Filter) que está a punto de ejecutarse o acaba de ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="2561b-114">When an exception notification is received, [ICorProfilerInfo2::GetNotifiedExceptionClauseInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) can be used to get the native address and frame information for the exception clause (`catch`/`finally`/filter) that is about to be run or has just been run.</span></span>  
  
 <span data-ttu-id="2561b-115">La ejecución de una cláusula de excepción implica estas devoluciones de llamada de Common Language Runtime (CLR):</span><span class="sxs-lookup"><span data-stu-id="2561b-115">Execution of an exception clause involves these callbacks from the common language runtime (CLR):</span></span>  
  
- [<span data-ttu-id="2561b-116">ICorProfilerCallback:: Exceptioncatcherenter (</span><span class="sxs-lookup"><span data-stu-id="2561b-116">ICorProfilerCallback::ExceptionCatcherEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)  
  
- [<span data-ttu-id="2561b-117">ICorProfilerCallback:: Exceptionunwindfinallyenter (</span><span class="sxs-lookup"><span data-stu-id="2561b-117">ICorProfilerCallback::ExceptionUnwindFinallyEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)  
  
- [<span data-ttu-id="2561b-118">ICorProfilerCallback:: Exceptionsearchfilterenter (</span><span class="sxs-lookup"><span data-stu-id="2561b-118">ICorProfilerCallback::ExceptionSearchFilterEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)  
  
- [<span data-ttu-id="2561b-119">ICorProfilerCallback:: Exceptioncatcherleave (</span><span class="sxs-lookup"><span data-stu-id="2561b-119">ICorProfilerCallback::ExceptionCatcherLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)  
  
- [<span data-ttu-id="2561b-120">ICorProfilerCallback:: ExceptionUnwindFinallyLeave (</span><span class="sxs-lookup"><span data-stu-id="2561b-120">ICorProfilerCallback::ExceptionUnwindFinallyLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)  
  
- [<span data-ttu-id="2561b-121">ICorProfilerCallback:: Exceptionsearchfilterleave (</span><span class="sxs-lookup"><span data-stu-id="2561b-121">ICorProfilerCallback::ExceptionSearchFilterLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)  
  
## <a name="requirements"></a><span data-ttu-id="2561b-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2561b-122">Requirements</span></span>  
 <span data-ttu-id="2561b-123">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2561b-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2561b-124">**Encabezado:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="2561b-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="2561b-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2561b-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2561b-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2561b-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2561b-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="2561b-127">See also</span></span>

- [<span data-ttu-id="2561b-128">Estructuras para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="2561b-128">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
