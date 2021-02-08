---
description: 'Más información sobre: enumeración Corlocalrefpreservation ('
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
ms.openlocfilehash: afcdf6ce22c5f786e8f728cc1e45ad3ca44e7ef5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784423"
---
# <a name="corlocalrefpreservation-enumeration"></a><span data-ttu-id="54633-103">CorLocalRefPreservation (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="54633-103">CorLocalRefPreservation Enumeration</span></span>

<span data-ttu-id="54633-104">Contiene valores de marca para el tratamiento de referencias locales.</span><span class="sxs-lookup"><span data-stu-id="54633-104">Contains flag values for the treatment of local references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54633-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="54633-105">Syntax</span></span>  
  
```cpp  
typedef enum CorLocalRefPreservation  
{  
    MDPreserveLocalRefsNone     =   0x00000000,  
    MDPreserveLocalTypeRef      =   0x00000001,  
    MDPreserveLocalMemberRef    =   0x00000002  
} CorLocalRefPreservation;  
```  
  
## <a name="members"></a><span data-ttu-id="54633-106">Members</span><span class="sxs-lookup"><span data-stu-id="54633-106">Members</span></span>  
  
|<span data-ttu-id="54633-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="54633-107">Member</span></span>|<span data-ttu-id="54633-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="54633-108">Description</span></span>|  
|------------|-----------------|  
|`MDPreserveLocalRefsNone`|<span data-ttu-id="54633-109">No conservar ninguna referencia local.</span><span class="sxs-lookup"><span data-stu-id="54633-109">Preserve no local references.</span></span>|  
|`MDPreserveLocalTypeRef`|<span data-ttu-id="54633-110">Conserva las referencias de tipo local.</span><span class="sxs-lookup"><span data-stu-id="54633-110">Preserve local type references.</span></span>|  
|`MDPreserveLocalMemberRef`|<span data-ttu-id="54633-111">Conservar las referencias de miembro local.</span><span class="sxs-lookup"><span data-stu-id="54633-111">Preserve local member references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="54633-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="54633-112">Requirements</span></span>  

 <span data-ttu-id="54633-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54633-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54633-114">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="54633-114">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="54633-115">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54633-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54633-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="54633-116">See also</span></span>

- [<span data-ttu-id="54633-117">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="54633-117">Metadata Enumerations</span></span>](metadata-enumerations.md)
