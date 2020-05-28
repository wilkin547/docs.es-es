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
ms.openlocfilehash: b6651f30e0df3a5ffc29d310b9067e76761dcf01
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007538"
---
# <a name="corpropertyattr-enumeration"></a><span data-ttu-id="f29db-102">CorPropertyAttr (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="f29db-102">CorPropertyAttr Enumeration</span></span>
<span data-ttu-id="f29db-103">Contiene valores que describen los metadatos de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="f29db-103">Contains values that describe the metadata of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f29db-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f29db-104">Syntax</span></span>  
  
```cpp  
typedef enum CorPropertyAttr {  
  
    prSpecialName           =   0x0200,
    prReservedMask          =   0xf400,  
    prRTSpecialName         =   0x0400,  
    prHasDefault            =   0x1000,  
    prUnused                =   0xe9ff  
  
} CorPropertyAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="f29db-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="f29db-105">Members</span></span>  
  
|<span data-ttu-id="f29db-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="f29db-106">Member</span></span>|<span data-ttu-id="f29db-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f29db-107">Description</span></span>|  
|------------|-----------------|  
|`prSpecialName`|<span data-ttu-id="f29db-108">Especifica que la propiedad es especial y que su nombre describe cómo.</span><span class="sxs-lookup"><span data-stu-id="f29db-108">Specifies that the property is special, and that its name describes how.</span></span>|  
|`prReservedMask`|<span data-ttu-id="f29db-109">Reservado para uso interno por el Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="f29db-109">Reserved for internal use by the common language runtime.</span></span>|  
|`prRTSpecialName`|<span data-ttu-id="f29db-110">Especifica que las API internas de metadatos de Common Language Runtime deben comprobar la codificación del nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="f29db-110">Specifies that the common language runtime metadata internal APIs should check the encoding of the property name.</span></span>|  
|`prHasDefault`|<span data-ttu-id="f29db-111">Especifica que la propiedad tiene un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="f29db-111">Specifies that the property has a default value.</span></span>|  
|`prUnused`|<span data-ttu-id="f29db-112">Sin usar.</span><span class="sxs-lookup"><span data-stu-id="f29db-112">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f29db-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f29db-113">Requirements</span></span>  
 <span data-ttu-id="f29db-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f29db-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f29db-115">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="f29db-115">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="f29db-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f29db-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f29db-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f29db-117">See also</span></span>

- [<span data-ttu-id="f29db-118">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="f29db-118">Metadata Enumerations</span></span>](metadata-enumerations.md)
