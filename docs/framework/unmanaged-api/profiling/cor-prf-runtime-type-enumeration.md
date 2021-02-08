---
description: 'Más información acerca de: enumeración COR_PRF_RUNTIME_TYPE'
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
ms.openlocfilehash: 8f4b4a0c51c43b1db97b511387eaee1aee79f523
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789052"
---
# <a name="cor_prf_runtime_type-enumeration"></a><span data-ttu-id="a78ec-103">COR_PRF_RUNTIME_TYPE (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="a78ec-103">COR_PRF_RUNTIME_TYPE Enumeration</span></span>

<span data-ttu-id="a78ec-104">Contiene valores que indican la versión de Common Language Runtime (CLR): Desktop o CoreCLR, que se usa en Silverlight.</span><span class="sxs-lookup"><span data-stu-id="a78ec-104">Contains values that indicate the version of the common language runtime (CLR): desktop or CoreCLR, which is used in Silverlight.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a78ec-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a78ec-105">Syntax</span></span>  
  
```cpp  
typedef enum  
{  
    COR_PRF_DESKTOP_CLR = 0x1,  
    COR_PRF_CORE_CLR    = 0x2,  
} COR_PRF_RUNTIME_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="a78ec-106">Members</span><span class="sxs-lookup"><span data-stu-id="a78ec-106">Members</span></span>  
  
|<span data-ttu-id="a78ec-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="a78ec-107">Member</span></span>|<span data-ttu-id="a78ec-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="a78ec-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_DESKTOP_CLR`|<span data-ttu-id="a78ec-109">Versión de escritorio de CLR.</span><span class="sxs-lookup"><span data-stu-id="a78ec-109">The desktop version of the CLR.</span></span>|  
|`COR_PRF_CORE_CLR`|<span data-ttu-id="a78ec-110">Versión básica de CLR, que se usa en Silverlight.</span><span class="sxs-lookup"><span data-stu-id="a78ec-110">The core version of the CLR, used in Silverlight.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a78ec-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a78ec-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a78ec-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a78ec-112">Requirements</span></span>  

 <span data-ttu-id="a78ec-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a78ec-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a78ec-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a78ec-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a78ec-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a78ec-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a78ec-116">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a78ec-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a78ec-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="a78ec-117">See also</span></span>

- [<span data-ttu-id="a78ec-118">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="a78ec-118">Profiling Enumerations</span></span>](profiling-enumerations.md)
