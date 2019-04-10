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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 321318b63368ed6e57d235cf97d94485352f8686
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211366"
---
# <a name="corprfcodegenflags-enumeration"></a><span data-ttu-id="09fe0-102">COR_PRF_CODEGEN_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="09fe0-102">COR_PRF_CODEGEN_FLAGS Enumeration</span></span>
<span data-ttu-id="09fe0-103">Define las marcas de generación de código que se pueden establecer con el [Icorprofilerfunctioncontrol](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="09fe0-103">Defines the code generation flags that can be set with the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09fe0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="09fe0-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_CODEGEN_DISABLE_INLINING =          0x0001,  
    COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS = 0x0002,  
} COR_PRF_CODEGEN_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="09fe0-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="09fe0-105">Members</span></span>  
  
|<span data-ttu-id="09fe0-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="09fe0-106">Member</span></span>|<span data-ttu-id="09fe0-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="09fe0-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_CODEGEN_DISABLE_INLINING`|<span data-ttu-id="09fe0-108">No hay ninguna función insertarse en el cuerpo de la función.</span><span class="sxs-lookup"><span data-stu-id="09fe0-108">No functions will be inlined into this function’s body.</span></span> <span data-ttu-id="09fe0-109">Sin embargo, la función en sí se puede insertar en sus llamadores.</span><span class="sxs-lookup"><span data-stu-id="09fe0-109">However, the function itself may be inlined into its callers.</span></span>|  
|`COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS`|<span data-ttu-id="09fe0-110">Todas las optimizaciones se deshabilitará para el cuerpo de la función.</span><span class="sxs-lookup"><span data-stu-id="09fe0-110">All optimizations will be disabled for this function’s body.</span></span> <span data-ttu-id="09fe0-111">Sin embargo, la propia función puede seguir siendo insertada en sus llamadores.</span><span class="sxs-lookup"><span data-stu-id="09fe0-111">However, the function itself may still be inlined into its callers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09fe0-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="09fe0-112">Remarks</span></span>  
 <span data-ttu-id="09fe0-113">El `COR_PRF_CODEGEN_FLAGS` enumeración la utiliza el [Icorprofilerfunctioncontrol](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) método para habilitar el generador de perfiles controlar la generación de código para la función recompilada con JIT.</span><span class="sxs-lookup"><span data-stu-id="09fe0-113">The `COR_PRF_CODEGEN_FLAGS` enumeration is used by the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) method to enable the profiler to control the code generation for the JIT-recompiled function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09fe0-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="09fe0-114">Requirements</span></span>  
 <span data-ttu-id="09fe0-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09fe0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09fe0-116">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="09fe0-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="09fe0-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09fe0-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="09fe0-118">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="09fe0-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="09fe0-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="09fe0-119">See also</span></span>

- [<span data-ttu-id="09fe0-120">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="09fe0-120">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
