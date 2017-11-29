---
title: COR_FIELD (Estructura)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_FIELD
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_FIELD
helpviewer_keywords: COR_FIELD structure [.NET Framework debugging]
ms.assetid: c0822423-a9df-4961-950d-50dcc152f863
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a01687b5a49bb64ab037dc408c8cc5bd381be589
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="corfield-structure"></a><span data-ttu-id="2ca30-102">COR_FIELD (Estructura)</span><span class="sxs-lookup"><span data-stu-id="2ca30-102">COR_FIELD Structure</span></span>
<span data-ttu-id="2ca30-103">Proporciona información sobre un campo en un objeto.</span><span class="sxs-lookup"><span data-stu-id="2ca30-103">Provides information about a field in an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ca30-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2ca30-104">Syntax</span></span>  
  
```  
typedef struct COR_FIELD{  
    mdFieldDef token;  
    ULONG32 offset;  
    COR_TYPEID id;  
    CorElementType fieldType;  
} COR_FIELD;  
```  
  
## <a name="members"></a><span data-ttu-id="2ca30-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="2ca30-105">Members</span></span>  
  
|<span data-ttu-id="2ca30-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="2ca30-106">Member</span></span>|<span data-ttu-id="2ca30-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="2ca30-107">Description</span></span>|  
|------------|-----------------|  
|`token`|<span data-ttu-id="2ca30-108">Un `mdFieldDef` símbolo (token) que puede utilizarse para obtener información de campo.</span><span class="sxs-lookup"><span data-stu-id="2ca30-108">An `mdFieldDef` token that can be used to get field information.</span></span>|  
|`offset`|<span data-ttu-id="2ca30-109">El desplazamiento, en bytes, que los datos del campo en el objeto.</span><span class="sxs-lookup"><span data-stu-id="2ca30-109">The offset, in bytes, to the field data in the object.</span></span>|  
|`id`|<span data-ttu-id="2ca30-110">A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) valor que identifica el tipo de este campo.</span><span class="sxs-lookup"><span data-stu-id="2ca30-110">A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) value that identifies the type of this field.</span></span>|  
|`fieldType`|<span data-ttu-id="2ca30-111">Un valor de enumeración CorElementType que indica el tipo del campo.</span><span class="sxs-lookup"><span data-stu-id="2ca30-111">A CorElementType enumeration value that indicates the type of the field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ca30-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2ca30-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ca30-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2ca30-113">Requirements</span></span>  
 <span data-ttu-id="2ca30-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ca30-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ca30-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2ca30-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ca30-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ca30-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ca30-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ca30-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ca30-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ca30-118">See Also</span></span>  
 [<span data-ttu-id="2ca30-119">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="2ca30-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="2ca30-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="2ca30-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
