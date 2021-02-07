---
description: 'Más información acerca de: enumeración COR_PRF_MISC'
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
ms.openlocfilehash: 037ea040dfdf9f5be48369ab4d8e94b12aea51ff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99687602"
---
# <a name="cor_prf_misc-enumeration"></a><span data-ttu-id="f0efe-103">COR_PRF_MISC (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="f0efe-103">COR_PRF_MISC Enumeration</span></span>

<span data-ttu-id="f0efe-104">Contiene valores constantes que especifican identificadores especiales.</span><span class="sxs-lookup"><span data-stu-id="f0efe-104">Contains constant values that specify special identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0efe-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f0efe-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    PROFILER_PARENT_UNKNOWN = 0xFFFFFFFD,  
    PROFILER_GLOBAL_CLASS   = 0xFFFFFFFE,  
    PROFILER_GLOBAL_MODULE  = 0xFFFFFFFF  
} COR_PRF_MISC;  
```  
  
## <a name="members"></a><span data-ttu-id="f0efe-106">Members</span><span class="sxs-lookup"><span data-stu-id="f0efe-106">Members</span></span>  
  
|<span data-ttu-id="f0efe-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="f0efe-107">Member</span></span>|<span data-ttu-id="f0efe-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="f0efe-108">Description</span></span>|  
|------------|-----------------|  
|`PROFILER_PARENT_UNKNOWN`|<span data-ttu-id="f0efe-109">Identificador predeterminado utilizado por [ICorProfilerInfo:: getmoduleinfo (](icorprofilerinfo-getmoduleinfo-method.md) para un módulo que todavía no se ha adjuntado a un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f0efe-109">The default identifier used by [ICorProfilerInfo::GetModuleInfo](icorprofilerinfo-getmoduleinfo-method.md) for a module that has not yet been attached to an assembly.</span></span>|  
|`PROFILER_GLOBAL_CLASS`|<span data-ttu-id="f0efe-110">Identificador de clase predeterminado para las constantes globales que no pertenecen a una clase.</span><span class="sxs-lookup"><span data-stu-id="f0efe-110">The default class identifier for global constants that do not belong to a class.</span></span>|  
|`PROFILER_GLOBAL_MODULE`|<span data-ttu-id="f0efe-111">Identificador de módulo predeterminado para los objetos globales que no pertenecen a un módulo.</span><span class="sxs-lookup"><span data-stu-id="f0efe-111">The default module identifier for global objects that do not belong to a module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f0efe-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f0efe-112">Requirements</span></span>  

 <span data-ttu-id="f0efe-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0efe-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0efe-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f0efe-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f0efe-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0efe-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0efe-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0efe-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0efe-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0efe-117">See also</span></span>

- [<span data-ttu-id="f0efe-118">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="f0efe-118">Profiling Enumerations</span></span>](profiling-enumerations.md)
