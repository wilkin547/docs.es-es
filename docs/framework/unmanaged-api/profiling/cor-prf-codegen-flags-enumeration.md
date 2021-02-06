---
description: 'Más información acerca de: enumeración COR_PRF_CODEGEN_FLAGS'
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
ms.openlocfilehash: 40ddaa77047e0b1daa743b512f21ba7643127230
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649181"
---
# <a name="cor_prf_codegen_flags-enumeration"></a><span data-ttu-id="342f7-103">COR_PRF_CODEGEN_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="342f7-103">COR_PRF_CODEGEN_FLAGS Enumeration</span></span>

<span data-ttu-id="342f7-104">Define las marcas de generación de código que se pueden establecer con el método [ICorProfilerFunctionControl:: setcodegenflags (](icorprofilerfunctioncontrol-setcodegenflags-method.md) .</span><span class="sxs-lookup"><span data-stu-id="342f7-104">Defines the code generation flags that can be set with the [ICorProfilerFunctionControl::SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="342f7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="342f7-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_CODEGEN_DISABLE_INLINING =          0x0001,  
    COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS = 0x0002,  
} COR_PRF_CODEGEN_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="342f7-106">Members</span><span class="sxs-lookup"><span data-stu-id="342f7-106">Members</span></span>  
  
|<span data-ttu-id="342f7-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="342f7-107">Member</span></span>|<span data-ttu-id="342f7-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="342f7-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_CODEGEN_DISABLE_INLINING`|<span data-ttu-id="342f7-109">No se insertará ninguna función en el cuerpo de esta función.</span><span class="sxs-lookup"><span data-stu-id="342f7-109">No functions will be inlined into this function’s body.</span></span> <span data-ttu-id="342f7-110">Sin embargo, la propia función puede estar insertada en sus llamadores.</span><span class="sxs-lookup"><span data-stu-id="342f7-110">However, the function itself may be inlined into its callers.</span></span>|  
|`COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS`|<span data-ttu-id="342f7-111">Todas las optimizaciones se deshabilitarán para el cuerpo de esta función.</span><span class="sxs-lookup"><span data-stu-id="342f7-111">All optimizations will be disabled for this function’s body.</span></span> <span data-ttu-id="342f7-112">Sin embargo, la propia función todavía puede estar insertada en sus llamadores.</span><span class="sxs-lookup"><span data-stu-id="342f7-112">However, the function itself may still be inlined into its callers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="342f7-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="342f7-113">Remarks</span></span>  

 <span data-ttu-id="342f7-114">El `COR_PRF_CODEGEN_FLAGS` método [ICorProfilerFunctionControl:: setcodegenflags (](icorprofilerfunctioncontrol-setcodegenflags-method.md) usa la enumeración para permitir que el generador de perfiles controle la generación de código para la función recompilada JIT.</span><span class="sxs-lookup"><span data-stu-id="342f7-114">The `COR_PRF_CODEGEN_FLAGS` enumeration is used by the [ICorProfilerFunctionControl::SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) method to enable the profiler to control the code generation for the JIT-recompiled function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="342f7-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="342f7-115">Requirements</span></span>  

 <span data-ttu-id="342f7-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="342f7-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="342f7-117">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="342f7-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="342f7-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="342f7-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="342f7-119">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="342f7-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="342f7-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="342f7-120">See also</span></span>

- [<span data-ttu-id="342f7-121">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="342f7-121">Profiling Enumerations</span></span>](profiling-enumerations.md)
