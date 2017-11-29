---
title: "CorRefToDefCheck (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorRefToDefCheck
api_location: mscoree.dll
api_type: COM
f1_keywords: CorRefToDefCheck
helpviewer_keywords: CorRefToDefCheck enumeration [.NET Framework metadata]
ms.assetid: f9a80f1a-55af-4459-b095-8441aae16119
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5144cd3ac261647c04ec7e3e27e28618c94fb439
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="correftodefcheck-enumeration"></a><span data-ttu-id="ca80a-102">CorRefToDefCheck (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="ca80a-102">CorRefToDefCheck Enumeration</span></span>
<span data-ttu-id="ca80a-103">Especifica marcas para controlar qué elementos referenciados se convierten en sus definiciones para optimizar el código.</span><span class="sxs-lookup"><span data-stu-id="ca80a-103">Specifies flags to control which referenced items are converted to their definitions in order to optimize the code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca80a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ca80a-104">Syntax</span></span>  
  
```  
typedef enum CorRefToDefCheck {  
    MDRefToDefDefault           = 0x00000003,  
    MDRefToDefAll               = 0xffffffff,  
    MDRefToDefNone              = 0x00000000,  
    MDTypeRefToDef              = 0x00000001,  
    MDMemberRefToDef            = 0x00000002  
} CorRefToDefCheck;  
```  
  
## <a name="members"></a><span data-ttu-id="ca80a-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="ca80a-105">Members</span></span>  
  
|<span data-ttu-id="ca80a-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="ca80a-106">Member</span></span>|<span data-ttu-id="ca80a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ca80a-107">Description</span></span>|  
|------------|-----------------|  
|`MDRefToDefDefault`|<span data-ttu-id="ca80a-108">Especifica que las referencias de tipos y las referencias de miembro deben convertirse en definiciones.</span><span class="sxs-lookup"><span data-stu-id="ca80a-108">Specifies that type references and member references should be converted to definitions.</span></span> <span data-ttu-id="ca80a-109">Este es el valor predeterminado (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).</span><span class="sxs-lookup"><span data-stu-id="ca80a-109">This is the default value (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).</span></span>|  
|`MDRefToDefAll`|<span data-ttu-id="ca80a-110">Especifica que se deben convertir todos los elementos que se hace referencia a las definiciones.</span><span class="sxs-lookup"><span data-stu-id="ca80a-110">Specifies that all referenced items should be converted to definitions.</span></span>|  
|`MDRefToDefNone`|<span data-ttu-id="ca80a-111">Especifica que no hay elementos que se hace referencia deben convertirse en definiciones.</span><span class="sxs-lookup"><span data-stu-id="ca80a-111">Specifies that no referenced items should be converted to definitions.</span></span>|  
|`MDTypeRefToDef`|<span data-ttu-id="ca80a-112">Especifica que sólo las referencias de tipos se deben convertir a las definiciones de tipo.</span><span class="sxs-lookup"><span data-stu-id="ca80a-112">Specifies that only type references should be converted to type definitions.</span></span>|  
|`MDMemberRefToDef`|<span data-ttu-id="ca80a-113">Especifica que sólo las referencias de miembro deben convertirse en definiciones.</span><span class="sxs-lookup"><span data-stu-id="ca80a-113">Specifies that only member references should be converted to definitions.</span></span> <span data-ttu-id="ca80a-114">Es decir, las referencias de miembro deben convertirse en definiciones de método o definiciones de campo.</span><span class="sxs-lookup"><span data-stu-id="ca80a-114">That is, member references should be converted to either method definitions or field definitions.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ca80a-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ca80a-115">Requirements</span></span>  
 <span data-ttu-id="ca80a-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca80a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca80a-117">**Encabezado:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="ca80a-117">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="ca80a-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca80a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca80a-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca80a-119">See Also</span></span>  
 [<span data-ttu-id="ca80a-120">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="ca80a-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
