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
ms.openlocfilehash: 7efb2c3e8033b8bd8fa736a29b2ab9b3bedebeaa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59109647"
---
# <a name="cortypelayout-structure"></a><span data-ttu-id="8c1d2-102">COR_TYPE_LAYOUT (Estructura)</span><span class="sxs-lookup"><span data-stu-id="8c1d2-102">COR_TYPE_LAYOUT Structure</span></span>
<span data-ttu-id="8c1d2-103">Proporciona información sobre la distribución de un objeto en la memoria.</span><span class="sxs-lookup"><span data-stu-id="8c1d2-103">Provides information about the layout of an object in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c1d2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8c1d2-104">Syntax</span></span>  
  
```  
typedef struct COR_TYPE_LAYOUT {  
    COR_TYPEID parentID;  
    ULONG32 objectSize;  
    ULONG32 numFields;  
    ULONG32 boxOffset;  
    CorElementType type;  
} COR_TYPE_LAYOUT;  
```  
  
## <a name="members"></a><span data-ttu-id="8c1d2-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="8c1d2-105">Members</span></span>  
  
|<span data-ttu-id="8c1d2-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="8c1d2-106">Member</span></span>|<span data-ttu-id="8c1d2-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="8c1d2-107">Description</span></span>|  
|------------|-----------------|  
|`parentID`|<span data-ttu-id="8c1d2-108">El identificador del tipo primario para este tipo.</span><span class="sxs-lookup"><span data-stu-id="8c1d2-108">The identifier of the parent type to this type.</span></span> <span data-ttu-id="8c1d2-109">Este será el identificador de tipo NULL (símbolo1 = 0, símbolo2 = 0) si el identificador de tipo corresponde a <xref:System.Object?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8c1d2-109">This will be the NULL type id (token1= 0, token2 = 0) if the type id corresponds to <xref:System.Object?displayProperty=nameWithType>.</span></span>|  
|`objectSize`|<span data-ttu-id="8c1d2-110">El tamaño de la base de un objeto de este tipo.</span><span class="sxs-lookup"><span data-stu-id="8c1d2-110">The base size of an object of this type.</span></span> <span data-ttu-id="8c1d2-111">Este es el tamaño total de objetos de tamaño no variable.</span><span class="sxs-lookup"><span data-stu-id="8c1d2-111">This is the total size for non-variable sized objects.</span></span>|  
|`numFields`|<span data-ttu-id="8c1d2-112">El número de campos incluidos en los objetos de este tipo.</span><span class="sxs-lookup"><span data-stu-id="8c1d2-112">The number of fields included in objects of this type.</span></span>|  
|`boxOffset`|<span data-ttu-id="8c1d2-113">Si se aplica este tipo, el principio de desplazamiento de campos de un objeto.</span><span class="sxs-lookup"><span data-stu-id="8c1d2-113">If this type is boxed, the beginning offset of an object's fields.</span></span> <span data-ttu-id="8c1d2-114">Este campo es válido sólo para los tipos de valor como tipos primitivos y las estructuras.</span><span class="sxs-lookup"><span data-stu-id="8c1d2-114">This field is valid only for value types such as primitives and structures.</span></span>|  
|`type`|<span data-ttu-id="8c1d2-115">El CorElementType al que pertenece este tipo.</span><span class="sxs-lookup"><span data-stu-id="8c1d2-115">The CorElementType to which this type belongs.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c1d2-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8c1d2-116">Remarks</span></span>  
 <span data-ttu-id="8c1d2-117">Si `numFields` es mayor que cero, se puede llamar a la [Icordebugprocess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md) método para obtener información acerca de los campos de este tipo.</span><span class="sxs-lookup"><span data-stu-id="8c1d2-117">If `numFields` is greater than zero, you can call the [ICorDebugProcess5::GetTypeFields](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md) method to obtain information about the fields in this type.</span></span> <span data-ttu-id="8c1d2-118">Si `type` es `ELEMENT_TYPE_STRING`, `ELEMENT_TYPE_ARRAY`, o `ELEMENT_TYPE_SZARRAY`, el tamaño de los objetos de este tipo es variable y puede pasar la [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) estructura a la [Icordebugprocess5 ](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="8c1d2-118">If `type` is `ELEMENT_TYPE_STRING`, `ELEMENT_TYPE_ARRAY`, or `ELEMENT_TYPE_SZARRAY`, the size of objects of this type is variable, and you can pass the [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) structure to the [ICorDebugProcess5::GetArrayLayout](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c1d2-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8c1d2-119">Requirements</span></span>  
 <span data-ttu-id="8c1d2-120">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c1d2-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c1d2-121">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8c1d2-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8c1d2-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c1d2-122">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="8c1d2-123">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="8c1d2-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8c1d2-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="8c1d2-124">See also</span></span>

- [<span data-ttu-id="8c1d2-125">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="8c1d2-125">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="8c1d2-126">Depuración</span><span class="sxs-lookup"><span data-stu-id="8c1d2-126">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
