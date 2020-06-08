---
title: COR_PRF_CODEGEN_FLAGS (Enumeración)
ms.date: 03/30/2017
api_name:
- COR_PRF_CODEGEN_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_CODEGEN_FLAGS
helpviewer_keywords:
- COR_PRF_CODEGEN_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 3e184022-0247-4824-a23d-6b29593d8d01
topic_type:
- apiref
ms.openlocfilehash: c2c7ae7a8930949c79b5e24e2da75f3b4649e7f6
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500993"
---
# <a name="cor_prf_codegen_flags-enumeration"></a><span data-ttu-id="c1fe2-102">COR_PRF_CODEGEN_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="c1fe2-102">COR_PRF_CODEGEN_FLAGS Enumeration</span></span>
<span data-ttu-id="c1fe2-103">Define las marcas de generación de código que se pueden establecer con el método [ICorProfilerFunctionControl:: setcodegenflags (](icorprofilerfunctioncontrol-setcodegenflags-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c1fe2-103">Defines the code generation flags that can be set with the [ICorProfilerFunctionControl::SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1fe2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c1fe2-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_CODEGEN_DISABLE_INLINING =          0x0001,  
    COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS = 0x0002,  
} COR_PRF_CODEGEN_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="c1fe2-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="c1fe2-105">Members</span></span>  
  
|<span data-ttu-id="c1fe2-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="c1fe2-106">Member</span></span>|<span data-ttu-id="c1fe2-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c1fe2-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_CODEGEN_DISABLE_INLINING`|<span data-ttu-id="c1fe2-108">No se insertará ninguna función en el cuerpo de esta función.</span><span class="sxs-lookup"><span data-stu-id="c1fe2-108">No functions will be inlined into this function’s body.</span></span> <span data-ttu-id="c1fe2-109">Sin embargo, la propia función puede estar insertada en sus llamadores.</span><span class="sxs-lookup"><span data-stu-id="c1fe2-109">However, the function itself may be inlined into its callers.</span></span>|  
|`COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS`|<span data-ttu-id="c1fe2-110">Todas las optimizaciones se deshabilitarán para el cuerpo de esta función.</span><span class="sxs-lookup"><span data-stu-id="c1fe2-110">All optimizations will be disabled for this function’s body.</span></span> <span data-ttu-id="c1fe2-111">Sin embargo, la propia función todavía puede estar insertada en sus llamadores.</span><span class="sxs-lookup"><span data-stu-id="c1fe2-111">However, the function itself may still be inlined into its callers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1fe2-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c1fe2-112">Remarks</span></span>  
 <span data-ttu-id="c1fe2-113">El `COR_PRF_CODEGEN_FLAGS` método [ICorProfilerFunctionControl:: setcodegenflags (](icorprofilerfunctioncontrol-setcodegenflags-method.md) usa la enumeración para permitir que el generador de perfiles controle la generación de código para la función recompilada JIT.</span><span class="sxs-lookup"><span data-stu-id="c1fe2-113">The `COR_PRF_CODEGEN_FLAGS` enumeration is used by the [ICorProfilerFunctionControl::SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) method to enable the profiler to control the code generation for the JIT-recompiled function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1fe2-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c1fe2-114">Requirements</span></span>  
 <span data-ttu-id="c1fe2-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1fe2-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1fe2-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c1fe2-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c1fe2-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c1fe2-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c1fe2-118">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1fe2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1fe2-119">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="c1fe2-119">See also</span></span>

- [<span data-ttu-id="c1fe2-120">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="c1fe2-120">Profiling Enumerations</span></span>](profiling-enumerations.md)
