---
title: CorPropertyAttr (Enumeración)
ms.date: 03/30/2017
api_name:
- CorPropertyAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPropertyAttr
helpviewer_keywords:
- CorPropertyAttr enumeration [.NET Framework metadata]
ms.assetid: 58ac8202-854d-4efd-acfb-d2da8b446e12
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f1a0fff266e964b506b2dc7c4030caa54abaa5ed
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59171826"
---
# <a name="corpropertyattr-enumeration"></a><span data-ttu-id="48672-102">CorPropertyAttr (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="48672-102">CorPropertyAttr Enumeration</span></span>
<span data-ttu-id="48672-103">Contiene valores que describen los metadatos de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="48672-103">Contains values that describe the metadata of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48672-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="48672-104">Syntax</span></span>  
  
```  
typedef enum CorPropertyAttr {  
  
    prSpecialName           =   0x0200,   
    prReservedMask          =   0xf400,  
    prRTSpecialName         =   0x0400,  
    prHasDefault            =   0x1000,  
    prUnused                =   0xe9ff  
  
} CorPropertyAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="48672-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="48672-105">Members</span></span>  
  
|<span data-ttu-id="48672-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="48672-106">Member</span></span>|<span data-ttu-id="48672-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="48672-107">Description</span></span>|  
|------------|-----------------|  
|`prSpecialName`|<span data-ttu-id="48672-108">Especifica que la propiedad es especial y que su nombre describe cómo.</span><span class="sxs-lookup"><span data-stu-id="48672-108">Specifies that the property is special, and that its name describes how.</span></span>|  
|`prReservedMask`|<span data-ttu-id="48672-109">Reservado para uso interno por common language runtime.</span><span class="sxs-lookup"><span data-stu-id="48672-109">Reserved for internal use by the common language runtime.</span></span>|  
|`prRTSpecialName`|<span data-ttu-id="48672-110">Especifica que los metadatos de common language runtime API internas deben comprobar la codificación del nombre de propiedad.</span><span class="sxs-lookup"><span data-stu-id="48672-110">Specifies that the common language runtime metadata internal APIs should check the encoding of the property name.</span></span>|  
|`prHasDefault`|<span data-ttu-id="48672-111">Especifica que la propiedad tiene un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="48672-111">Specifies that the property has a default value.</span></span>|  
|`prUnused`|<span data-ttu-id="48672-112">Sin usar.</span><span class="sxs-lookup"><span data-stu-id="48672-112">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="48672-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="48672-113">Requirements</span></span>  
 <span data-ttu-id="48672-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48672-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48672-115">**Encabezado**: CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="48672-115">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="48672-116">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="48672-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="48672-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="48672-117">See also</span></span>

- [<span data-ttu-id="48672-118">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="48672-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
