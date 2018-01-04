---
title: "COR_PRF_CLAUSE_TYPE (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_CLAUSE_TYPE
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_CLAUSE_TYPE
helpviewer_keywords: COR_PRF_CLAUSE_TYPE enumeration [.NET Framework profiling]
ms.assetid: f64c325a-ed3a-4aaf-b847-a88edbc4fefc
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e03b3f2462b8876bfba3cf7d0df40311935722f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="corprfclausetype-enumeration"></a><span data-ttu-id="9d75e-102">COR_PRF_CLAUSE_TYPE (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="9d75e-102">COR_PRF_CLAUSE_TYPE Enumeration</span></span>
<span data-ttu-id="9d75e-103">Indica el tipo de cláusula de excepción en la que el código acaba de entrar o de la que acaba de salir.</span><span class="sxs-lookup"><span data-stu-id="9d75e-103">Indicates the type of exception clause that the code has just entered or left.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d75e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9d75e-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_CLAUSE_NONE = 0,  
    COR_PRF_CLAUSE_FILTER = 1,  
    COR_PRF_CLAUSE_CATCH = 2,  
    COR_PRF_CLAUSE_FINALLY = 3,  
} COR_PRF_CLAUSE_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="9d75e-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="9d75e-105">Members</span></span>  
  
|<span data-ttu-id="9d75e-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="9d75e-106">Member</span></span>|<span data-ttu-id="9d75e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9d75e-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_CLAUSE_NONE`|<span data-ttu-id="9d75e-108">La cláusula de excepción no es válida.</span><span class="sxs-lookup"><span data-stu-id="9d75e-108">The exception clause is not valid.</span></span>|  
|`COR_PRF_CLAUSE_FILTER`|<span data-ttu-id="9d75e-109">La cláusula de excepción es una expresión de filtro.</span><span class="sxs-lookup"><span data-stu-id="9d75e-109">The exception clause is a filter expression.</span></span>|  
|`COR_PRF_CLAUSE_CATCH`|<span data-ttu-id="9d75e-110">La cláusula de excepción es una `catch` instrucción.</span><span class="sxs-lookup"><span data-stu-id="9d75e-110">The exception clause is a `catch` statement.</span></span>|  
|`COR_PRF_CLAUSE_FINALLY`|<span data-ttu-id="9d75e-111">La cláusula de excepción es una `finally` instrucción.</span><span class="sxs-lookup"><span data-stu-id="9d75e-111">The exception clause is a `finally` statement.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9d75e-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9d75e-112">Requirements</span></span>  
 <span data-ttu-id="9d75e-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d75e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d75e-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9d75e-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9d75e-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d75e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d75e-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d75e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d75e-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d75e-117">See Also</span></span>  
 [<span data-ttu-id="9d75e-118">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="9d75e-118">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
