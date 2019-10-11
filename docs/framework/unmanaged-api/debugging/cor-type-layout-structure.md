---
title: COR_TYPE_LAYOUT (Estructura)
ms.date: 03/30/2017
api_name:
- COR_TYPE_LAYOUT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_TYPE_LAYOUT
helpviewer_keywords:
- COR_TYPE_LAYOUT structure [.NET Framework debugging]
ms.assetid: 43a7addd-f25a-4049-9907-abec3eb17af2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6bd274b1eb14532629580e777288317186544912
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274163"
---
# <a name="cor_type_layout-structure"></a><span data-ttu-id="dfcdb-102">COR_TYPE_LAYOUT (Estructura)</span><span class="sxs-lookup"><span data-stu-id="dfcdb-102">COR_TYPE_LAYOUT Structure</span></span>
<span data-ttu-id="dfcdb-103">Proporciona información sobre la distribución de un objeto en la memoria.</span><span class="sxs-lookup"><span data-stu-id="dfcdb-103">Provides information about the layout of an object in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfcdb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dfcdb-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_TYPE_LAYOUT {  
    COR_TYPEID parentID;  
    ULONG32 objectSize;  
    ULONG32 numFields;  
    ULONG32 boxOffset;  
    CorElementType type;  
} COR_TYPE_LAYOUT;  
```  
  
## <a name="members"></a><span data-ttu-id="dfcdb-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="dfcdb-105">Members</span></span>  
  
|<span data-ttu-id="dfcdb-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="dfcdb-106">Member</span></span>|<span data-ttu-id="dfcdb-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="dfcdb-107">Description</span></span>|  
|------------|-----------------|  
|`parentID`|<span data-ttu-id="dfcdb-108">Identificador del tipo primario de este tipo.</span><span class="sxs-lookup"><span data-stu-id="dfcdb-108">The identifier of the parent type to this type.</span></span> <span data-ttu-id="dfcdb-109">Será el identificador de tipo NULL (token1 = 0, token2 = 0) si el identificador de tipo corresponde a <xref:System.Object?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="dfcdb-109">This will be the NULL type id (token1= 0, token2 = 0) if the type id corresponds to <xref:System.Object?displayProperty=nameWithType>.</span></span>|  
|`objectSize`|<span data-ttu-id="dfcdb-110">Tamaño base de un objeto de este tipo.</span><span class="sxs-lookup"><span data-stu-id="dfcdb-110">The base size of an object of this type.</span></span> <span data-ttu-id="dfcdb-111">Es el tamaño total de los objetos de tamaño no variable.</span><span class="sxs-lookup"><span data-stu-id="dfcdb-111">This is the total size for non-variable sized objects.</span></span>|  
|`numFields`|<span data-ttu-id="dfcdb-112">El número de campos incluidos en los objetos de este tipo.</span><span class="sxs-lookup"><span data-stu-id="dfcdb-112">The number of fields included in objects of this type.</span></span>|  
|`boxOffset`|<span data-ttu-id="dfcdb-113">Si se aplica la conversión boxing a este tipo, el desplazamiento inicial de los campos de un objeto.</span><span class="sxs-lookup"><span data-stu-id="dfcdb-113">If this type is boxed, the beginning offset of an object's fields.</span></span> <span data-ttu-id="dfcdb-114">Este campo solo es válido para tipos de valor como primitivas y estructuras.</span><span class="sxs-lookup"><span data-stu-id="dfcdb-114">This field is valid only for value types such as primitives and structures.</span></span>|  
|`type`|<span data-ttu-id="dfcdb-115">El CorElementType al que pertenece este tipo.</span><span class="sxs-lookup"><span data-stu-id="dfcdb-115">The CorElementType to which this type belongs.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dfcdb-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dfcdb-116">Remarks</span></span>  
 <span data-ttu-id="dfcdb-117">Si `numFields` es mayor que cero, puede llamar al método [ICorDebugProcess5:: gettypefields (](icordebugprocess5-gettypefields-method.md) para obtener información sobre los campos de este tipo.</span><span class="sxs-lookup"><span data-stu-id="dfcdb-117">If `numFields` is greater than zero, you can call the [ICorDebugProcess5::GetTypeFields](icordebugprocess5-gettypefields-method.md) method to obtain information about the fields in this type.</span></span> <span data-ttu-id="dfcdb-118">Si `type` es `ELEMENT_TYPE_STRING`, `ELEMENT_TYPE_ARRAY` o `ELEMENT_TYPE_SZARRAY`, el tamaño de los objetos de este tipo es variable y se puede pasar la estructura [COR_TYPEID](cor-typeid-structure.md) al método [ICorDebugProcess5::GetArrayLayout](icordebugprocess5-getarraylayout-method.md).</span><span class="sxs-lookup"><span data-stu-id="dfcdb-118">If `type` is `ELEMENT_TYPE_STRING`, `ELEMENT_TYPE_ARRAY`, or `ELEMENT_TYPE_SZARRAY`, the size of objects of this type is variable, and you can pass the [COR_TYPEID](cor-typeid-structure.md) structure to the [ICorDebugProcess5::GetArrayLayout](icordebugprocess5-getarraylayout-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dfcdb-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dfcdb-119">Requirements</span></span>  
 <span data-ttu-id="dfcdb-120">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dfcdb-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfcdb-121">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="dfcdb-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dfcdb-122">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dfcdb-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dfcdb-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfcdb-123">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfcdb-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="dfcdb-124">See also</span></span>

- [<span data-ttu-id="dfcdb-125">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="dfcdb-125">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="dfcdb-126">Depuración</span><span class="sxs-lookup"><span data-stu-id="dfcdb-126">Debugging</span></span>](index.md)
