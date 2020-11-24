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
ms.openlocfilehash: 5a3c820b52ae9376d769ea9956edc0b8553a1f88
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682177"
---
# <a name="cor_prf_misc-enumeration"></a><span data-ttu-id="50ea5-102">COR_PRF_MISC (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="50ea5-102">COR_PRF_MISC Enumeration</span></span>

<span data-ttu-id="50ea5-103">Contiene valores constantes que especifican identificadores especiales.</span><span class="sxs-lookup"><span data-stu-id="50ea5-103">Contains constant values that specify special identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50ea5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="50ea5-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    PROFILER_PARENT_UNKNOWN = 0xFFFFFFFD,  
    PROFILER_GLOBAL_CLASS   = 0xFFFFFFFE,  
    PROFILER_GLOBAL_MODULE  = 0xFFFFFFFF  
} COR_PRF_MISC;  
```  
  
## <a name="members"></a><span data-ttu-id="50ea5-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="50ea5-105">Members</span></span>  
  
|<span data-ttu-id="50ea5-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="50ea5-106">Member</span></span>|<span data-ttu-id="50ea5-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="50ea5-107">Description</span></span>|  
|------------|-----------------|  
|`PROFILER_PARENT_UNKNOWN`|<span data-ttu-id="50ea5-108">Identificador predeterminado utilizado por [ICorProfilerInfo:: getmoduleinfo (](icorprofilerinfo-getmoduleinfo-method.md) para un módulo que todavía no se ha adjuntado a un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="50ea5-108">The default identifier used by [ICorProfilerInfo::GetModuleInfo](icorprofilerinfo-getmoduleinfo-method.md) for a module that has not yet been attached to an assembly.</span></span>|  
|`PROFILER_GLOBAL_CLASS`|<span data-ttu-id="50ea5-109">Identificador de clase predeterminado para las constantes globales que no pertenecen a una clase.</span><span class="sxs-lookup"><span data-stu-id="50ea5-109">The default class identifier for global constants that do not belong to a class.</span></span>|  
|`PROFILER_GLOBAL_MODULE`|<span data-ttu-id="50ea5-110">Identificador de módulo predeterminado para los objetos globales que no pertenecen a un módulo.</span><span class="sxs-lookup"><span data-stu-id="50ea5-110">The default module identifier for global objects that do not belong to a module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="50ea5-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="50ea5-111">Requirements</span></span>  

 <span data-ttu-id="50ea5-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50ea5-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50ea5-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="50ea5-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="50ea5-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50ea5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50ea5-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50ea5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50ea5-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="50ea5-116">See also</span></span>

- [<span data-ttu-id="50ea5-117">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="50ea5-117">Profiling Enumerations</span></span>](profiling-enumerations.md)
