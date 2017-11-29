---
title: "CorManifestResourceFlags (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorManifestResourceFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: CorManifestResourceFlags
helpviewer_keywords: CorManifestResourceFlags enumeration [.NET Framework metadata]
ms.assetid: 1b0306b7-622b-4b57-8edc-3c713bb147ae
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5cdaba8b1186d1720ff8b64f50a8effc4691fe8c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="cormanifestresourceflags-enumeration"></a><span data-ttu-id="58e95-102">CorManifestResourceFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="58e95-102">CorManifestResourceFlags Enumeration</span></span>
<span data-ttu-id="58e95-103">Indica la visibilidad de los recursos codificados en un manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="58e95-103">Indicates the visibility of resources encoded in an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58e95-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="58e95-104">Syntax</span></span>  
  
```  
typedef enum CorManifestResourceFlags {  
  
    mrVisibilityMask        =   0x0007,  
    mrPublic                =   0x0001,  
    mrPrivate               =   0x0002  
  
} CorManifestResourceFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="58e95-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="58e95-105">Members</span></span>  
  
|<span data-ttu-id="58e95-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="58e95-106">Member</span></span>|<span data-ttu-id="58e95-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="58e95-107">Description</span></span>|  
|------------|-----------------|  
|`mrVisibilityMask`|<span data-ttu-id="58e95-108">Reservado.</span><span class="sxs-lookup"><span data-stu-id="58e95-108">Reserved.</span></span>|  
|`mrPublic`|<span data-ttu-id="58e95-109">Los recursos son públicos.</span><span class="sxs-lookup"><span data-stu-id="58e95-109">The resources are public.</span></span>|  
|`mrPrivate`|<span data-ttu-id="58e95-110">Los recursos son privados.</span><span class="sxs-lookup"><span data-stu-id="58e95-110">The resources are private.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="58e95-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="58e95-111">Requirements</span></span>  
 <span data-ttu-id="58e95-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58e95-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58e95-113">**Encabezado:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="58e95-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="58e95-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58e95-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58e95-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="58e95-115">See Also</span></span>  
 [<span data-ttu-id="58e95-116">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="58e95-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
