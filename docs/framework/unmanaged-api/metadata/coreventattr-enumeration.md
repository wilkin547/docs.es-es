---
title: CorEventAttr (Enumeración)
ms.date: 03/30/2017
api_name:
- CorEventAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorEventAttr
helpviewer_keywords:
- CorEventAttr enumeration [.NET Framework metadata]
ms.assetid: dc2b3281-3820-487e-930d-350b66dc6417
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e4e4b9d9c7481bdc51aaf75b26b3805940875f8d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442311"
---
# <a name="coreventattr-enumeration"></a><span data-ttu-id="4da2f-102">CorEventAttr (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="4da2f-102">CorEventAttr Enumeration</span></span>
<span data-ttu-id="4da2f-103">Contiene valores que describen los metadatos de un evento.</span><span class="sxs-lookup"><span data-stu-id="4da2f-103">Contains values that describe the metadata of an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4da2f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4da2f-104">Syntax</span></span>  
  
```  
typedef enum CorEventAttr {  
  
    evSpecialName           =   0x0200,  
  
    evReservedMask          =   0x0400,  
    evRTSpecialName         =   0x0400,  
  
} CorEventAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="4da2f-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="4da2f-105">Members</span></span>  
  
|<span data-ttu-id="4da2f-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="4da2f-106">Member</span></span>|<span data-ttu-id="4da2f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="4da2f-107">Description</span></span>|  
|------------|-----------------|  
|`evSpecialName`|<span data-ttu-id="4da2f-108">Especifica que el evento es especial y que su nombre describe cómo.</span><span class="sxs-lookup"><span data-stu-id="4da2f-108">Specifies that the event is special, and that its name describes how.</span></span>|  
|`evReservedMask`|<span data-ttu-id="4da2f-109">Reservado para uso interno por common language runtime.</span><span class="sxs-lookup"><span data-stu-id="4da2f-109">Reserved for internal use by the common language runtime.</span></span>|  
|`evRTSpecialName`|<span data-ttu-id="4da2f-110">Especifica que common language runtime debe comprobar la codificación del nombre del evento.</span><span class="sxs-lookup"><span data-stu-id="4da2f-110">Specifies that the common language runtime should check the encoding of the event name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4da2f-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4da2f-111">Requirements</span></span>  
 <span data-ttu-id="4da2f-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4da2f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4da2f-113">**Encabezado:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="4da2f-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="4da2f-114">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4da2f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4da2f-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="4da2f-115">See Also</span></span>  
 [<span data-ttu-id="4da2f-116">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="4da2f-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
