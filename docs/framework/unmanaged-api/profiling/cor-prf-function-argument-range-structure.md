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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59125598"
---
# <a name="corprffunctionargumentrange-structure"></a><span data-ttu-id="c5e41-102">COR_PRF_FUNCTION_ARGUMENT_RANGE (Estructura)</span><span class="sxs-lookup"><span data-stu-id="c5e41-102">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>
<span data-ttu-id="c5e41-103">Representa un bloque de argumentos de función almacenados en la memoria de forma contigua, ordenados de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="c5e41-103">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5e41-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c5e41-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_RANGE {  
    UINT_PTR startAddress;  
    ULONG length;  
} COR_PRF_FUNCTION_ARGUMENT_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="c5e41-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="c5e41-105">Members</span></span>  
  
|<span data-ttu-id="c5e41-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="c5e41-106">Members</span></span>|<span data-ttu-id="c5e41-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c5e41-107">Description</span></span>|  
|-------------|-----------------|  
|`startAddress`|<span data-ttu-id="c5e41-108">La dirección inicial del bloque.</span><span class="sxs-lookup"><span data-stu-id="c5e41-108">The starting address of the block.</span></span>|  
|`length`|<span data-ttu-id="c5e41-109">La longitud del bloque contiguo.</span><span class="sxs-lookup"><span data-stu-id="c5e41-109">The length of the contiguous block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c5e41-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c5e41-110">Requirements</span></span>  
 <span data-ttu-id="c5e41-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5e41-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5e41-112">**Encabezado**: CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="c5e41-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="c5e41-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c5e41-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="c5e41-114">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c5e41-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c5e41-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5e41-115">See also</span></span>

- [<span data-ttu-id="c5e41-116">Estructuras para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="c5e41-116">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
