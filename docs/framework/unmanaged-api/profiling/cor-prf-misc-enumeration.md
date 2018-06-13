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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c8f4cffd718fffa9145e1082092ecec45b80a2ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33451064"
---
# <a name="corprfmisc-enumeration"></a><span data-ttu-id="1e458-102">COR_PRF_MISC (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="1e458-102">COR_PRF_MISC Enumeration</span></span>
<span data-ttu-id="1e458-103">Contiene valores constantes que especifican identificadores especiales.</span><span class="sxs-lookup"><span data-stu-id="1e458-103">Contains constant values that specify special identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e458-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1e458-104">Syntax</span></span>  
  
```  
typedef enum {  
    PROFILER_PARENT_UNKNOWN = 0xFFFFFFFD,  
    PROFILER_GLOBAL_CLASS   = 0xFFFFFFFE,  
    PROFILER_GLOBAL_MODULE  = 0xFFFFFFFF  
} COR_PRF_MISC;  
```  
  
## <a name="members"></a><span data-ttu-id="1e458-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="1e458-105">Members</span></span>  
  
|<span data-ttu-id="1e458-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="1e458-106">Member</span></span>|<span data-ttu-id="1e458-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="1e458-107">Description</span></span>|  
|------------|-----------------|  
|`PROFILER_PARENT_UNKNOWN`|<span data-ttu-id="1e458-108">El identificador predeterminado utilizado por [ICorProfilerInfo:: GetModuleInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md) para un módulo que aún no se ha adjuntado a un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1e458-108">The default identifier used by [ICorProfilerInfo::GetModuleInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md) for a module that has not yet been attached to an assembly.</span></span>|  
|`PROFILER_GLOBAL_CLASS`|<span data-ttu-id="1e458-109">El identificador de clase predeterminado para las constantes globales que no pertenecen a una clase.</span><span class="sxs-lookup"><span data-stu-id="1e458-109">The default class identifier for global constants that do not belong to a class.</span></span>|  
|`PROFILER_GLOBAL_MODULE`|<span data-ttu-id="1e458-110">Identificador del módulo predeterminado para los objetos globales que no pertenecen a un módulo.</span><span class="sxs-lookup"><span data-stu-id="1e458-110">The default module identifier for global objects that do not belong to a module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1e458-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1e458-111">Requirements</span></span>  
 <span data-ttu-id="1e458-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e458-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e458-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1e458-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1e458-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1e458-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1e458-115">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e458-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e458-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e458-116">See Also</span></span>  
 [<span data-ttu-id="1e458-117">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="1e458-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
