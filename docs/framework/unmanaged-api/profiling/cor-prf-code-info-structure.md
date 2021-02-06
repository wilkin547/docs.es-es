---
description: 'Más información acerca de: estructura de COR_PRF_CODE_INFO'
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
ms.openlocfilehash: 11eae032424a039cac1136c08409b5b4712e6db1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649252"
---
# <a name="cor_prf_code_info-structure"></a><span data-ttu-id="b32e5-103">COR_PRF_CODE_INFO (Estructura)</span><span class="sxs-lookup"><span data-stu-id="b32e5-103">COR_PRF_CODE_INFO Structure</span></span>

<span data-ttu-id="b32e5-104">Representa un bloque contiguo de código nativo almacenado en la memoria.</span><span class="sxs-lookup"><span data-stu-id="b32e5-104">Represents one contiguous block of native code stored in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b32e5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b32e5-105">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_CODE_INFO {  
    UINT_PTR startAddress;  
    SIZE_T size;  
} COR_PRF_CODE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="b32e5-106">Members</span><span class="sxs-lookup"><span data-stu-id="b32e5-106">Members</span></span>  
  
|<span data-ttu-id="b32e5-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="b32e5-107">Member</span></span>|<span data-ttu-id="b32e5-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="b32e5-108">Description</span></span>|  
|------------|-----------------|  
|`startAddress`|<span data-ttu-id="b32e5-109">Dirección inicial del bloque de código contiguo.</span><span class="sxs-lookup"><span data-stu-id="b32e5-109">The starting address of the contiguous block of code.</span></span>|  
|`size`|<span data-ttu-id="b32e5-110">Tamaño del bloque.</span><span class="sxs-lookup"><span data-stu-id="b32e5-110">The size of the block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b32e5-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b32e5-111">Requirements</span></span>  

 <span data-ttu-id="b32e5-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b32e5-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b32e5-113">**Encabezado:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="b32e5-113">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="b32e5-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b32e5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b32e5-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b32e5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b32e5-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="b32e5-116">See also</span></span>

- [<span data-ttu-id="b32e5-117">Estructuras para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="b32e5-117">Profiling Structures</span></span>](profiling-structures.md)
