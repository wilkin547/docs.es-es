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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 845994b96445d8ec2a0e37affc5164b432894a91
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045717"
---
# <a name="corlocalrefpreservation-enumeration"></a><span data-ttu-id="37de2-102">CorLocalRefPreservation (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="37de2-102">CorLocalRefPreservation Enumeration</span></span>
<span data-ttu-id="37de2-103">Contiene valores de marca para el tratamiento de referencias locales.</span><span class="sxs-lookup"><span data-stu-id="37de2-103">Contains flag values for the treatment of local references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37de2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="37de2-104">Syntax</span></span>  
  
```  
typedef enum CorLocalRefPreservation  
{  
    MDPreserveLocalRefsNone     =   0x00000000,  
    MDPreserveLocalTypeRef      =   0x00000001,  
    MDPreserveLocalMemberRef    =   0x00000002  
} CorLocalRefPreservation;  
```  
  
## <a name="members"></a><span data-ttu-id="37de2-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="37de2-105">Members</span></span>  
  
|<span data-ttu-id="37de2-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="37de2-106">Member</span></span>|<span data-ttu-id="37de2-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="37de2-107">Description</span></span>|  
|------------|-----------------|  
|`MDPreserveLocalRefsNone`|<span data-ttu-id="37de2-108">No conservar ninguna referencia local.</span><span class="sxs-lookup"><span data-stu-id="37de2-108">Preserve no local references.</span></span>|  
|`MDPreserveLocalTypeRef`|<span data-ttu-id="37de2-109">Preservar referencias de tipo local.</span><span class="sxs-lookup"><span data-stu-id="37de2-109">Preserve local type references.</span></span>|  
|`MDPreserveLocalMemberRef`|<span data-ttu-id="37de2-110">Preservar referencias de miembro local.</span><span class="sxs-lookup"><span data-stu-id="37de2-110">Preserve local member references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="37de2-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="37de2-111">Requirements</span></span>  
 <span data-ttu-id="37de2-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37de2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37de2-113">**Encabezado**: CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="37de2-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="37de2-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37de2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37de2-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="37de2-115">See also</span></span>

- [<span data-ttu-id="37de2-116">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="37de2-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
