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
ms.openlocfilehash: 78e34d9d33d34047e3ebd2effb4894bc7b709585
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132357"
---
# <a name="cor_field-structure"></a><span data-ttu-id="b9196-102">COR_FIELD (Estructura)</span><span class="sxs-lookup"><span data-stu-id="b9196-102">COR_FIELD Structure</span></span>
<span data-ttu-id="b9196-103">Proporciona información sobre un campo en un objeto.</span><span class="sxs-lookup"><span data-stu-id="b9196-103">Provides information about a field in an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9196-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b9196-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_FIELD{  
    mdFieldDef token;  
    ULONG32 offset;  
    COR_TYPEID id;  
    CorElementType fieldType;  
} COR_FIELD;  
```  
  
## <a name="members"></a><span data-ttu-id="b9196-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="b9196-105">Members</span></span>  
  
|<span data-ttu-id="b9196-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="b9196-106">Member</span></span>|<span data-ttu-id="b9196-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b9196-107">Description</span></span>|  
|------------|-----------------|  
|`token`|<span data-ttu-id="b9196-108">Un token de `mdFieldDef` que se puede utilizar para obtener información de campo.</span><span class="sxs-lookup"><span data-stu-id="b9196-108">An `mdFieldDef` token that can be used to get field information.</span></span>|  
|`offset`|<span data-ttu-id="b9196-109">Desplazamiento, en bytes, para los datos de campo del objeto.</span><span class="sxs-lookup"><span data-stu-id="b9196-109">The offset, in bytes, to the field data in the object.</span></span>|  
|`id`|<span data-ttu-id="b9196-110">Valor de [COR_TYPEID](cor-typeid-structure.md) que identifica el tipo de este campo.</span><span class="sxs-lookup"><span data-stu-id="b9196-110">A [COR_TYPEID](cor-typeid-structure.md) value that identifies the type of this field.</span></span>|  
|`fieldType`|<span data-ttu-id="b9196-111">Un valor de enumeración CorElementType que indica el tipo del campo.</span><span class="sxs-lookup"><span data-stu-id="b9196-111">A CorElementType enumeration value that indicates the type of the field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9196-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b9196-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9196-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b9196-113">Requirements</span></span>  
 <span data-ttu-id="b9196-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9196-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9196-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b9196-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b9196-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9196-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9196-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9196-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9196-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9196-118">See also</span></span>

- [<span data-ttu-id="b9196-119">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="b9196-119">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="b9196-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="b9196-120">Debugging</span></span>](index.md)
