---
title: CorRefToDefCheck (Enumeración)
ms.date: 03/30/2017
api_name:
- CorRefToDefCheck
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRefToDefCheck
helpviewer_keywords:
- CorRefToDefCheck enumeration [.NET Framework metadata]
ms.assetid: f9a80f1a-55af-4459-b095-8441aae16119
topic_type:
- apiref
ms.openlocfilehash: e7ce604acddb88d5a15844cbce2622b21e364cc1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706117"
---
# <a name="correftodefcheck-enumeration"></a><span data-ttu-id="3d214-102">CorRefToDefCheck (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="3d214-102">CorRefToDefCheck Enumeration</span></span>

<span data-ttu-id="3d214-103">Especifica marcas para controlar qué elementos referenciados se convierten en sus definiciones para optimizar el código.</span><span class="sxs-lookup"><span data-stu-id="3d214-103">Specifies flags to control which referenced items are converted to their definitions in order to optimize the code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d214-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3d214-104">Syntax</span></span>  
  
```cpp  
typedef enum CorRefToDefCheck {  
    MDRefToDefDefault           = 0x00000003,  
    MDRefToDefAll               = 0xffffffff,  
    MDRefToDefNone              = 0x00000000,  
    MDTypeRefToDef              = 0x00000001,  
    MDMemberRefToDef            = 0x00000002  
} CorRefToDefCheck;  
```  
  
## <a name="members"></a><span data-ttu-id="3d214-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="3d214-105">Members</span></span>  
  
|<span data-ttu-id="3d214-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="3d214-106">Member</span></span>|<span data-ttu-id="3d214-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="3d214-107">Description</span></span>|  
|------------|-----------------|  
|`MDRefToDefDefault`|<span data-ttu-id="3d214-108">Especifica que las referencias de tipo y las referencias de miembro deben convertirse en definiciones.</span><span class="sxs-lookup"><span data-stu-id="3d214-108">Specifies that type references and member references should be converted to definitions.</span></span> <span data-ttu-id="3d214-109">Este es el valor predeterminado ( `MDTypeRefToDef` &#124; `MDMemberRefToDef` ).</span><span class="sxs-lookup"><span data-stu-id="3d214-109">This is the default value (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).</span></span>|  
|`MDRefToDefAll`|<span data-ttu-id="3d214-110">Especifica que todos los elementos a los que se hace referencia deben convertirse en definiciones.</span><span class="sxs-lookup"><span data-stu-id="3d214-110">Specifies that all referenced items should be converted to definitions.</span></span>|  
|`MDRefToDefNone`|<span data-ttu-id="3d214-111">Especifica que no se deben convertir los elementos a los que se hace referencia en definiciones.</span><span class="sxs-lookup"><span data-stu-id="3d214-111">Specifies that no referenced items should be converted to definitions.</span></span>|  
|`MDTypeRefToDef`|<span data-ttu-id="3d214-112">Especifica que solo se deben convertir las referencias de tipo en definiciones de tipo.</span><span class="sxs-lookup"><span data-stu-id="3d214-112">Specifies that only type references should be converted to type definitions.</span></span>|  
|`MDMemberRefToDef`|<span data-ttu-id="3d214-113">Especifica que solo se deben convertir las referencias de miembro en definiciones.</span><span class="sxs-lookup"><span data-stu-id="3d214-113">Specifies that only member references should be converted to definitions.</span></span> <span data-ttu-id="3d214-114">Es decir, las referencias de miembro se deben convertir en definiciones de método o definiciones de campo.</span><span class="sxs-lookup"><span data-stu-id="3d214-114">That is, member references should be converted to either method definitions or field definitions.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3d214-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3d214-115">Requirements</span></span>  

 <span data-ttu-id="3d214-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d214-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d214-117">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="3d214-117">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="3d214-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d214-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d214-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3d214-119">See also</span></span>

- [<span data-ttu-id="3d214-120">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="3d214-120">Metadata Enumerations</span></span>](metadata-enumerations.md)
