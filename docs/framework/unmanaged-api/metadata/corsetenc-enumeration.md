---
description: 'Más información sobre: enumeración Corsetenc ('
title: CorSetENC (Enumeración)
ms.date: 03/30/2017
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
ms.openlocfilehash: 5ba3e41c10b082ceb2ce7d327f7ff7f857ca98a5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707402"
---
# <a name="corsetenc-enumeration"></a><span data-ttu-id="b12ef-103">CorSetENC (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="b12ef-103">CorSetENC Enumeration</span></span>

<span data-ttu-id="b12ef-104">Contiene valores que se usan para influir en el comportamiento durante la generación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="b12ef-104">Contains values used to influence behavior during the generation of metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b12ef-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b12ef-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="b12ef-106">Members</span><span class="sxs-lookup"><span data-stu-id="b12ef-106">Members</span></span>  
  
|<span data-ttu-id="b12ef-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="b12ef-107">Member</span></span>|<span data-ttu-id="b12ef-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="b12ef-108">Description</span></span>|  
|------------|-----------------|  
|`MDSetENCOn`|<span data-ttu-id="b12ef-109">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="b12ef-109">Obsolete.</span></span>|  
|`MDSetENCOff`|<span data-ttu-id="b12ef-110">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="b12ef-110">Obsolete.</span></span>|  
|`MDUpdateENC`|<span data-ttu-id="b12ef-111">Indica que, mientras que los metadatos se pueden actualizar, los tokens no se pueden transferir.</span><span class="sxs-lookup"><span data-stu-id="b12ef-111">Indicates that whereas metadata can be updated, tokens cannot be moved.</span></span>|  
|`MDUpdateFull`|<span data-ttu-id="b12ef-112">Indica que los tokens se pueden pasar durante las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="b12ef-112">Indicates that tokens can be moved during updates.</span></span>|  
|`MDUpdateExtension`|<span data-ttu-id="b12ef-113">Indica que las actualizaciones pueden constar solo de adiciones.</span><span class="sxs-lookup"><span data-stu-id="b12ef-113">Indicates that updates can consist only of additions.</span></span> <span data-ttu-id="b12ef-114">No se pueden moverse los tokens.</span><span class="sxs-lookup"><span data-stu-id="b12ef-114">Tokens cannot be moved.</span></span>|  
|`MDUpdateIncremental`|<span data-ttu-id="b12ef-115">Indica que la compilación es incremental.</span><span class="sxs-lookup"><span data-stu-id="b12ef-115">Indicates that compilation is incremental.</span></span>|  
|`MDUpdateDelta`|<span data-ttu-id="b12ef-116">Indica que solo se deben guardar los metadatos modificados.</span><span class="sxs-lookup"><span data-stu-id="b12ef-116">Indicates that only changed metadata should be saved.</span></span>|  
|`MDUpdateMask`|<span data-ttu-id="b12ef-117">Incluye `MDUpdateENC` , `MDUpdateFull` y `MDUpdateIncremental` .</span><span class="sxs-lookup"><span data-stu-id="b12ef-117">Includes `MDUpdateENC`, `MDUpdateFull` and `MDUpdateIncremental`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b12ef-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b12ef-118">Requirements</span></span>  

 <span data-ttu-id="b12ef-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b12ef-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b12ef-120">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="b12ef-120">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="b12ef-121">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b12ef-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b12ef-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="b12ef-122">See also</span></span>

- [<span data-ttu-id="b12ef-123">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="b12ef-123">Metadata Enumerations</span></span>](metadata-enumerations.md)
