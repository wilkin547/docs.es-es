---
title: COR_PRF_FUNCTION_ARGUMENT_RANGE (Estructura)
ms.date: 03/30/2017
api_name:
- COR_PRF_FUNCTION_ARGUMENT_RANGE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FUNCTION_ARGUMENT_RANGE
helpviewer_keywords:
- COR_PRF_FUNCTION_ARGUMENT_RANGE structure [.NET Framework profiling'
ms.assetid: 9f469eac-ac66-419b-8668-fe705bc1a51f
topic_type:
- apiref
ms.openlocfilehash: 028395b1c8677d07d4a6481740ecdc7ebb48c180
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718532"
---
# <a name="cor_prf_function_argument_range-structure"></a><span data-ttu-id="ea1e2-102">COR_PRF_FUNCTION_ARGUMENT_RANGE (Estructura)</span><span class="sxs-lookup"><span data-stu-id="ea1e2-102">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>

<span data-ttu-id="ea1e2-103">Representa un bloque de argumentos de función almacenados en la memoria de forma contigua, ordenados de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="ea1e2-103">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea1e2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ea1e2-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_RANGE {  
    UINT_PTR startAddress;  
    ULONG length;  
} COR_PRF_FUNCTION_ARGUMENT_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="ea1e2-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="ea1e2-105">Members</span></span>  
  
|<span data-ttu-id="ea1e2-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="ea1e2-106">Members</span></span>|<span data-ttu-id="ea1e2-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ea1e2-107">Description</span></span>|  
|-------------|-----------------|  
|`startAddress`|<span data-ttu-id="ea1e2-108">Dirección inicial del bloque.</span><span class="sxs-lookup"><span data-stu-id="ea1e2-108">The starting address of the block.</span></span>|  
|`length`|<span data-ttu-id="ea1e2-109">Longitud del bloque contiguo.</span><span class="sxs-lookup"><span data-stu-id="ea1e2-109">The length of the contiguous block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ea1e2-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ea1e2-110">Requirements</span></span>  

 <span data-ttu-id="ea1e2-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea1e2-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea1e2-112">**Encabezado:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="ea1e2-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="ea1e2-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea1e2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea1e2-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea1e2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea1e2-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ea1e2-115">See also</span></span>

- [<span data-ttu-id="ea1e2-116">Estructuras para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="ea1e2-116">Profiling Structures</span></span>](profiling-structures.md)
