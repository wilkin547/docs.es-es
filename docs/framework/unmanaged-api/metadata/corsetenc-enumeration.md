---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3e09bf424a41445f7e36397775d1578cdf4e7e75
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442792"
---
# <a name="corsetenc-enumeration"></a><span data-ttu-id="3b68e-102">CorSetENC (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="3b68e-102">CorSetENC Enumeration</span></span>
<span data-ttu-id="3b68e-103">Contiene valores que se usan para influir en el comportamiento durante la generación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="3b68e-103">Contains values used to influence behavior during the generation of metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b68e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3b68e-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="3b68e-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="3b68e-105">Members</span></span>  
  
|<span data-ttu-id="3b68e-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="3b68e-106">Member</span></span>|<span data-ttu-id="3b68e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="3b68e-107">Description</span></span>|  
|------------|-----------------|  
|`MDSetENCOn`|<span data-ttu-id="3b68e-108">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="3b68e-108">Obsolete.</span></span>|  
|`MDSetENCOff`|<span data-ttu-id="3b68e-109">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="3b68e-109">Obsolete.</span></span>|  
|`MDUpdateENC`|<span data-ttu-id="3b68e-110">Indica que mientras que se puedan actualizar los metadatos no se puede mover los símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="3b68e-110">Indicates that whereas metadata can be updated, tokens cannot be moved.</span></span>|  
|`MDUpdateFull`|<span data-ttu-id="3b68e-111">Indica que se pueden mover tokens durante las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="3b68e-111">Indicates that tokens can be moved during updates.</span></span>|  
|`MDUpdateExtension`|<span data-ttu-id="3b68e-112">Indica que las actualizaciones pueden constar solo de adiciones.</span><span class="sxs-lookup"><span data-stu-id="3b68e-112">Indicates that updates can consist only of additions.</span></span> <span data-ttu-id="3b68e-113">No se puede mover los símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="3b68e-113">Tokens cannot be moved.</span></span>|  
|`MDUpdateIncremental`|<span data-ttu-id="3b68e-114">Indica que la compilación es incremental.</span><span class="sxs-lookup"><span data-stu-id="3b68e-114">Indicates that compilation is incremental.</span></span>|  
|`MDUpdateDelta`|<span data-ttu-id="3b68e-115">Indica que solo los metadatos modificados deben guardarse.</span><span class="sxs-lookup"><span data-stu-id="3b68e-115">Indicates that only changed metadata should be saved.</span></span>|  
|`MDUpdateMask`|<span data-ttu-id="3b68e-116">Incluye `MDUpdateENC`, `MDUpdateFull` y `MDUpdateIncremental`.</span><span class="sxs-lookup"><span data-stu-id="3b68e-116">Includes `MDUpdateENC`, `MDUpdateFull` and `MDUpdateIncremental`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3b68e-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3b68e-117">Requirements</span></span>  
 <span data-ttu-id="3b68e-118">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b68e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b68e-119">**Encabezado:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="3b68e-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="3b68e-120">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b68e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b68e-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b68e-121">See Also</span></span>  
 [<span data-ttu-id="3b68e-122">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="3b68e-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
