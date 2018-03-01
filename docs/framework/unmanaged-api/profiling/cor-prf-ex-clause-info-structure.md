---
title: COR_PRF_EX_CLAUSE_INFO (Estructura)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 65025384aa94ac363336bae7f37f8ea88a3bab67
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="corprfexclauseinfo-structure"></a><span data-ttu-id="327d6-102">COR_PRF_EX_CLAUSE_INFO (Estructura)</span><span class="sxs-lookup"><span data-stu-id="327d6-102">COR_PRF_EX_CLAUSE_INFO Structure</span></span>
<span data-ttu-id="327d6-103">Almacena información sobre una instancia específica de cláusula de excepción y su marco asociado.</span><span class="sxs-lookup"><span data-stu-id="327d6-103">Stores information about a specific exception clause instance and its associated frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="327d6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="327d6-104">Syntax</span></span>  
  
```  
typedef struct COR_PRF_EX_CLAUSE_INFO {  
    COR_PRF_CLAUSE_TYPE clauseType;  
    UINT_PTR programCounter;  
    UINT_PTR framePointer;  
    UINT_PTR shadowStackPointer;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="327d6-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="327d6-105">Members</span></span>  
  
|<span data-ttu-id="327d6-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="327d6-106">Member</span></span>|<span data-ttu-id="327d6-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="327d6-107">Description</span></span>|  
|------------|-----------------|  
|`clauseType`|<span data-ttu-id="327d6-108">Un valor de la [COR_PRF_CLAUSE_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md) enumeración que especifica el tipo de cláusula de excepción el código que acaba de escribir o a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="327d6-108">A value of the [COR_PRF_CLAUSE_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md) enumeration that specifies the type of exception clause the code just entered or left.</span></span>|  
|`programCounter`|<span data-ttu-id="327d6-109">El punto de entrada nativo del controlador de cláusula, por ejemplo, el contenido del registro X86 EIP.</span><span class="sxs-lookup"><span data-stu-id="327d6-109">The native entry point of the clause handler — for example, the contents of the X86 EIP register.</span></span>|  
|`framePointer`|<span data-ttu-id="327d6-110">El puntero al marco lógico del controlador de cláusula, por ejemplo, el contenido del registro X86 EBP.</span><span class="sxs-lookup"><span data-stu-id="327d6-110">The pointer to the logical frame for the clause handler — for example, the contents of the X86 EBP register.</span></span>|  
|`shadowStackPointer`|<span data-ttu-id="327d6-111">El puntero a la pila sombra.</span><span class="sxs-lookup"><span data-stu-id="327d6-111">The pointer to the shadow stack.</span></span> <span data-ttu-id="327d6-112">Este valor es el contenido del registro BSP y sólo se aplica a IA64.</span><span class="sxs-lookup"><span data-stu-id="327d6-112">This value is the contents of the BSP register and applies only to IA64.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="327d6-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="327d6-113">Remarks</span></span>  
 <span data-ttu-id="327d6-114">Cuando se recibe una notificación de excepción, [ICorProfilerInfo2:: GetNotifiedExceptionClauseInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) puede utilizarse para obtener la información de dirección y el marco nativo para la cláusula de excepción (`catch` / `finally`/filtro) que se va a ejecutarse o recientemente ejecutado.</span><span class="sxs-lookup"><span data-stu-id="327d6-114">When an exception notification is received, [ICorProfilerInfo2::GetNotifiedExceptionClauseInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) can be used to get the native address and frame information for the exception clause (`catch`/`finally`/filter) that is about to be run or has just been run.</span></span>  
  
 <span data-ttu-id="327d6-115">Ejecución de una cláusula de excepción implica estas devoluciones de llamada de common language runtime (CLR):</span><span class="sxs-lookup"><span data-stu-id="327d6-115">Execution of an exception clause involves these callbacks from the common language runtime (CLR):</span></span>  
  
-   [<span data-ttu-id="327d6-116">ICorProfilerCallback:: ExceptionCatcherEnter</span><span class="sxs-lookup"><span data-stu-id="327d6-116">ICorProfilerCallback::ExceptionCatcherEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)  
  
-   [<span data-ttu-id="327d6-117">ICorProfilerCallback:: ExceptionUnwindFinallyEnter</span><span class="sxs-lookup"><span data-stu-id="327d6-117">ICorProfilerCallback::ExceptionUnwindFinallyEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)  
  
-   [<span data-ttu-id="327d6-118">ICorProfilerCallback:: ExceptionSearchFilterEnter</span><span class="sxs-lookup"><span data-stu-id="327d6-118">ICorProfilerCallback::ExceptionSearchFilterEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)  
  
-   [<span data-ttu-id="327d6-119">ICorProfilerCallback:: ExceptionCatcherLeave</span><span class="sxs-lookup"><span data-stu-id="327d6-119">ICorProfilerCallback::ExceptionCatcherLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)  
  
-   [<span data-ttu-id="327d6-120">ICorProfilerCallback:: ExceptionUnwindFinallyLeave</span><span class="sxs-lookup"><span data-stu-id="327d6-120">ICorProfilerCallback::ExceptionUnwindFinallyLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)  
  
-   [<span data-ttu-id="327d6-121">ICorProfilerCallback:: ExceptionSearchFilterLeave</span><span class="sxs-lookup"><span data-stu-id="327d6-121">ICorProfilerCallback::ExceptionSearchFilterLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)  
  
## <a name="requirements"></a><span data-ttu-id="327d6-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="327d6-122">Requirements</span></span>  
 <span data-ttu-id="327d6-123">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="327d6-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="327d6-124">**Encabezado:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="327d6-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="327d6-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="327d6-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="327d6-126">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="327d6-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="327d6-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="327d6-127">See Also</span></span>  
 [<span data-ttu-id="327d6-128">Estructuras para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="327d6-128">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
