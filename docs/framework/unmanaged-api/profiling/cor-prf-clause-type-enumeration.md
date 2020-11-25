---
title: COR_PRF_CLAUSE_TYPE (Enumeración)
ms.date: 03/30/2017
api_name:
- COR_PRF_CLAUSE_TYPE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_CLAUSE_TYPE
helpviewer_keywords:
- COR_PRF_CLAUSE_TYPE enumeration [.NET Framework profiling]
ms.assetid: f64c325a-ed3a-4aaf-b847-a88edbc4fefc
topic_type:
- apiref
ms.openlocfilehash: c3058229a3c2b3c529136dad70fea35a23708a33
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718662"
---
# <a name="cor_prf_clause_type-enumeration"></a><span data-ttu-id="e5b72-102">COR_PRF_CLAUSE_TYPE (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="e5b72-102">COR_PRF_CLAUSE_TYPE Enumeration</span></span>

<span data-ttu-id="e5b72-103">Indica el tipo de cláusula de excepción en la que el código acaba de entrar o de la que acaba de salir.</span><span class="sxs-lookup"><span data-stu-id="e5b72-103">Indicates the type of exception clause that the code has just entered or left.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5b72-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5b72-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_CLAUSE_NONE = 0,  
    COR_PRF_CLAUSE_FILTER = 1,  
    COR_PRF_CLAUSE_CATCH = 2,  
    COR_PRF_CLAUSE_FINALLY = 3,  
} COR_PRF_CLAUSE_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="e5b72-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="e5b72-105">Members</span></span>  
  
|<span data-ttu-id="e5b72-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="e5b72-106">Member</span></span>|<span data-ttu-id="e5b72-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e5b72-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_CLAUSE_NONE`|<span data-ttu-id="e5b72-108">La cláusula de excepción no es válida.</span><span class="sxs-lookup"><span data-stu-id="e5b72-108">The exception clause is not valid.</span></span>|  
|`COR_PRF_CLAUSE_FILTER`|<span data-ttu-id="e5b72-109">La cláusula Exception es una expresión de filtro.</span><span class="sxs-lookup"><span data-stu-id="e5b72-109">The exception clause is a filter expression.</span></span>|  
|`COR_PRF_CLAUSE_CATCH`|<span data-ttu-id="e5b72-110">La cláusula Exception es una `catch` instrucción.</span><span class="sxs-lookup"><span data-stu-id="e5b72-110">The exception clause is a `catch` statement.</span></span>|  
|`COR_PRF_CLAUSE_FINALLY`|<span data-ttu-id="e5b72-111">La cláusula Exception es una `finally` instrucción.</span><span class="sxs-lookup"><span data-stu-id="e5b72-111">The exception clause is a `finally` statement.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e5b72-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e5b72-112">Requirements</span></span>  

 <span data-ttu-id="e5b72-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5b72-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5b72-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e5b72-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e5b72-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5b72-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5b72-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5b72-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5b72-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e5b72-117">See also</span></span>

- [<span data-ttu-id="e5b72-118">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="e5b72-118">Profiling Enumerations</span></span>](profiling-enumerations.md)
