---
description: 'Más información sobre: enumeración CorManifestResourceFlags ('
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
ms.openlocfilehash: a863e1248bf5274e12fc16d2edea6b28dd493963
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784410"
---
# <a name="cormanifestresourceflags-enumeration"></a><span data-ttu-id="4d5fc-103">CorManifestResourceFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="4d5fc-103">CorManifestResourceFlags Enumeration</span></span>

<span data-ttu-id="4d5fc-104">Indica la visibilidad de los recursos codificados en un manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4d5fc-104">Indicates the visibility of resources encoded in an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d5fc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4d5fc-105">Syntax</span></span>  
  
```cpp  
typedef enum CorManifestResourceFlags {  
  
    mrVisibilityMask        =   0x0007,  
    mrPublic                =   0x0001,  
    mrPrivate               =   0x0002  
  
} CorManifestResourceFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="4d5fc-106">Members</span><span class="sxs-lookup"><span data-stu-id="4d5fc-106">Members</span></span>  
  
|<span data-ttu-id="4d5fc-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="4d5fc-107">Member</span></span>|<span data-ttu-id="4d5fc-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="4d5fc-108">Description</span></span>|  
|------------|-----------------|  
|`mrVisibilityMask`|<span data-ttu-id="4d5fc-109">Reservado.</span><span class="sxs-lookup"><span data-stu-id="4d5fc-109">Reserved.</span></span>|  
|`mrPublic`|<span data-ttu-id="4d5fc-110">Los recursos son públicos.</span><span class="sxs-lookup"><span data-stu-id="4d5fc-110">The resources are public.</span></span>|  
|`mrPrivate`|<span data-ttu-id="4d5fc-111">Los recursos son privados.</span><span class="sxs-lookup"><span data-stu-id="4d5fc-111">The resources are private.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4d5fc-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4d5fc-112">Requirements</span></span>  

 <span data-ttu-id="4d5fc-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d5fc-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d5fc-114">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="4d5fc-114">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="4d5fc-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d5fc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d5fc-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d5fc-116">See also</span></span>

- [<span data-ttu-id="4d5fc-117">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="4d5fc-117">Metadata Enumerations</span></span>](metadata-enumerations.md)
