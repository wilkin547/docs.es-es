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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5e12410ab9886055dca8c3f9103c1e56475c2d5e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59140353"
---
# <a name="corprfexclauseinfo-structure"></a><span data-ttu-id="de4dd-102">COR_PRF_EX_CLAUSE_INFO (Estructura)</span><span class="sxs-lookup"><span data-stu-id="de4dd-102">COR_PRF_EX_CLAUSE_INFO Structure</span></span>
<span data-ttu-id="de4dd-103">Almacena información sobre una instancia específica de cláusula de excepción y su marco asociado.</span><span class="sxs-lookup"><span data-stu-id="de4dd-103">Stores information about a specific exception clause instance and its associated frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de4dd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="de4dd-104">Syntax</span></span>  
  
```  
typedef struct COR_PRF_EX_CLAUSE_INFO {  
    COR_PRF_CLAUSE_TYPE clauseType;  
    UINT_PTR programCounter;  
    UINT_PTR framePointer;  
    UINT_PTR shadowStackPointer;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="de4dd-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="de4dd-105">Members</span></span>  
  
|<span data-ttu-id="de4dd-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="de4dd-106">Member</span></span>|<span data-ttu-id="de4dd-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="de4dd-107">Description</span></span>|  
|------------|-----------------|  
|`clauseType`|<span data-ttu-id="de4dd-108">Un valor de la [COR_PRF_CLAUSE_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md) enumeración que especifica el tipo de cláusula de excepción del código que acaba de escribir o a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="de4dd-108">A value of the [COR_PRF_CLAUSE_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md) enumeration that specifies the type of exception clause the code just entered or left.</span></span>|  
|`programCounter`|<span data-ttu-id="de4dd-109">El punto de entrada nativo del controlador de cláusula, por ejemplo, el contenido del registro X86 EIP.</span><span class="sxs-lookup"><span data-stu-id="de4dd-109">The native entry point of the clause handler — for example, the contents of the X86 EIP register.</span></span>|  
|`framePointer`|<span data-ttu-id="de4dd-110">El puntero al marco lógico para el controlador de la cláusula — por ejemplo, el contenido del registro X86 EBP.</span><span class="sxs-lookup"><span data-stu-id="de4dd-110">The pointer to the logical frame for the clause handler — for example, the contents of the X86 EBP register.</span></span>|  
|`shadowStackPointer`|<span data-ttu-id="de4dd-111">Puntero a la pila de sombra.</span><span class="sxs-lookup"><span data-stu-id="de4dd-111">The pointer to the shadow stack.</span></span> <span data-ttu-id="de4dd-112">Este valor es el contenido del registro BSP y solo se aplica a IA64.</span><span class="sxs-lookup"><span data-stu-id="de4dd-112">This value is the contents of the BSP register and applies only to IA64.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de4dd-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="de4dd-113">Remarks</span></span>  
 <span data-ttu-id="de4dd-114">Cuando se recibe una notificación de excepción, [ICorProfilerInfo2:: GetNotifiedExceptionClauseInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) puede usarse para obtener la información de dirección y el marco nativa para la cláusula de excepción (`catch` / `finally`/datos de filtro) que se va a ejecutarse o que recientemente se ha ejecutado.</span><span class="sxs-lookup"><span data-stu-id="de4dd-114">When an exception notification is received, [ICorProfilerInfo2::GetNotifiedExceptionClauseInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) can be used to get the native address and frame information for the exception clause (`catch`/`finally`/filter) that is about to be run or has just been run.</span></span>  
  
 <span data-ttu-id="de4dd-115">Ejecución de una cláusula de excepción implica estas devoluciones de llamada de common language runtime (CLR):</span><span class="sxs-lookup"><span data-stu-id="de4dd-115">Execution of an exception clause involves these callbacks from the common language runtime (CLR):</span></span>  
  
-   [<span data-ttu-id="de4dd-116">ICorProfilerCallback::ExceptionCatcherEnter</span><span class="sxs-lookup"><span data-stu-id="de4dd-116">ICorProfilerCallback::ExceptionCatcherEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)  
  
-   [<span data-ttu-id="de4dd-117">ICorProfilerCallback::ExceptionUnwindFinallyEnter</span><span class="sxs-lookup"><span data-stu-id="de4dd-117">ICorProfilerCallback::ExceptionUnwindFinallyEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)  
  
-   [<span data-ttu-id="de4dd-118">ICorProfilerCallback::ExceptionSearchFilterEnter</span><span class="sxs-lookup"><span data-stu-id="de4dd-118">ICorProfilerCallback::ExceptionSearchFilterEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)  
  
-   [<span data-ttu-id="de4dd-119">ICorProfilerCallback::ExceptionCatcherLeave</span><span class="sxs-lookup"><span data-stu-id="de4dd-119">ICorProfilerCallback::ExceptionCatcherLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)  
  
-   [<span data-ttu-id="de4dd-120">ICorProfilerCallback::ExceptionUnwindFinallyLeave</span><span class="sxs-lookup"><span data-stu-id="de4dd-120">ICorProfilerCallback::ExceptionUnwindFinallyLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)  
  
-   [<span data-ttu-id="de4dd-121">ICorProfilerCallback::ExceptionSearchFilterLeave</span><span class="sxs-lookup"><span data-stu-id="de4dd-121">ICorProfilerCallback::ExceptionSearchFilterLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)  
  
## <a name="requirements"></a><span data-ttu-id="de4dd-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="de4dd-122">Requirements</span></span>  
 <span data-ttu-id="de4dd-123">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de4dd-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de4dd-124">**Encabezado**: CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="de4dd-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="de4dd-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de4dd-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de4dd-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de4dd-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de4dd-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="de4dd-127">See also</span></span>

- [<span data-ttu-id="de4dd-128">Estructuras para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="de4dd-128">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
