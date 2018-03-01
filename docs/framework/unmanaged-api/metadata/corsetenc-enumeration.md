---
title: "CorSetENC (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CorSetENC
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSetENC
helpviewer_keywords:
- CorSetENC enumeration [.NET Framework metadata]
ms.assetid: fe4150e8-071d-43fb-8e06-c3c616dbeed2
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0f39a1481361377fce3f6b55cf6c7daf8c075ce5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="corsetenc-enumeration"></a><span data-ttu-id="4eb74-102">CorSetENC (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="4eb74-102">CorSetENC Enumeration</span></span>
<span data-ttu-id="4eb74-103">Contiene valores que se usan para influir en el comportamiento durante la generación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="4eb74-103">Contains values used to influence behavior during the generation of metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4eb74-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4eb74-104">Syntax</span></span>  
  
```  
typedef enum CorSetENC {  
  
    MDSetENCOn                  = 0x00000001,  
    MDSetENCOff                 = 0x00000002,  
  
    MDUpdateENC                 = 0x00000001,  
    MDUpdateFull                = 0x00000002,  
    MDUpdateExtension           = 0x00000003,  
    MDUpdateIncremental         = 0x00000004,  
    MDUpdateDelta               = 0x00000005,  
    MDUpdateMask                = 0x00000007  
  
} CorSetENC;  
```  
  
## <a name="members"></a><span data-ttu-id="4eb74-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="4eb74-105">Members</span></span>  
  
|<span data-ttu-id="4eb74-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="4eb74-106">Member</span></span>|<span data-ttu-id="4eb74-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="4eb74-107">Description</span></span>|  
|------------|-----------------|  
|`MDSetENCOn`|<span data-ttu-id="4eb74-108">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="4eb74-108">Obsolete.</span></span>|  
|`MDSetENCOff`|<span data-ttu-id="4eb74-109">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="4eb74-109">Obsolete.</span></span>|  
|`MDUpdateENC`|<span data-ttu-id="4eb74-110">Indica que mientras que se puedan actualizar los metadatos no se puede mover los símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="4eb74-110">Indicates that whereas metadata can be updated, tokens cannot be moved.</span></span>|  
|`MDUpdateFull`|<span data-ttu-id="4eb74-111">Indica que se pueden mover tokens durante las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="4eb74-111">Indicates that tokens can be moved during updates.</span></span>|  
|`MDUpdateExtension`|<span data-ttu-id="4eb74-112">Indica que las actualizaciones pueden constar solo de adiciones.</span><span class="sxs-lookup"><span data-stu-id="4eb74-112">Indicates that updates can consist only of additions.</span></span> <span data-ttu-id="4eb74-113">No se puede mover los símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="4eb74-113">Tokens cannot be moved.</span></span>|  
|`MDUpdateIncremental`|<span data-ttu-id="4eb74-114">Indica que la compilación es incremental.</span><span class="sxs-lookup"><span data-stu-id="4eb74-114">Indicates that compilation is incremental.</span></span>|  
|`MDUpdateDelta`|<span data-ttu-id="4eb74-115">Indica que solo los metadatos modificados deben guardarse.</span><span class="sxs-lookup"><span data-stu-id="4eb74-115">Indicates that only changed metadata should be saved.</span></span>|  
|`MDUpdateMask`|<span data-ttu-id="4eb74-116">Incluye `MDUpdateENC`, `MDUpdateFull` y `MDUpdateIncremental`.</span><span class="sxs-lookup"><span data-stu-id="4eb74-116">Includes `MDUpdateENC`, `MDUpdateFull` and `MDUpdateIncremental`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4eb74-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4eb74-117">Requirements</span></span>  
 <span data-ttu-id="4eb74-118">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4eb74-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4eb74-119">**Encabezado:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="4eb74-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="4eb74-120">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4eb74-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4eb74-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="4eb74-121">See Also</span></span>  
 [<span data-ttu-id="4eb74-122">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="4eb74-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
