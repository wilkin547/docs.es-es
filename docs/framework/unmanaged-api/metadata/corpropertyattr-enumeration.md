---
title: "CorPropertyAttr (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorPropertyAttr
api_location: mscoree.dll
api_type: COM
f1_keywords: CorPropertyAttr
helpviewer_keywords: CorPropertyAttr enumeration [.NET Framework metadata]
ms.assetid: 58ac8202-854d-4efd-acfb-d2da8b446e12
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a87676064f39dc01d04e881bbf46476fb12a1c65
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="corpropertyattr-enumeration"></a><span data-ttu-id="c313c-102">CorPropertyAttr (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="c313c-102">CorPropertyAttr Enumeration</span></span>
<span data-ttu-id="c313c-103">Contiene valores que describen los metadatos de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="c313c-103">Contains values that describe the metadata of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c313c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c313c-104">Syntax</span></span>  
  
```  
typedef enum CorPropertyAttr {  
  
    prSpecialName           =   0x0200,   
    prReservedMask          =   0xf400,  
    prRTSpecialName         =   0x0400,  
    prHasDefault            =   0x1000,  
    prUnused                =   0xe9ff  
  
} CorPropertyAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="c313c-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="c313c-105">Members</span></span>  
  
|<span data-ttu-id="c313c-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="c313c-106">Member</span></span>|<span data-ttu-id="c313c-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c313c-107">Description</span></span>|  
|------------|-----------------|  
|`prSpecialName`|<span data-ttu-id="c313c-108">Especifica que la propiedad es especial, y que su nombre describe cómo.</span><span class="sxs-lookup"><span data-stu-id="c313c-108">Specifies that the property is special, and that its name describes how.</span></span>|  
|`prReservedMask`|<span data-ttu-id="c313c-109">Reservado para uso interno por common language runtime.</span><span class="sxs-lookup"><span data-stu-id="c313c-109">Reserved for internal use by the common language runtime.</span></span>|  
|`prRTSpecialName`|<span data-ttu-id="c313c-110">Especifica que los metadatos de common language runtime API internas deben comprobar la codificación del nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="c313c-110">Specifies that the common language runtime metadata internal APIs should check the encoding of the property name.</span></span>|  
|`prHasDefault`|<span data-ttu-id="c313c-111">Especifica que la propiedad tiene un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c313c-111">Specifies that the property has a default value.</span></span>|  
|`prUnused`|<span data-ttu-id="c313c-112">Sin usar.</span><span class="sxs-lookup"><span data-stu-id="c313c-112">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c313c-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c313c-113">Requirements</span></span>  
 <span data-ttu-id="c313c-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c313c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c313c-115">**Encabezado:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="c313c-115">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="c313c-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c313c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c313c-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="c313c-117">See Also</span></span>  
 [<span data-ttu-id="c313c-118">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="c313c-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
