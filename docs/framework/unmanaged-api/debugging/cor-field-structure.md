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
ms.workload: dotnet
ms.openlocfilehash: 09a96a22a653688540bcc2ea3a03d86e242c10f5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="corfield-structure"></a><span data-ttu-id="37a05-102">COR_FIELD (Estructura)</span><span class="sxs-lookup"><span data-stu-id="37a05-102">COR_FIELD Structure</span></span>
<span data-ttu-id="37a05-103">Proporciona información sobre un campo en un objeto.</span><span class="sxs-lookup"><span data-stu-id="37a05-103">Provides information about a field in an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37a05-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="37a05-104">Syntax</span></span>  
  
```  
typedef struct COR_FIELD{  
    mdFieldDef token;  
    ULONG32 offset;  
    COR_TYPEID id;  
    CorElementType fieldType;  
} COR_FIELD;  
```  
  
## <a name="members"></a><span data-ttu-id="37a05-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="37a05-105">Members</span></span>  
  
|<span data-ttu-id="37a05-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="37a05-106">Member</span></span>|<span data-ttu-id="37a05-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="37a05-107">Description</span></span>|  
|------------|-----------------|  
|`token`|<span data-ttu-id="37a05-108">Un `mdFieldDef` símbolo (token) que puede utilizarse para obtener información de campo.</span><span class="sxs-lookup"><span data-stu-id="37a05-108">An `mdFieldDef` token that can be used to get field information.</span></span>|  
|`offset`|<span data-ttu-id="37a05-109">El desplazamiento, en bytes, que los datos del campo en el objeto.</span><span class="sxs-lookup"><span data-stu-id="37a05-109">The offset, in bytes, to the field data in the object.</span></span>|  
|`id`|<span data-ttu-id="37a05-110">A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) valor que identifica el tipo de este campo.</span><span class="sxs-lookup"><span data-stu-id="37a05-110">A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) value that identifies the type of this field.</span></span>|  
|`fieldType`|<span data-ttu-id="37a05-111">Un valor de enumeración CorElementType que indica el tipo del campo.</span><span class="sxs-lookup"><span data-stu-id="37a05-111">A CorElementType enumeration value that indicates the type of the field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37a05-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="37a05-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37a05-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="37a05-113">Requirements</span></span>  
 <span data-ttu-id="37a05-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37a05-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37a05-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="37a05-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="37a05-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="37a05-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="37a05-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37a05-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37a05-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="37a05-118">See Also</span></span>  
 [<span data-ttu-id="37a05-119">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="37a05-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="37a05-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="37a05-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
