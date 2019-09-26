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
ms.openlocfilehash: f857f773f02da25fe6650000be777b8290f5af91
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274060"
---
# <a name="cor_field-structure"></a><span data-ttu-id="f9c5e-102">COR_FIELD (Estructura)</span><span class="sxs-lookup"><span data-stu-id="f9c5e-102">COR_FIELD Structure</span></span>
<span data-ttu-id="f9c5e-103">Proporciona información sobre un campo en un objeto.</span><span class="sxs-lookup"><span data-stu-id="f9c5e-103">Provides information about a field in an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9c5e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f9c5e-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_FIELD{  
    mdFieldDef token;  
    ULONG32 offset;  
    COR_TYPEID id;  
    CorElementType fieldType;  
} COR_FIELD;  
```  
  
## <a name="members"></a><span data-ttu-id="f9c5e-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="f9c5e-105">Members</span></span>  
  
|<span data-ttu-id="f9c5e-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="f9c5e-106">Member</span></span>|<span data-ttu-id="f9c5e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f9c5e-107">Description</span></span>|  
|------------|-----------------|  
|`token`|<span data-ttu-id="f9c5e-108">Un `mdFieldDef` token que se puede utilizar para obtener información de campo.</span><span class="sxs-lookup"><span data-stu-id="f9c5e-108">An `mdFieldDef` token that can be used to get field information.</span></span>|  
|`offset`|<span data-ttu-id="f9c5e-109">Desplazamiento, en bytes, para los datos de campo del objeto.</span><span class="sxs-lookup"><span data-stu-id="f9c5e-109">The offset, in bytes, to the field data in the object.</span></span>|  
|`id`|<span data-ttu-id="f9c5e-110">Valor de [COR_TYPEID](cor-typeid-structure.md) que identifica el tipo de este campo.</span><span class="sxs-lookup"><span data-stu-id="f9c5e-110">A [COR_TYPEID](cor-typeid-structure.md) value that identifies the type of this field.</span></span>|  
|`fieldType`|<span data-ttu-id="f9c5e-111">Un valor de enumeración CorElementType que indica el tipo del campo.</span><span class="sxs-lookup"><span data-stu-id="f9c5e-111">A CorElementType enumeration value that indicates the type of the field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f9c5e-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f9c5e-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9c5e-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f9c5e-113">Requirements</span></span>  
 <span data-ttu-id="f9c5e-114">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9c5e-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9c5e-115">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="f9c5e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f9c5e-116">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f9c5e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f9c5e-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9c5e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9c5e-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9c5e-118">See also</span></span>

- [<span data-ttu-id="f9c5e-119">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="f9c5e-119">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="f9c5e-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="f9c5e-120">Debugging</span></span>](index.md)
