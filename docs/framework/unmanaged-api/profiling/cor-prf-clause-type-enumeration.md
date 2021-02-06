---
description: 'Más información acerca de: enumeración COR_PRF_CLAUSE_TYPE'
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
ms.openlocfilehash: 413dbc0ad94e4ab670cd7cd9537bbd1735ffd7cf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649291"
---
# <a name="cor_prf_clause_type-enumeration"></a><span data-ttu-id="e08da-103">COR_PRF_CLAUSE_TYPE (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="e08da-103">COR_PRF_CLAUSE_TYPE Enumeration</span></span>

<span data-ttu-id="e08da-104">Indica el tipo de cláusula de excepción en la que el código acaba de entrar o de la que acaba de salir.</span><span class="sxs-lookup"><span data-stu-id="e08da-104">Indicates the type of exception clause that the code has just entered or left.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e08da-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e08da-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_CLAUSE_NONE = 0,  
    COR_PRF_CLAUSE_FILTER = 1,  
    COR_PRF_CLAUSE_CATCH = 2,  
    COR_PRF_CLAUSE_FINALLY = 3,  
} COR_PRF_CLAUSE_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="e08da-106">Members</span><span class="sxs-lookup"><span data-stu-id="e08da-106">Members</span></span>  
  
|<span data-ttu-id="e08da-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="e08da-107">Member</span></span>|<span data-ttu-id="e08da-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="e08da-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_CLAUSE_NONE`|<span data-ttu-id="e08da-109">La cláusula de excepción no es válida.</span><span class="sxs-lookup"><span data-stu-id="e08da-109">The exception clause is not valid.</span></span>|  
|`COR_PRF_CLAUSE_FILTER`|<span data-ttu-id="e08da-110">La cláusula Exception es una expresión de filtro.</span><span class="sxs-lookup"><span data-stu-id="e08da-110">The exception clause is a filter expression.</span></span>|  
|`COR_PRF_CLAUSE_CATCH`|<span data-ttu-id="e08da-111">La cláusula Exception es una `catch` instrucción.</span><span class="sxs-lookup"><span data-stu-id="e08da-111">The exception clause is a `catch` statement.</span></span>|  
|`COR_PRF_CLAUSE_FINALLY`|<span data-ttu-id="e08da-112">La cláusula Exception es una `finally` instrucción.</span><span class="sxs-lookup"><span data-stu-id="e08da-112">The exception clause is a `finally` statement.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e08da-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e08da-113">Requirements</span></span>  

 <span data-ttu-id="e08da-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e08da-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e08da-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e08da-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e08da-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e08da-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e08da-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e08da-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e08da-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="e08da-118">See also</span></span>

- [<span data-ttu-id="e08da-119">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="e08da-119">Profiling Enumerations</span></span>](profiling-enumerations.md)
