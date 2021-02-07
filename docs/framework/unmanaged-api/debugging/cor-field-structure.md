---
description: 'Más información acerca de: estructura de COR_FIELD'
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
ms.openlocfilehash: a3e9dcc2a5c3bb2abae42dab4292c1d285df5ad7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747118"
---
# <a name="cor_field-structure"></a><span data-ttu-id="1bec8-103">COR_FIELD (Estructura)</span><span class="sxs-lookup"><span data-stu-id="1bec8-103">COR_FIELD Structure</span></span>

<span data-ttu-id="1bec8-104">Proporciona información sobre un campo en un objeto.</span><span class="sxs-lookup"><span data-stu-id="1bec8-104">Provides information about a field in an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bec8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1bec8-105">Syntax</span></span>  
  
```cpp  
typedef struct COR_FIELD{  
    mdFieldDef token;  
    ULONG32 offset;  
    COR_TYPEID id;  
    CorElementType fieldType;  
} COR_FIELD;  
```  
  
## <a name="members"></a><span data-ttu-id="1bec8-106">Members</span><span class="sxs-lookup"><span data-stu-id="1bec8-106">Members</span></span>  
  
|<span data-ttu-id="1bec8-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="1bec8-107">Member</span></span>|<span data-ttu-id="1bec8-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="1bec8-108">Description</span></span>|  
|------------|-----------------|  
|`token`|<span data-ttu-id="1bec8-109">Un `mdFieldDef` token que se puede utilizar para obtener información de campo.</span><span class="sxs-lookup"><span data-stu-id="1bec8-109">An `mdFieldDef` token that can be used to get field information.</span></span>|  
|`offset`|<span data-ttu-id="1bec8-110">Desplazamiento, en bytes, para los datos de campo del objeto.</span><span class="sxs-lookup"><span data-stu-id="1bec8-110">The offset, in bytes, to the field data in the object.</span></span>|  
|`id`|<span data-ttu-id="1bec8-111">[COR_TYPEID](cor-typeid-structure.md) valor que identifica el tipo de este campo.</span><span class="sxs-lookup"><span data-stu-id="1bec8-111">A [COR_TYPEID](cor-typeid-structure.md) value that identifies the type of this field.</span></span>|  
|`fieldType`|<span data-ttu-id="1bec8-112">Un valor de enumeración CorElementType que indica el tipo del campo.</span><span class="sxs-lookup"><span data-stu-id="1bec8-112">A CorElementType enumeration value that indicates the type of the field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1bec8-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1bec8-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bec8-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1bec8-114">Requirements</span></span>  

 <span data-ttu-id="1bec8-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1bec8-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bec8-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1bec8-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1bec8-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1bec8-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1bec8-118">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1bec8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bec8-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="1bec8-119">See also</span></span>

- [<span data-ttu-id="1bec8-120">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="1bec8-120">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="1bec8-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="1bec8-121">Debugging</span></span>](index.md)
