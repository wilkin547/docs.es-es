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
ms.openlocfilehash: 12c594f157c803d5fc179e09a8ca6c0ef40f3f44
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099027"
---
# <a name="cor_type_layout-structure"></a><span data-ttu-id="85798-102">COR_TYPE_LAYOUT (Estructura)</span><span class="sxs-lookup"><span data-stu-id="85798-102">COR_TYPE_LAYOUT Structure</span></span>
<span data-ttu-id="85798-103">Proporciona información sobre la distribución de un objeto en la memoria.</span><span class="sxs-lookup"><span data-stu-id="85798-103">Provides information about the layout of an object in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85798-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="85798-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_TYPE_LAYOUT {  
    COR_TYPEID parentID;  
    ULONG32 objectSize;  
    ULONG32 numFields;  
    ULONG32 boxOffset;  
    CorElementType type;  
} COR_TYPE_LAYOUT;  
```  
  
## <a name="members"></a><span data-ttu-id="85798-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="85798-105">Members</span></span>  
  
|<span data-ttu-id="85798-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="85798-106">Member</span></span>|<span data-ttu-id="85798-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="85798-107">Description</span></span>|  
|------------|-----------------|  
|`parentID`|<span data-ttu-id="85798-108">Identificador del tipo primario de este tipo.</span><span class="sxs-lookup"><span data-stu-id="85798-108">The identifier of the parent type to this type.</span></span> <span data-ttu-id="85798-109">Será el identificador de tipo NULL (token1 = 0, token2 = 0) si el identificador de tipo corresponde a <xref:System.Object?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="85798-109">This will be the NULL type id (token1= 0, token2 = 0) if the type id corresponds to <xref:System.Object?displayProperty=nameWithType>.</span></span>|  
|`objectSize`|<span data-ttu-id="85798-110">Tamaño base de un objeto de este tipo.</span><span class="sxs-lookup"><span data-stu-id="85798-110">The base size of an object of this type.</span></span> <span data-ttu-id="85798-111">Es el tamaño total de los objetos de tamaño no variable.</span><span class="sxs-lookup"><span data-stu-id="85798-111">This is the total size for non-variable sized objects.</span></span>|  
|`numFields`|<span data-ttu-id="85798-112">El número de campos incluidos en los objetos de este tipo.</span><span class="sxs-lookup"><span data-stu-id="85798-112">The number of fields included in objects of this type.</span></span>|  
|`boxOffset`|<span data-ttu-id="85798-113">Si se aplica la conversión boxing a este tipo, el desplazamiento inicial de los campos de un objeto.</span><span class="sxs-lookup"><span data-stu-id="85798-113">If this type is boxed, the beginning offset of an object's fields.</span></span> <span data-ttu-id="85798-114">Este campo solo es válido para tipos de valor como primitivas y estructuras.</span><span class="sxs-lookup"><span data-stu-id="85798-114">This field is valid only for value types such as primitives and structures.</span></span>|  
|`type`|<span data-ttu-id="85798-115">El CorElementType al que pertenece este tipo.</span><span class="sxs-lookup"><span data-stu-id="85798-115">The CorElementType to which this type belongs.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85798-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="85798-116">Remarks</span></span>  
 <span data-ttu-id="85798-117">Si `numFields` es mayor que cero, puede llamar al método [ICorDebugProcess5:: gettypefields (](icordebugprocess5-gettypefields-method.md) para obtener información sobre los campos de este tipo.</span><span class="sxs-lookup"><span data-stu-id="85798-117">If `numFields` is greater than zero, you can call the [ICorDebugProcess5::GetTypeFields](icordebugprocess5-gettypefields-method.md) method to obtain information about the fields in this type.</span></span> <span data-ttu-id="85798-118">Si `type` es `ELEMENT_TYPE_STRING`, `ELEMENT_TYPE_ARRAY` o `ELEMENT_TYPE_SZARRAY`, el tamaño de los objetos de este tipo es variable y se puede pasar la estructura [COR_TYPEID](cor-typeid-structure.md) al método [ICorDebugProcess5::GetArrayLayout](icordebugprocess5-getarraylayout-method.md).</span><span class="sxs-lookup"><span data-stu-id="85798-118">If `type` is `ELEMENT_TYPE_STRING`, `ELEMENT_TYPE_ARRAY`, or `ELEMENT_TYPE_SZARRAY`, the size of objects of this type is variable, and you can pass the [COR_TYPEID](cor-typeid-structure.md) structure to the [ICorDebugProcess5::GetArrayLayout](icordebugprocess5-getarraylayout-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85798-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="85798-119">Requirements</span></span>  
 <span data-ttu-id="85798-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85798-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85798-121">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="85798-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="85798-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="85798-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="85798-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85798-123">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85798-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="85798-124">See also</span></span>

- [<span data-ttu-id="85798-125">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="85798-125">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="85798-126">Depuración</span><span class="sxs-lookup"><span data-stu-id="85798-126">Debugging</span></span>](index.md)
