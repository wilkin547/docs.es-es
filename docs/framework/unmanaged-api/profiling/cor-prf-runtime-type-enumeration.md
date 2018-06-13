---
title: COR_PRF_RUNTIME_TYPE (Enumeración)
ms.date: 03/30/2017
api_name:
- COR_PRF_RUNTIME_TYPE Enumeration
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_RUNTIME_TYPE
helpviewer_keywords:
- COR_PRF_RUNTIME_TYPE enumeration [.NET Framework profiling]
ms.assetid: 35449514-333f-4918-9c60-7aa198d655d2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 28e6e95bbcca35ad39f30adcf100519748c02838
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450003"
---
# <a name="corprfruntimetype-enumeration"></a><span data-ttu-id="57a88-102">COR_PRF_RUNTIME_TYPE (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="57a88-102">COR_PRF_RUNTIME_TYPE Enumeration</span></span>
<span data-ttu-id="57a88-103">Contiene valores que indican la versión de common language runtime (CLR): escritorio o CoreCLR, que se usa en Silverlight.</span><span class="sxs-lookup"><span data-stu-id="57a88-103">Contains values that indicate the version of the common language runtime (CLR): desktop or CoreCLR, which is used in Silverlight.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57a88-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="57a88-104">Syntax</span></span>  
  
```  
typedef enum  
{  
    COR_PRF_DESKTOP_CLR = 0x1,  
    COR_PRF_CORE_CLR    = 0x2,  
} COR_PRF_RUNTIME_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="57a88-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="57a88-105">Members</span></span>  
  
|<span data-ttu-id="57a88-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="57a88-106">Member</span></span>|<span data-ttu-id="57a88-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="57a88-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_DESKTOP_CLR`|<span data-ttu-id="57a88-108">La versión de escritorio de CLR.</span><span class="sxs-lookup"><span data-stu-id="57a88-108">The desktop version of the CLR.</span></span>|  
|`COR_PRF_CORE_CLR`|<span data-ttu-id="57a88-109">La versión principal de CLR, que se usa en Silverlight.</span><span class="sxs-lookup"><span data-stu-id="57a88-109">The core version of the CLR, used in Silverlight.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="57a88-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="57a88-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57a88-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="57a88-111">Requirements</span></span>  
 <span data-ttu-id="57a88-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57a88-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57a88-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="57a88-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="57a88-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="57a88-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="57a88-115">**Versiones de .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57a88-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57a88-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="57a88-116">See Also</span></span>  
 [<span data-ttu-id="57a88-117">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="57a88-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
