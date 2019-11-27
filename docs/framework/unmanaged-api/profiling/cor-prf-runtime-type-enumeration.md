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
ms.openlocfilehash: 26948261c571dbe963811e8e9631551685a63bdb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450375"
---
# <a name="cor_prf_runtime_type-enumeration"></a><span data-ttu-id="9c722-102">COR_PRF_RUNTIME_TYPE (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="9c722-102">COR_PRF_RUNTIME_TYPE Enumeration</span></span>
<span data-ttu-id="9c722-103">Contiene valores que indican la versión de Common Language Runtime (CLR): Desktop o CoreCLR, que se usa en Silverlight.</span><span class="sxs-lookup"><span data-stu-id="9c722-103">Contains values that indicate the version of the common language runtime (CLR): desktop or CoreCLR, which is used in Silverlight.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c722-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9c722-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{  
    COR_PRF_DESKTOP_CLR = 0x1,  
    COR_PRF_CORE_CLR    = 0x2,  
} COR_PRF_RUNTIME_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="9c722-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="9c722-105">Members</span></span>  
  
|<span data-ttu-id="9c722-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="9c722-106">Member</span></span>|<span data-ttu-id="9c722-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9c722-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_DESKTOP_CLR`|<span data-ttu-id="9c722-108">Versión de escritorio de CLR.</span><span class="sxs-lookup"><span data-stu-id="9c722-108">The desktop version of the CLR.</span></span>|  
|`COR_PRF_CORE_CLR`|<span data-ttu-id="9c722-109">Versión básica de CLR, que se usa en Silverlight.</span><span class="sxs-lookup"><span data-stu-id="9c722-109">The core version of the CLR, used in Silverlight.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c722-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9c722-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c722-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9c722-111">Requirements</span></span>  
 <span data-ttu-id="9c722-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c722-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c722-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9c722-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9c722-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c722-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c722-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c722-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c722-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c722-116">See also</span></span>

- [<span data-ttu-id="9c722-117">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="9c722-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
