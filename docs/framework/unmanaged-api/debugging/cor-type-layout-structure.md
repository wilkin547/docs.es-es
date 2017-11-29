---
title: COR_TYPE_LAYOUT (Estructura)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_TYPE_LAYOUT
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_TYPE_LAYOUT
helpviewer_keywords: COR_TYPE_LAYOUT structure [.NET Framework debugging]
ms.assetid: 43a7addd-f25a-4049-9907-abec3eb17af2
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fc23e33abf47d19792c25d36a62bf95a098ee7a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="cortypelayout-structure"></a><span data-ttu-id="6e40c-102">COR_TYPE_LAYOUT (Estructura)</span><span class="sxs-lookup"><span data-stu-id="6e40c-102">COR_TYPE_LAYOUT Structure</span></span>
<span data-ttu-id="6e40c-103">Proporciona información sobre la distribución de un objeto en la memoria.</span><span class="sxs-lookup"><span data-stu-id="6e40c-103">Provides information about the layout of an object in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e40c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6e40c-104">Syntax</span></span>  
  
```  
typedef struct COR_TYPE_LAYOUT {  
    COR_TYPEID parentID;  
    ULONG32 objectSize;  
    ULONG32 numFields;  
    ULONG32 boxOffset;  
    CorElementType type;  
} COR_TYPE_LAYOUT;  
```  
  
## <a name="members"></a><span data-ttu-id="6e40c-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="6e40c-105">Members</span></span>  
  
|<span data-ttu-id="6e40c-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="6e40c-106">Member</span></span>|<span data-ttu-id="6e40c-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="6e40c-107">Description</span></span>|  
|------------|-----------------|  
|`parentID`|<span data-ttu-id="6e40c-108">El identificador del tipo primario para este tipo.</span><span class="sxs-lookup"><span data-stu-id="6e40c-108">The identifier of the parent type to this type.</span></span> <span data-ttu-id="6e40c-109">Se usará el identificador de tipo NULL (símbolo1 = 0, símbolo2 = 0) si el identificador de tipo corresponde a <xref:System.Object?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6e40c-109">This will be the NULL type id (token1= 0, token2 = 0) if the type id corresponds to <xref:System.Object?displayProperty=nameWithType>.</span></span>|  
|`objectSize`|<span data-ttu-id="6e40c-110">El tamaño de la base de un objeto de este tipo.</span><span class="sxs-lookup"><span data-stu-id="6e40c-110">The base size of an object of this type.</span></span> <span data-ttu-id="6e40c-111">Este es el tamaño total para los objetos de tamaño no variable.</span><span class="sxs-lookup"><span data-stu-id="6e40c-111">This is the total size for non-variable sized objects.</span></span>|  
|`numFields`|<span data-ttu-id="6e40c-112">El número de campos que se incluyen en los objetos de este tipo.</span><span class="sxs-lookup"><span data-stu-id="6e40c-112">The number of fields included in objects of this type.</span></span>|  
|`boxOffset`|<span data-ttu-id="6e40c-113">Si este tipo es una conversión boxing, el principio de desplazamiento de campos de un objeto.</span><span class="sxs-lookup"><span data-stu-id="6e40c-113">If this type is boxed, the beginning offset of an object's fields.</span></span> <span data-ttu-id="6e40c-114">Este campo es válida únicamente para los tipos de valor como tipos primitivos y las estructuras.</span><span class="sxs-lookup"><span data-stu-id="6e40c-114">This field is valid only for value types such as primitives and structures.</span></span>|  
|`type`|<span data-ttu-id="6e40c-115">CorElementType al que pertenece este tipo.</span><span class="sxs-lookup"><span data-stu-id="6e40c-115">The CorElementType to which this type belongs.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e40c-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6e40c-116">Remarks</span></span>  
 <span data-ttu-id="6e40c-117">Si `numFields` es mayor que cero, se puede llamar a la [icordebugprocess5:: Gettypefields](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md) método para obtener información sobre los campos de este tipo.</span><span class="sxs-lookup"><span data-stu-id="6e40c-117">If `numFields` is greater than zero, you can call the [ICorDebugProcess5::GetTypeFields](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md) method to obtain information about the fields in this type.</span></span> <span data-ttu-id="6e40c-118">Si `type` es `ELEMENT_TYPE_STRING`, `ELEMENT_TYPE_ARRAY`, o `ELEMENT_TYPE_SZARRAY`, el tamaño de los objetos de este tipo es variable y se puede pasar el [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) estructura especificada en el [icordebugprocess5:: Getarraylayout ](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md) (método).</span><span class="sxs-lookup"><span data-stu-id="6e40c-118">If `type` is `ELEMENT_TYPE_STRING`, `ELEMENT_TYPE_ARRAY`, or `ELEMENT_TYPE_SZARRAY`, the size of objects of this type is variable, and you can pass the [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) structure to the [ICorDebugProcess5::GetArrayLayout](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e40c-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6e40c-119">Requirements</span></span>  
 <span data-ttu-id="6e40c-120">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e40c-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e40c-121">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6e40c-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6e40c-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6e40c-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6e40c-123">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e40c-123">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e40c-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="6e40c-124">See Also</span></span>  
 [<span data-ttu-id="6e40c-125">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="6e40c-125">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="6e40c-126">Depuración</span><span class="sxs-lookup"><span data-stu-id="6e40c-126">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
