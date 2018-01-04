---
title: "CorNativeLinkType (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorNativeLinkType
api_location: mscoree.dll
api_type: COM
f1_keywords: CorNativeLinkType
helpviewer_keywords: CorNativeLinkType enumeration [.NET Framework metadata]
ms.assetid: 4f86ff37-2dab-4e64-819a-76b3bfe828ff
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f19a4366958249881c1f4c33919f239f33c21b21
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="cornativelinktype-enumeration"></a><span data-ttu-id="33ba8-102">CorNativeLinkType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="33ba8-102">CorNativeLinkType Enumeration</span></span>
<span data-ttu-id="33ba8-103">Proporciona valores que indican el tipo vinculado en código nativo.</span><span class="sxs-lookup"><span data-stu-id="33ba8-103">Provides values that indicate the type linked in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33ba8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="33ba8-104">Syntax</span></span>  
  
```  
typedef enum   
{  
    nltNone       = 1,  
    nltAnsi       = 2,  
    nltUnicode    = 3,  
    nltAuto       = 4,  
    nltOle        = 5,  
    nltMaxValue   = 7  
} CorNativeLinkType;  
```  
  
## <a name="members"></a><span data-ttu-id="33ba8-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="33ba8-105">Members</span></span>  
  
|<span data-ttu-id="33ba8-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="33ba8-106">Member</span></span>|<span data-ttu-id="33ba8-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="33ba8-107">Description</span></span>|  
|------------|-----------------|  
|`nltNone`|<span data-ttu-id="33ba8-108">Indica que no se especifica ninguna de las palabras clave.</span><span class="sxs-lookup"><span data-stu-id="33ba8-108">Indicates that none of the keywords are specified.</span></span>|  
|`nltAnsi`|<span data-ttu-id="33ba8-109">Indica que se ha especificado una palabra clave ANSI.</span><span class="sxs-lookup"><span data-stu-id="33ba8-109">Indicates that an ANSI keyword is specified.</span></span>|  
|`nltUnicode`|<span data-ttu-id="33ba8-110">Indica que se ha especificado una palabra clave Unicode</span><span class="sxs-lookup"><span data-stu-id="33ba8-110">Indicates that a Unicode keyword is specified</span></span>|  
|`nltAuto`|<span data-ttu-id="33ba8-111">Indica que se ha especificado una palabra clave auto.</span><span class="sxs-lookup"><span data-stu-id="33ba8-111">Indicates that an auto keyword is specified.</span></span>|  
|`nltOle`|<span data-ttu-id="33ba8-112">Indica que se ha especificado una palabra clave OLE.</span><span class="sxs-lookup"><span data-stu-id="33ba8-112">Indicates that an OLE keyword is specified.</span></span>|  
|`nltMaxValue`|<span data-ttu-id="33ba8-113">No usado.</span><span class="sxs-lookup"><span data-stu-id="33ba8-113">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="33ba8-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="33ba8-114">Requirements</span></span>  
 <span data-ttu-id="33ba8-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33ba8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33ba8-116">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="33ba8-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="33ba8-117">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="33ba8-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="33ba8-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33ba8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33ba8-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="33ba8-119">See Also</span></span>  
 [<span data-ttu-id="33ba8-120">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="33ba8-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
