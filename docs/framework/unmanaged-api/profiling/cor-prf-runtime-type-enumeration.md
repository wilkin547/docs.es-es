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
ms.openlocfilehash: 6c52f96ad9458dfd5cdedc5cc73154aa570c6759
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751964"
---
# <a name="corprfruntimetype-enumeration"></a><span data-ttu-id="4ae55-102">COR_PRF_RUNTIME_TYPE (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="4ae55-102">COR_PRF_RUNTIME_TYPE Enumeration</span></span>
<span data-ttu-id="4ae55-103">Contiene valores que indican la versión de common language runtime (CLR): escritorio o CoreCLR, que se usa en Silverlight.</span><span class="sxs-lookup"><span data-stu-id="4ae55-103">Contains values that indicate the version of the common language runtime (CLR): desktop or CoreCLR, which is used in Silverlight.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ae55-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4ae55-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{  
    COR_PRF_DESKTOP_CLR = 0x1,  
    COR_PRF_CORE_CLR    = 0x2,  
} COR_PRF_RUNTIME_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="4ae55-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="4ae55-105">Members</span></span>  
  
|<span data-ttu-id="4ae55-106">Member</span><span class="sxs-lookup"><span data-stu-id="4ae55-106">Member</span></span>|<span data-ttu-id="4ae55-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4ae55-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_DESKTOP_CLR`|<span data-ttu-id="4ae55-108">La versión de CLR de escritorio.</span><span class="sxs-lookup"><span data-stu-id="4ae55-108">The desktop version of the CLR.</span></span>|  
|`COR_PRF_CORE_CLR`|<span data-ttu-id="4ae55-109">La versión principal de CLR, que usa en Silverlight.</span><span class="sxs-lookup"><span data-stu-id="4ae55-109">The core version of the CLR, used in Silverlight.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ae55-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4ae55-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ae55-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4ae55-111">Requirements</span></span>  
 <span data-ttu-id="4ae55-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ae55-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ae55-113">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4ae55-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4ae55-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ae55-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ae55-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ae55-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ae55-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ae55-116">See also</span></span>

- [<span data-ttu-id="4ae55-117">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="4ae55-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
