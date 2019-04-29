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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dffefedf14d5f219736e429be191021b2de7ddd2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61599330"
---
# <a name="corprffunctionargumentrange-structure"></a><span data-ttu-id="0bac4-102">COR_PRF_FUNCTION_ARGUMENT_RANGE (Estructura)</span><span class="sxs-lookup"><span data-stu-id="0bac4-102">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>
<span data-ttu-id="0bac4-103">Representa un bloque de argumentos de función almacenados en la memoria de forma contigua, ordenados de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="0bac4-103">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bac4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0bac4-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_RANGE {  
    UINT_PTR startAddress;  
    ULONG length;  
} COR_PRF_FUNCTION_ARGUMENT_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="0bac4-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="0bac4-105">Members</span></span>  
  
|<span data-ttu-id="0bac4-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="0bac4-106">Members</span></span>|<span data-ttu-id="0bac4-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="0bac4-107">Description</span></span>|  
|-------------|-----------------|  
|`startAddress`|<span data-ttu-id="0bac4-108">La dirección inicial del bloque.</span><span class="sxs-lookup"><span data-stu-id="0bac4-108">The starting address of the block.</span></span>|  
|`length`|<span data-ttu-id="0bac4-109">La longitud del bloque contiguo.</span><span class="sxs-lookup"><span data-stu-id="0bac4-109">The length of the contiguous block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0bac4-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0bac4-110">Requirements</span></span>  
 <span data-ttu-id="0bac4-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0bac4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bac4-112">**Encabezado**: CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="0bac4-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="0bac4-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0bac4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0bac4-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bac4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bac4-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="0bac4-115">See also</span></span>

- [<span data-ttu-id="0bac4-116">Estructuras para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="0bac4-116">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
