---
title: COR_PRF_MISC (Enumeración)
ms.date: 03/30/2017
api_name:
- COR_PRF_MISC
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_MISC
helpviewer_keywords:
- COR_PRF_MISC enumeration [.NET Framework profiling]
ms.assetid: 619bb5de-e309-48b6-a3af-32d935a0ff46
topic_type:
- apiref
ms.openlocfilehash: fe27c0fca6d38b4cff6cac2b9778cf2be68903a3
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867131"
---
# <a name="cor_prf_misc-enumeration"></a><span data-ttu-id="d44ef-102">COR_PRF_MISC (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="d44ef-102">COR_PRF_MISC Enumeration</span></span>
<span data-ttu-id="d44ef-103">Contiene valores constantes que especifican identificadores especiales.</span><span class="sxs-lookup"><span data-stu-id="d44ef-103">Contains constant values that specify special identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d44ef-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d44ef-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    PROFILER_PARENT_UNKNOWN = 0xFFFFFFFD,  
    PROFILER_GLOBAL_CLASS   = 0xFFFFFFFE,  
    PROFILER_GLOBAL_MODULE  = 0xFFFFFFFF  
} COR_PRF_MISC;  
```  
  
## <a name="members"></a><span data-ttu-id="d44ef-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="d44ef-105">Members</span></span>  
  
|<span data-ttu-id="d44ef-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="d44ef-106">Member</span></span>|<span data-ttu-id="d44ef-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d44ef-107">Description</span></span>|  
|------------|-----------------|  
|`PROFILER_PARENT_UNKNOWN`|<span data-ttu-id="d44ef-108">Identificador predeterminado utilizado por [ICorProfilerInfo:: getmoduleinfo (](icorprofilerinfo-getmoduleinfo-method.md) para un módulo que todavía no se ha adjuntado a un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d44ef-108">The default identifier used by [ICorProfilerInfo::GetModuleInfo](icorprofilerinfo-getmoduleinfo-method.md) for a module that has not yet been attached to an assembly.</span></span>|  
|`PROFILER_GLOBAL_CLASS`|<span data-ttu-id="d44ef-109">Identificador de clase predeterminado para las constantes globales que no pertenecen a una clase.</span><span class="sxs-lookup"><span data-stu-id="d44ef-109">The default class identifier for global constants that do not belong to a class.</span></span>|  
|`PROFILER_GLOBAL_MODULE`|<span data-ttu-id="d44ef-110">Identificador de módulo predeterminado para los objetos globales que no pertenecen a un módulo.</span><span class="sxs-lookup"><span data-stu-id="d44ef-110">The default module identifier for global objects that do not belong to a module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d44ef-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="d44ef-111">Requirements</span></span>  
 <span data-ttu-id="d44ef-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d44ef-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d44ef-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d44ef-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d44ef-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d44ef-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d44ef-115">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d44ef-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d44ef-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="d44ef-116">See also</span></span>

- [<span data-ttu-id="d44ef-117">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="d44ef-117">Profiling Enumerations</span></span>](profiling-enumerations.md)
