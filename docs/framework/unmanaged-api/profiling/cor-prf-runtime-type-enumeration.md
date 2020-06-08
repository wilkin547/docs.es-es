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
ms.openlocfilehash: cc8b7a3174502471debf1d28725ed26c847eeb69
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500798"
---
# <a name="cor_prf_runtime_type-enumeration"></a><span data-ttu-id="3d03f-102">COR_PRF_RUNTIME_TYPE (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="3d03f-102">COR_PRF_RUNTIME_TYPE Enumeration</span></span>
<span data-ttu-id="3d03f-103">Contiene valores que indican la versión de Common Language Runtime (CLR): Desktop o CoreCLR, que se usa en Silverlight.</span><span class="sxs-lookup"><span data-stu-id="3d03f-103">Contains values that indicate the version of the common language runtime (CLR): desktop or CoreCLR, which is used in Silverlight.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d03f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3d03f-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{  
    COR_PRF_DESKTOP_CLR = 0x1,  
    COR_PRF_CORE_CLR    = 0x2,  
} COR_PRF_RUNTIME_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="3d03f-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="3d03f-105">Members</span></span>  
  
|<span data-ttu-id="3d03f-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="3d03f-106">Member</span></span>|<span data-ttu-id="3d03f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="3d03f-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_DESKTOP_CLR`|<span data-ttu-id="3d03f-108">Versión de escritorio de CLR.</span><span class="sxs-lookup"><span data-stu-id="3d03f-108">The desktop version of the CLR.</span></span>|  
|`COR_PRF_CORE_CLR`|<span data-ttu-id="3d03f-109">Versión básica de CLR, que se usa en Silverlight.</span><span class="sxs-lookup"><span data-stu-id="3d03f-109">The core version of the CLR, used in Silverlight.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d03f-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3d03f-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d03f-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3d03f-111">Requirements</span></span>  
 <span data-ttu-id="3d03f-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d03f-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d03f-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3d03f-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3d03f-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d03f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d03f-115">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d03f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d03f-116">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="3d03f-116">See also</span></span>

- [<span data-ttu-id="3d03f-117">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="3d03f-117">Profiling Enumerations</span></span>](profiling-enumerations.md)
