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
ms.openlocfilehash: 3b40ac5f49288f7b30018e0c8c727e3ce6b73ae8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199497"
---
# <a name="corprfmisc-enumeration"></a><span data-ttu-id="ec65b-102">COR_PRF_MISC (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="ec65b-102">COR_PRF_MISC Enumeration</span></span>
<span data-ttu-id="ec65b-103">Contiene valores constantes que especifican identificadores especiales.</span><span class="sxs-lookup"><span data-stu-id="ec65b-103">Contains constant values that specify special identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec65b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ec65b-104">Syntax</span></span>  
  
```  
typedef enum {  
    PROFILER_PARENT_UNKNOWN = 0xFFFFFFFD,  
    PROFILER_GLOBAL_CLASS   = 0xFFFFFFFE,  
    PROFILER_GLOBAL_MODULE  = 0xFFFFFFFF  
} COR_PRF_MISC;  
```  
  
## <a name="members"></a><span data-ttu-id="ec65b-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="ec65b-105">Members</span></span>  
  
|<span data-ttu-id="ec65b-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="ec65b-106">Member</span></span>|<span data-ttu-id="ec65b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec65b-107">Description</span></span>|  
|------------|-----------------|  
|`PROFILER_PARENT_UNKNOWN`|<span data-ttu-id="ec65b-108">El identificador predeterminado utilizado por [GetModuleInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md) para un módulo que todavía no se ha asociado a un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ec65b-108">The default identifier used by [ICorProfilerInfo::GetModuleInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md) for a module that has not yet been attached to an assembly.</span></span>|  
|`PROFILER_GLOBAL_CLASS`|<span data-ttu-id="ec65b-109">El identificador de clase predeterminada para las constantes globales que no pertenecen a una clase.</span><span class="sxs-lookup"><span data-stu-id="ec65b-109">The default class identifier for global constants that do not belong to a class.</span></span>|  
|`PROFILER_GLOBAL_MODULE`|<span data-ttu-id="ec65b-110">El identificador de módulo predeterminado para los objetos globales que no pertenecen a un módulo.</span><span class="sxs-lookup"><span data-stu-id="ec65b-110">The default module identifier for global objects that do not belong to a module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ec65b-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ec65b-111">Requirements</span></span>  
 <span data-ttu-id="ec65b-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec65b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec65b-113">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ec65b-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ec65b-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec65b-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="ec65b-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ec65b-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ec65b-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec65b-116">See also</span></span>

- [<span data-ttu-id="ec65b-117">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="ec65b-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
