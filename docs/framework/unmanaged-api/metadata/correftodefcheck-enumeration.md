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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 82abeb0ce3db075d794787bb1fcd5bc18321bef2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59093896"
---
# <a name="correftodefcheck-enumeration"></a><span data-ttu-id="4a230-102">CorRefToDefCheck (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="4a230-102">CorRefToDefCheck Enumeration</span></span>
<span data-ttu-id="4a230-103">Especifica marcas para controlar qué elementos referenciados se convierten en sus definiciones para optimizar el código.</span><span class="sxs-lookup"><span data-stu-id="4a230-103">Specifies flags to control which referenced items are converted to their definitions in order to optimize the code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a230-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4a230-104">Syntax</span></span>  
  
```  
typedef enum CorRefToDefCheck {  
    MDRefToDefDefault           = 0x00000003,  
    MDRefToDefAll               = 0xffffffff,  
    MDRefToDefNone              = 0x00000000,  
    MDTypeRefToDef              = 0x00000001,  
    MDMemberRefToDef            = 0x00000002  
} CorRefToDefCheck;  
```  
  
## <a name="members"></a><span data-ttu-id="4a230-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="4a230-105">Members</span></span>  
  
|<span data-ttu-id="4a230-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="4a230-106">Member</span></span>|<span data-ttu-id="4a230-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="4a230-107">Description</span></span>|  
|------------|-----------------|  
|`MDRefToDefDefault`|<span data-ttu-id="4a230-108">Especifica que se debe convertir a las definiciones de las referencias de tipo y miembro.</span><span class="sxs-lookup"><span data-stu-id="4a230-108">Specifies that type references and member references should be converted to definitions.</span></span> <span data-ttu-id="4a230-109">Este es el valor predeterminado (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).</span><span class="sxs-lookup"><span data-stu-id="4a230-109">This is the default value (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).</span></span>|  
|`MDRefToDefAll`|<span data-ttu-id="4a230-110">Especifica que se deben convertir todos los elementos que se hace referencia a las definiciones.</span><span class="sxs-lookup"><span data-stu-id="4a230-110">Specifies that all referenced items should be converted to definitions.</span></span>|  
|`MDRefToDefNone`|<span data-ttu-id="4a230-111">Especifica que no hay elementos que se hace referencia deben convertirse a las definiciones.</span><span class="sxs-lookup"><span data-stu-id="4a230-111">Specifies that no referenced items should be converted to definitions.</span></span>|  
|`MDTypeRefToDef`|<span data-ttu-id="4a230-112">Especifica que solo las referencias de tipos se deben convertir las definiciones de tipo.</span><span class="sxs-lookup"><span data-stu-id="4a230-112">Specifies that only type references should be converted to type definitions.</span></span>|  
|`MDMemberRefToDef`|<span data-ttu-id="4a230-113">Especifica que solo las referencias de miembro deben convertirse a las definiciones.</span><span class="sxs-lookup"><span data-stu-id="4a230-113">Specifies that only member references should be converted to definitions.</span></span> <span data-ttu-id="4a230-114">Es decir, las referencias de miembro deben convertirse en definiciones de método o definiciones de campo.</span><span class="sxs-lookup"><span data-stu-id="4a230-114">That is, member references should be converted to either method definitions or field definitions.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4a230-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4a230-115">Requirements</span></span>  
 <span data-ttu-id="4a230-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a230-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a230-117">**Encabezado**: CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="4a230-117">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="4a230-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a230-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a230-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a230-119">See also</span></span>

- [<span data-ttu-id="4a230-120">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="4a230-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
