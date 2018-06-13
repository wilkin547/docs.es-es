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
ms.openlocfilehash: 92e3a0a930a4e4b91cac27cbed1b745dea4207a9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450029"
---
# <a name="corprffunctionargumentrange-structure"></a><span data-ttu-id="2950c-102">COR_PRF_FUNCTION_ARGUMENT_RANGE (Estructura)</span><span class="sxs-lookup"><span data-stu-id="2950c-102">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>
<span data-ttu-id="2950c-103">Representa un bloque de argumentos de función almacenados en la memoria de forma contigua, ordenados de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="2950c-103">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2950c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2950c-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_RANGE {  
    UINT_PTR startAddress;  
    ULONG length;  
} COR_PRF_FUNCTION_ARGUMENT_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="2950c-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="2950c-105">Members</span></span>  
  
|<span data-ttu-id="2950c-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="2950c-106">Members</span></span>|<span data-ttu-id="2950c-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="2950c-107">Description</span></span>|  
|-------------|-----------------|  
|`startAddress`|<span data-ttu-id="2950c-108">La dirección inicial del bloque.</span><span class="sxs-lookup"><span data-stu-id="2950c-108">The starting address of the block.</span></span>|  
|`length`|<span data-ttu-id="2950c-109">La longitud del bloque contiguo.</span><span class="sxs-lookup"><span data-stu-id="2950c-109">The length of the contiguous block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2950c-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2950c-110">Requirements</span></span>  
 <span data-ttu-id="2950c-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2950c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2950c-112">**Encabezado:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="2950c-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="2950c-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2950c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2950c-114">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2950c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2950c-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="2950c-115">See Also</span></span>  
 [<span data-ttu-id="2950c-116">Estructuras para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="2950c-116">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
