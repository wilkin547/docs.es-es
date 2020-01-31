---
title: CorDebugJITCompilerFlags (Enumeración)
ms.date: 03/30/2017
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
ms.openlocfilehash: 65d7e830b82cc1780826517fe8cff1da0a7d6188
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793891"
---
# <a name="cordebugjitcompilerflags-enumeration"></a><span data-ttu-id="545f1-102">CorDebugJITCompilerFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="545f1-102">CorDebugJITCompilerFlags Enumeration</span></span>
<span data-ttu-id="545f1-103">Contiene valores que influyen en el comportamiento del compilador Just-In-Time (JIT) administrado.</span><span class="sxs-lookup"><span data-stu-id="545f1-103">Contains values that influence the behavior of the managed just-in-time (JIT) compiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="545f1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="545f1-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugJITCompilerFlags {  
  
    CORDEBUG_JIT_DEFAULT = 0x1,  
    CORDEBUG_JIT_DISABLE_OPTIMIZATION = 0x3,  
    CORDEBUG_JIT_ENABLE_ENC = 0x7  
  
} CorDebugJITCompilerFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="545f1-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="545f1-105">Members</span></span>  
  
|<span data-ttu-id="545f1-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="545f1-106">Member</span></span>|<span data-ttu-id="545f1-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="545f1-107">Description</span></span>|  
|------------|-----------------|  
|`CORDEBUG_JIT_DEFAULT`|<span data-ttu-id="545f1-108">Especifica que el compilador debe realizar el seguimiento de los datos de compilación y permite las optimizaciones.</span><span class="sxs-lookup"><span data-stu-id="545f1-108">Specifies that the compiler should track compilation data, and allows optimizations.</span></span>|  
|`CORDEBUG_JIT_DISABLE_OPTIMIZATION`|<span data-ttu-id="545f1-109">Especifica que el compilador debe realizar el seguimiento de los datos de compilación, pero deshabilita las optimizaciones.</span><span class="sxs-lookup"><span data-stu-id="545f1-109">Specifies that the compiler should track compilation data, but disables optimizations.</span></span>|  
|`CORDEBUG_JIT_ENABLE_ENC`|<span data-ttu-id="545f1-110">Especifica que el compilador debe realizar el seguimiento de los datos de compilación, deshabilita las optimizaciones y habilita las tecnologías editar y continuar.</span><span class="sxs-lookup"><span data-stu-id="545f1-110">Specifies that the compiler should track compilation data, disables optimizations, and enables Edit and Continue technologies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="545f1-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="545f1-111">Requirements</span></span>  
 <span data-ttu-id="545f1-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="545f1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="545f1-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="545f1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="545f1-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="545f1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="545f1-115">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="545f1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="545f1-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="545f1-116">See also</span></span>

- [<span data-ttu-id="545f1-117">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="545f1-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
