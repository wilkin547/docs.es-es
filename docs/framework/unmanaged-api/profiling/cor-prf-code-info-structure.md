---
title: COR_PRF_CODE_INFO (Estructura)
ms.date: 03/30/2017
api_name:
- COR_PRF_CODE_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_CODE_INFO
helpviewer_keywords:
- COR_PRF_CODE_INFO structure [.NET Framework profiling]
ms.assetid: cf30e27c-1f7e-43a2-ba1e-01e4137301db
topic_type:
- apiref
ms.openlocfilehash: b64e58a79f3dbe0c91b0c0cefc4a9d918c700cf9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718636"
---
# <a name="cor_prf_code_info-structure"></a><span data-ttu-id="41008-102">COR_PRF_CODE_INFO (Estructura)</span><span class="sxs-lookup"><span data-stu-id="41008-102">COR_PRF_CODE_INFO Structure</span></span>

<span data-ttu-id="41008-103">Representa un bloque contiguo de código nativo almacenado en la memoria.</span><span class="sxs-lookup"><span data-stu-id="41008-103">Represents one contiguous block of native code stored in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41008-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="41008-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_CODE_INFO {  
    UINT_PTR startAddress;  
    SIZE_T size;  
} COR_PRF_CODE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="41008-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="41008-105">Members</span></span>  
  
|<span data-ttu-id="41008-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="41008-106">Member</span></span>|<span data-ttu-id="41008-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="41008-107">Description</span></span>|  
|------------|-----------------|  
|`startAddress`|<span data-ttu-id="41008-108">Dirección inicial del bloque de código contiguo.</span><span class="sxs-lookup"><span data-stu-id="41008-108">The starting address of the contiguous block of code.</span></span>|  
|`size`|<span data-ttu-id="41008-109">Tamaño del bloque.</span><span class="sxs-lookup"><span data-stu-id="41008-109">The size of the block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="41008-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="41008-110">Requirements</span></span>  

 <span data-ttu-id="41008-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41008-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41008-112">**Encabezado:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="41008-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="41008-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41008-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41008-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41008-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41008-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="41008-115">See also</span></span>

- [<span data-ttu-id="41008-116">Estructuras para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="41008-116">Profiling Structures</span></span>](profiling-structures.md)
