---
title: CorEventAttr (Enumeración)
ms.date: 03/30/2017
api_name:
- CorEventAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorEventAttr
helpviewer_keywords:
- CorEventAttr enumeration [.NET Framework metadata]
ms.assetid: dc2b3281-3820-487e-930d-350b66dc6417
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a1a50c15071ea1e696e508c779309225c7e7bfa2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097826"
---
# <a name="coreventattr-enumeration"></a><span data-ttu-id="a5403-102">CorEventAttr (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="a5403-102">CorEventAttr Enumeration</span></span>
<span data-ttu-id="a5403-103">Contiene valores que describen los metadatos de un evento.</span><span class="sxs-lookup"><span data-stu-id="a5403-103">Contains values that describe the metadata of an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5403-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a5403-104">Syntax</span></span>  
  
```  
typedef enum CorEventAttr {  
  
    evSpecialName           =   0x0200,  
  
    evReservedMask          =   0x0400,  
    evRTSpecialName         =   0x0400,  
  
} CorEventAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="a5403-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="a5403-105">Members</span></span>  
  
|<span data-ttu-id="a5403-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="a5403-106">Member</span></span>|<span data-ttu-id="a5403-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a5403-107">Description</span></span>|  
|------------|-----------------|  
|`evSpecialName`|<span data-ttu-id="a5403-108">Especifica que el evento es especial y que su nombre describe cómo.</span><span class="sxs-lookup"><span data-stu-id="a5403-108">Specifies that the event is special, and that its name describes how.</span></span>|  
|`evReservedMask`|<span data-ttu-id="a5403-109">Reservado para uso interno por common language runtime.</span><span class="sxs-lookup"><span data-stu-id="a5403-109">Reserved for internal use by the common language runtime.</span></span>|  
|`evRTSpecialName`|<span data-ttu-id="a5403-110">Especifica que common language runtime debe comprobar la codificación del nombre del evento.</span><span class="sxs-lookup"><span data-stu-id="a5403-110">Specifies that the common language runtime should check the encoding of the event name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a5403-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a5403-111">Requirements</span></span>  
 <span data-ttu-id="a5403-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5403-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5403-113">**Encabezado**: CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="a5403-113">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="a5403-114">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="a5403-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a5403-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5403-115">See also</span></span>

- [<span data-ttu-id="a5403-116">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="a5403-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
