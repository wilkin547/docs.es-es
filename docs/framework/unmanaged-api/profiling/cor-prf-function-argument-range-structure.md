---
description: 'Más información acerca de: estructura de COR_PRF_FUNCTION_ARGUMENT_RANGE'
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
ms.openlocfilehash: 65d762ba4513341b20426ea56d423a2066f6e714
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649031"
---
# <a name="cor_prf_function_argument_range-structure"></a><span data-ttu-id="103ee-103">COR_PRF_FUNCTION_ARGUMENT_RANGE (Estructura)</span><span class="sxs-lookup"><span data-stu-id="103ee-103">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>

<span data-ttu-id="103ee-104">Representa un bloque de argumentos de función almacenados en la memoria de forma contigua, ordenados de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="103ee-104">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="103ee-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="103ee-105">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_RANGE {  
    UINT_PTR startAddress;  
    ULONG length;  
} COR_PRF_FUNCTION_ARGUMENT_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="103ee-106">Members</span><span class="sxs-lookup"><span data-stu-id="103ee-106">Members</span></span>  
  
|<span data-ttu-id="103ee-107">Members</span><span class="sxs-lookup"><span data-stu-id="103ee-107">Members</span></span>|<span data-ttu-id="103ee-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="103ee-108">Description</span></span>|  
|-------------|-----------------|  
|`startAddress`|<span data-ttu-id="103ee-109">Dirección inicial del bloque.</span><span class="sxs-lookup"><span data-stu-id="103ee-109">The starting address of the block.</span></span>|  
|`length`|<span data-ttu-id="103ee-110">Longitud del bloque contiguo.</span><span class="sxs-lookup"><span data-stu-id="103ee-110">The length of the contiguous block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="103ee-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="103ee-111">Requirements</span></span>  

 <span data-ttu-id="103ee-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="103ee-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="103ee-113">**Encabezado:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="103ee-113">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="103ee-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="103ee-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="103ee-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="103ee-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="103ee-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="103ee-116">See also</span></span>

- [<span data-ttu-id="103ee-117">Estructuras para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="103ee-117">Profiling Structures</span></span>](profiling-structures.md)
