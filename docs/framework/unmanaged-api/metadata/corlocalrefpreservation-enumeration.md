---
title: CorLocalRefPreservation (Enumeración)
ms.date: 03/30/2017
api_name:
- CorLocalRefPreservation
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorLocalRefPreservation
helpviewer_keywords:
- CorLocalRefPreservation enumeration [.NET Framework metadata]
ms.assetid: 44757163-1228-4213-a4c4-d4de503cc75d
topic_type:
- apiref
ms.openlocfilehash: 49b0298f4fa776c93f89ac380ce65568b493379b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677120"
---
# <a name="corlocalrefpreservation-enumeration"></a><span data-ttu-id="921c7-102">CorLocalRefPreservation (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="921c7-102">CorLocalRefPreservation Enumeration</span></span>

<span data-ttu-id="921c7-103">Contiene valores de marca para el tratamiento de referencias locales.</span><span class="sxs-lookup"><span data-stu-id="921c7-103">Contains flag values for the treatment of local references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="921c7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="921c7-104">Syntax</span></span>  
  
```cpp  
typedef enum CorLocalRefPreservation  
{  
    MDPreserveLocalRefsNone     =   0x00000000,  
    MDPreserveLocalTypeRef      =   0x00000001,  
    MDPreserveLocalMemberRef    =   0x00000002  
} CorLocalRefPreservation;  
```  
  
## <a name="members"></a><span data-ttu-id="921c7-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="921c7-105">Members</span></span>  
  
|<span data-ttu-id="921c7-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="921c7-106">Member</span></span>|<span data-ttu-id="921c7-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="921c7-107">Description</span></span>|  
|------------|-----------------|  
|`MDPreserveLocalRefsNone`|<span data-ttu-id="921c7-108">No conservar ninguna referencia local.</span><span class="sxs-lookup"><span data-stu-id="921c7-108">Preserve no local references.</span></span>|  
|`MDPreserveLocalTypeRef`|<span data-ttu-id="921c7-109">Conserva las referencias de tipo local.</span><span class="sxs-lookup"><span data-stu-id="921c7-109">Preserve local type references.</span></span>|  
|`MDPreserveLocalMemberRef`|<span data-ttu-id="921c7-110">Conservar las referencias de miembro local.</span><span class="sxs-lookup"><span data-stu-id="921c7-110">Preserve local member references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="921c7-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="921c7-111">Requirements</span></span>  

 <span data-ttu-id="921c7-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="921c7-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="921c7-113">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="921c7-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="921c7-114">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="921c7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="921c7-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="921c7-115">See also</span></span>

- [<span data-ttu-id="921c7-116">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="921c7-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
