---
title: COR_FIELD (Estructura)
ms.date: 03/30/2017
api_name:
- COR_FIELD
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_FIELD
helpviewer_keywords:
- COR_FIELD structure [.NET Framework debugging]
ms.assetid: c0822423-a9df-4961-950d-50dcc152f863
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2efe159eaa8b49d4d3825e9737593d0a12fc4d4c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740737"
---
# <a name="corfield-structure"></a><span data-ttu-id="174c3-102">COR_FIELD (Estructura)</span><span class="sxs-lookup"><span data-stu-id="174c3-102">COR_FIELD Structure</span></span>
<span data-ttu-id="174c3-103">Proporciona información sobre un campo en un objeto.</span><span class="sxs-lookup"><span data-stu-id="174c3-103">Provides information about a field in an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="174c3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="174c3-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_FIELD{  
    mdFieldDef token;  
    ULONG32 offset;  
    COR_TYPEID id;  
    CorElementType fieldType;  
} COR_FIELD;  
```  
  
## <a name="members"></a><span data-ttu-id="174c3-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="174c3-105">Members</span></span>  
  
|<span data-ttu-id="174c3-106">Member</span><span class="sxs-lookup"><span data-stu-id="174c3-106">Member</span></span>|<span data-ttu-id="174c3-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="174c3-107">Description</span></span>|  
|------------|-----------------|  
|`token`|<span data-ttu-id="174c3-108">Un `mdFieldDef` símbolo (token) que puede usarse para obtener información de campo.</span><span class="sxs-lookup"><span data-stu-id="174c3-108">An `mdFieldDef` token that can be used to get field information.</span></span>|  
|`offset`|<span data-ttu-id="174c3-109">El desplazamiento, en bytes, para los datos del campo en el objeto.</span><span class="sxs-lookup"><span data-stu-id="174c3-109">The offset, in bytes, to the field data in the object.</span></span>|  
|`id`|<span data-ttu-id="174c3-110">Un [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) valor que identifica el tipo de este campo.</span><span class="sxs-lookup"><span data-stu-id="174c3-110">A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) value that identifies the type of this field.</span></span>|  
|`fieldType`|<span data-ttu-id="174c3-111">Un valor de enumeración CorElementType que indica el tipo del campo.</span><span class="sxs-lookup"><span data-stu-id="174c3-111">A CorElementType enumeration value that indicates the type of the field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="174c3-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="174c3-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="174c3-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="174c3-113">Requirements</span></span>  
 <span data-ttu-id="174c3-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="174c3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="174c3-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="174c3-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="174c3-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="174c3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="174c3-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="174c3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="174c3-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="174c3-118">See also</span></span>

- [<span data-ttu-id="174c3-119">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="174c3-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="174c3-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="174c3-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
