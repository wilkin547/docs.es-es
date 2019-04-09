---
title: CorManifestResourceFlags (Enumeración)
ms.date: 03/30/2017
api_name:
- CorManifestResourceFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorManifestResourceFlags
helpviewer_keywords:
- CorManifestResourceFlags enumeration [.NET Framework metadata]
ms.assetid: 1b0306b7-622b-4b57-8edc-3c713bb147ae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 204f04b1ed1ea293639e0b9826f7e0ce6f384763
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59198548"
---
# <a name="cormanifestresourceflags-enumeration"></a><span data-ttu-id="5e26d-102">CorManifestResourceFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="5e26d-102">CorManifestResourceFlags Enumeration</span></span>
<span data-ttu-id="5e26d-103">Indica la visibilidad de los recursos codificados en un manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5e26d-103">Indicates the visibility of resources encoded in an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e26d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5e26d-104">Syntax</span></span>  
  
```  
typedef enum CorManifestResourceFlags {  
  
    mrVisibilityMask        =   0x0007,  
    mrPublic                =   0x0001,  
    mrPrivate               =   0x0002  
  
} CorManifestResourceFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="5e26d-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="5e26d-105">Members</span></span>  
  
|<span data-ttu-id="5e26d-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="5e26d-106">Member</span></span>|<span data-ttu-id="5e26d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="5e26d-107">Description</span></span>|  
|------------|-----------------|  
|`mrVisibilityMask`|<span data-ttu-id="5e26d-108">Reservado.</span><span class="sxs-lookup"><span data-stu-id="5e26d-108">Reserved.</span></span>|  
|`mrPublic`|<span data-ttu-id="5e26d-109">Los recursos son públicos.</span><span class="sxs-lookup"><span data-stu-id="5e26d-109">The resources are public.</span></span>|  
|`mrPrivate`|<span data-ttu-id="5e26d-110">Los recursos son privados.</span><span class="sxs-lookup"><span data-stu-id="5e26d-110">The resources are private.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5e26d-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5e26d-111">Requirements</span></span>  
 <span data-ttu-id="5e26d-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e26d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e26d-113">**Encabezado**: CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="5e26d-113">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="5e26d-114">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="5e26d-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5e26d-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e26d-115">See also</span></span>

- [<span data-ttu-id="5e26d-116">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="5e26d-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
