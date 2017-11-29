---
title: "COR_PRF_RUNTIME_TYPE (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_RUNTIME_TYPE Enumeration
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_RUNTIME_TYPE
helpviewer_keywords: COR_PRF_RUNTIME_TYPE enumeration [.NET Framework profiling]
ms.assetid: 35449514-333f-4918-9c60-7aa198d655d2
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1a16cfe2f0f2c05721be4d4630729cfbbff98c8f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="corprfruntimetype-enumeration"></a><span data-ttu-id="a3e1d-102">COR_PRF_RUNTIME_TYPE (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="a3e1d-102">COR_PRF_RUNTIME_TYPE Enumeration</span></span>
<span data-ttu-id="a3e1d-103">Contiene valores que indican la versión de common language runtime (CLR): escritorio o CoreCLR, que se usa en Silverlight.</span><span class="sxs-lookup"><span data-stu-id="a3e1d-103">Contains values that indicate the version of the common language runtime (CLR): desktop or CoreCLR, which is used in Silverlight.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3e1d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a3e1d-104">Syntax</span></span>  
  
```  
typedef enum  
{  
    COR_PRF_DESKTOP_CLR = 0x1,  
    COR_PRF_CORE_CLR    = 0x2,  
} COR_PRF_RUNTIME_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="a3e1d-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="a3e1d-105">Members</span></span>  
  
|<span data-ttu-id="a3e1d-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="a3e1d-106">Member</span></span>|<span data-ttu-id="a3e1d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a3e1d-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_DESKTOP_CLR`|<span data-ttu-id="a3e1d-108">La versión de escritorio de CLR.</span><span class="sxs-lookup"><span data-stu-id="a3e1d-108">The desktop version of the CLR.</span></span>|  
|`COR_PRF_CORE_CLR`|<span data-ttu-id="a3e1d-109">La versión principal de CLR, que se usa en Silverlight.</span><span class="sxs-lookup"><span data-stu-id="a3e1d-109">The core version of the CLR, used in Silverlight.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3e1d-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a3e1d-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3e1d-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a3e1d-111">Requirements</span></span>  
 <span data-ttu-id="a3e1d-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3e1d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3e1d-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a3e1d-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a3e1d-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3e1d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3e1d-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3e1d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3e1d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3e1d-116">See Also</span></span>  
 [<span data-ttu-id="a3e1d-117">Enumeraciones de generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="a3e1d-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
