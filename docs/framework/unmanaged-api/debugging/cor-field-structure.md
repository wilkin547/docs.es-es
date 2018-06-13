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
ms.openlocfilehash: 0898936665b3b337f2fd4e4d53bcc9f6071469b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405364"
---
# <a name="corfield-structure"></a><span data-ttu-id="de4f2-102">COR_FIELD (Estructura)</span><span class="sxs-lookup"><span data-stu-id="de4f2-102">COR_FIELD Structure</span></span>
<span data-ttu-id="de4f2-103">Proporciona información sobre un campo en un objeto.</span><span class="sxs-lookup"><span data-stu-id="de4f2-103">Provides information about a field in an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de4f2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="de4f2-104">Syntax</span></span>  
  
```  
typedef struct COR_FIELD{  
    mdFieldDef token;  
    ULONG32 offset;  
    COR_TYPEID id;  
    CorElementType fieldType;  
} COR_FIELD;  
```  
  
## <a name="members"></a><span data-ttu-id="de4f2-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="de4f2-105">Members</span></span>  
  
|<span data-ttu-id="de4f2-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="de4f2-106">Member</span></span>|<span data-ttu-id="de4f2-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="de4f2-107">Description</span></span>|  
|------------|-----------------|  
|`token`|<span data-ttu-id="de4f2-108">Un `mdFieldDef` símbolo (token) que puede utilizarse para obtener información de campo.</span><span class="sxs-lookup"><span data-stu-id="de4f2-108">An `mdFieldDef` token that can be used to get field information.</span></span>|  
|`offset`|<span data-ttu-id="de4f2-109">El desplazamiento, en bytes, que los datos del campo en el objeto.</span><span class="sxs-lookup"><span data-stu-id="de4f2-109">The offset, in bytes, to the field data in the object.</span></span>|  
|`id`|<span data-ttu-id="de4f2-110">A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) valor que identifica el tipo de este campo.</span><span class="sxs-lookup"><span data-stu-id="de4f2-110">A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) value that identifies the type of this field.</span></span>|  
|`fieldType`|<span data-ttu-id="de4f2-111">Un valor de enumeración CorElementType que indica el tipo del campo.</span><span class="sxs-lookup"><span data-stu-id="de4f2-111">A CorElementType enumeration value that indicates the type of the field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de4f2-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="de4f2-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de4f2-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="de4f2-113">Requirements</span></span>  
 <span data-ttu-id="de4f2-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de4f2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de4f2-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="de4f2-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="de4f2-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de4f2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de4f2-117">**Versiones de .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de4f2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de4f2-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="de4f2-118">See Also</span></span>  
 [<span data-ttu-id="de4f2-119">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="de4f2-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="de4f2-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="de4f2-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
