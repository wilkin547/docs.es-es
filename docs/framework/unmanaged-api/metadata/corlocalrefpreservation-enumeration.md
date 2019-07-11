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
ms.openlocfilehash: 6338034d6714e8770e06ff61994fdf4433eb1684
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781787"
---
# <a name="corlocalrefpreservation-enumeration"></a><span data-ttu-id="ccab4-102">CorLocalRefPreservation (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="ccab4-102">CorLocalRefPreservation Enumeration</span></span>
<span data-ttu-id="ccab4-103">Contiene valores de marca para el tratamiento de referencias locales.</span><span class="sxs-lookup"><span data-stu-id="ccab4-103">Contains flag values for the treatment of local references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccab4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ccab4-104">Syntax</span></span>  
  
```cpp  
typedef enum CorLocalRefPreservation  
{  
    MDPreserveLocalRefsNone     =   0x00000000,  
    MDPreserveLocalTypeRef      =   0x00000001,  
    MDPreserveLocalMemberRef    =   0x00000002  
} CorLocalRefPreservation;  
```  
  
## <a name="members"></a><span data-ttu-id="ccab4-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="ccab4-105">Members</span></span>  
  
|<span data-ttu-id="ccab4-106">Member</span><span class="sxs-lookup"><span data-stu-id="ccab4-106">Member</span></span>|<span data-ttu-id="ccab4-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ccab4-107">Description</span></span>|  
|------------|-----------------|  
|`MDPreserveLocalRefsNone`|<span data-ttu-id="ccab4-108">No conservar ninguna referencia local.</span><span class="sxs-lookup"><span data-stu-id="ccab4-108">Preserve no local references.</span></span>|  
|`MDPreserveLocalTypeRef`|<span data-ttu-id="ccab4-109">Preservar referencias de tipo local.</span><span class="sxs-lookup"><span data-stu-id="ccab4-109">Preserve local type references.</span></span>|  
|`MDPreserveLocalMemberRef`|<span data-ttu-id="ccab4-110">Preservar referencias de miembro local.</span><span class="sxs-lookup"><span data-stu-id="ccab4-110">Preserve local member references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ccab4-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ccab4-111">Requirements</span></span>  
 <span data-ttu-id="ccab4-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ccab4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccab4-113">**Encabezado**: CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="ccab4-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="ccab4-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccab4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccab4-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="ccab4-115">See also</span></span>

- [<span data-ttu-id="ccab4-116">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="ccab4-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
