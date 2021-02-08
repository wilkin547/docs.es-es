---
description: 'Más información sobre: enumeración Cordebugjitcompilerflags ('
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
ms.openlocfilehash: 7e5337293aa4fe446deb12653acd22864eb7679a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801610"
---
# <a name="cordebugjitcompilerflags-enumeration"></a><span data-ttu-id="9a0dd-103">CorDebugJITCompilerFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="9a0dd-103">CorDebugJITCompilerFlags Enumeration</span></span>

<span data-ttu-id="9a0dd-104">Contiene valores que influyen en el comportamiento del compilador Just-In-Time (JIT) administrado.</span><span class="sxs-lookup"><span data-stu-id="9a0dd-104">Contains values that influence the behavior of the managed just-in-time (JIT) compiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a0dd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9a0dd-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugJITCompilerFlags {  
  
    CORDEBUG_JIT_DEFAULT = 0x1,  
    CORDEBUG_JIT_DISABLE_OPTIMIZATION = 0x3,  
    CORDEBUG_JIT_ENABLE_ENC = 0x7  
  
} CorDebugJITCompilerFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="9a0dd-106">Members</span><span class="sxs-lookup"><span data-stu-id="9a0dd-106">Members</span></span>  
  
|<span data-ttu-id="9a0dd-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="9a0dd-107">Member</span></span>|<span data-ttu-id="9a0dd-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="9a0dd-108">Description</span></span>|  
|------------|-----------------|  
|`CORDEBUG_JIT_DEFAULT`|<span data-ttu-id="9a0dd-109">Especifica que el compilador debe realizar el seguimiento de los datos de compilación y permite las optimizaciones.</span><span class="sxs-lookup"><span data-stu-id="9a0dd-109">Specifies that the compiler should track compilation data, and allows optimizations.</span></span>|  
|`CORDEBUG_JIT_DISABLE_OPTIMIZATION`|<span data-ttu-id="9a0dd-110">Especifica que el compilador debe realizar el seguimiento de los datos de compilación, pero deshabilita las optimizaciones.</span><span class="sxs-lookup"><span data-stu-id="9a0dd-110">Specifies that the compiler should track compilation data, but disables optimizations.</span></span>|  
|`CORDEBUG_JIT_ENABLE_ENC`|<span data-ttu-id="9a0dd-111">Especifica que el compilador debe realizar el seguimiento de los datos de compilación, deshabilita las optimizaciones y habilita las tecnologías editar y continuar.</span><span class="sxs-lookup"><span data-stu-id="9a0dd-111">Specifies that the compiler should track compilation data, disables optimizations, and enables Edit and Continue technologies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9a0dd-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9a0dd-112">Requirements</span></span>  

 <span data-ttu-id="9a0dd-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a0dd-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a0dd-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a0dd-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a0dd-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a0dd-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a0dd-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a0dd-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a0dd-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a0dd-117">See also</span></span>

- [<span data-ttu-id="9a0dd-118">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="9a0dd-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
