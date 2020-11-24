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
ms.openlocfilehash: f8334cb44042e21c086bc05c723e99b0c079fa2c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677068"
---
# <a name="cormanifestresourceflags-enumeration"></a><span data-ttu-id="c4150-102">CorManifestResourceFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="c4150-102">CorManifestResourceFlags Enumeration</span></span>

<span data-ttu-id="c4150-103">Indica la visibilidad de los recursos codificados en un manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c4150-103">Indicates the visibility of resources encoded in an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4150-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c4150-104">Syntax</span></span>  
  
```cpp  
typedef enum CorManifestResourceFlags {  
  
    mrVisibilityMask        =   0x0007,  
    mrPublic                =   0x0001,  
    mrPrivate               =   0x0002  
  
} CorManifestResourceFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="c4150-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="c4150-105">Members</span></span>  
  
|<span data-ttu-id="c4150-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="c4150-106">Member</span></span>|<span data-ttu-id="c4150-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c4150-107">Description</span></span>|  
|------------|-----------------|  
|`mrVisibilityMask`|<span data-ttu-id="c4150-108">Reservado.</span><span class="sxs-lookup"><span data-stu-id="c4150-108">Reserved.</span></span>|  
|`mrPublic`|<span data-ttu-id="c4150-109">Los recursos son públicos.</span><span class="sxs-lookup"><span data-stu-id="c4150-109">The resources are public.</span></span>|  
|`mrPrivate`|<span data-ttu-id="c4150-110">Los recursos son privados.</span><span class="sxs-lookup"><span data-stu-id="c4150-110">The resources are private.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c4150-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c4150-111">Requirements</span></span>  

 <span data-ttu-id="c4150-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4150-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4150-113">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="c4150-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="c4150-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4150-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4150-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c4150-115">See also</span></span>

- [<span data-ttu-id="c4150-116">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="c4150-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
