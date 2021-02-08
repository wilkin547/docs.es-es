---
description: 'Más información sobre: enumeración CorPropertyAttr ('
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
ms.openlocfilehash: 1f3e2fccb11a067c6c46350a2c36d47007875755
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784241"
---
# <a name="corpropertyattr-enumeration"></a><span data-ttu-id="28e4a-103">CorPropertyAttr (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="28e4a-103">CorPropertyAttr Enumeration</span></span>

<span data-ttu-id="28e4a-104">Contiene valores que describen los metadatos de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="28e4a-104">Contains values that describe the metadata of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28e4a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="28e4a-105">Syntax</span></span>  
  
```cpp  
typedef enum CorPropertyAttr {  
  
    prSpecialName           =   0x0200,
    prReservedMask          =   0xf400,  
    prRTSpecialName         =   0x0400,  
    prHasDefault            =   0x1000,  
    prUnused                =   0xe9ff  
  
} CorPropertyAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="28e4a-106">Members</span><span class="sxs-lookup"><span data-stu-id="28e4a-106">Members</span></span>  
  
|<span data-ttu-id="28e4a-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="28e4a-107">Member</span></span>|<span data-ttu-id="28e4a-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="28e4a-108">Description</span></span>|  
|------------|-----------------|  
|`prSpecialName`|<span data-ttu-id="28e4a-109">Especifica que la propiedad es especial y que su nombre describe cómo.</span><span class="sxs-lookup"><span data-stu-id="28e4a-109">Specifies that the property is special, and that its name describes how.</span></span>|  
|`prReservedMask`|<span data-ttu-id="28e4a-110">Reservado para uso interno por el Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="28e4a-110">Reserved for internal use by the common language runtime.</span></span>|  
|`prRTSpecialName`|<span data-ttu-id="28e4a-111">Especifica que las API internas de metadatos de Common Language Runtime deben comprobar la codificación del nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="28e4a-111">Specifies that the common language runtime metadata internal APIs should check the encoding of the property name.</span></span>|  
|`prHasDefault`|<span data-ttu-id="28e4a-112">Especifica que la propiedad tiene un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="28e4a-112">Specifies that the property has a default value.</span></span>|  
|`prUnused`|<span data-ttu-id="28e4a-113">Sin usar.</span><span class="sxs-lookup"><span data-stu-id="28e4a-113">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="28e4a-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="28e4a-114">Requirements</span></span>  

 <span data-ttu-id="28e4a-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28e4a-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28e4a-116">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="28e4a-116">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="28e4a-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28e4a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28e4a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="28e4a-118">See also</span></span>

- [<span data-ttu-id="28e4a-119">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="28e4a-119">Metadata Enumerations</span></span>](metadata-enumerations.md)
