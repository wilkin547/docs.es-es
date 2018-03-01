---
title: "CorDebugJITCompilerFlags (Enumeración)"
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
- CorDebugJITCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugJITCompilerFlags
helpviewer_keywords:
- CorDebugJITCompilerFlags enumeration [.NET Framework debugging]
ms.assetid: c0774f70-5bed-45e8-9922-fdad778c4c33
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: dfb78a160a7a6b9f50174fc8bb177cfd8d3f9383
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugjitcompilerflags-enumeration"></a><span data-ttu-id="f8bd7-102">CorDebugJITCompilerFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="f8bd7-102">CorDebugJITCompilerFlags Enumeration</span></span>
<span data-ttu-id="f8bd7-103">Contiene valores que influyen en el comportamiento del compilador Just-In-Time (JIT) administrado.</span><span class="sxs-lookup"><span data-stu-id="f8bd7-103">Contains values that influence the behavior of the managed just-in-time (JIT) compiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8bd7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f8bd7-104">Syntax</span></span>  
  
```  
typedef enum CorDebugJITCompilerFlags {  
  
    CORDEBUG_JIT_DEFAULT = 0x1,  
    CORDEBUG_JIT_DISABLE_OPTIMIZATION = 0x3,  
    CORDEBUG_JIT_ENABLE_ENC = 0x7  
  
} CorDebugJITCompilerFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="f8bd7-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="f8bd7-105">Members</span></span>  
  
|<span data-ttu-id="f8bd7-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="f8bd7-106">Member</span></span>|<span data-ttu-id="f8bd7-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f8bd7-107">Description</span></span>|  
|------------|-----------------|  
|`CORDEBUG_JIT_DEFAULT`|<span data-ttu-id="f8bd7-108">Especifica que el compilador debe realizar un seguimiento de los datos de compilación y permite que las optimizaciones.</span><span class="sxs-lookup"><span data-stu-id="f8bd7-108">Specifies that the compiler should track compilation data, and allows optimizations.</span></span>|  
|`CORDEBUG_JIT_DISABLE_OPTIMIZATION`|<span data-ttu-id="f8bd7-109">Especifica que el compilador debe realizar el seguimiento de los datos de compilación, pero deshabilita las optimizaciones.</span><span class="sxs-lookup"><span data-stu-id="f8bd7-109">Specifies that the compiler should track compilation data, but disables optimizations.</span></span>|  
|`CORDEBUG_JIT_ENABLE_ENC`|<span data-ttu-id="f8bd7-110">Especifica que el compilador debe realizar el seguimiento de datos de compilación, deshabilita las optimizaciones, y permite editar y continuar tecnologías.</span><span class="sxs-lookup"><span data-stu-id="f8bd7-110">Specifies that the compiler should track compilation data, disables optimizations, and enables Edit and Continue technologies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f8bd7-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f8bd7-111">Requirements</span></span>  
 <span data-ttu-id="f8bd7-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8bd7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8bd7-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f8bd7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f8bd7-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8bd7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8bd7-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8bd7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8bd7-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8bd7-116">See Also</span></span>  
 [<span data-ttu-id="f8bd7-117">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="f8bd7-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
