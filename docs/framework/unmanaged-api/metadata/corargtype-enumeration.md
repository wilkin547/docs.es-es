---
description: 'Más información sobre: enumeración Corargtype ('
title: CorArgType (Enumeración)
ms.date: 03/30/2017
api_name:
- CorArgType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorArgType
helpviewer_keywords:
- CorArgType enumeration [.NET Framework metadata]
ms.assetid: 3c1cb268-57a0-4664-91c7-f6908ff29e32
topic_type:
- apiref
ms.openlocfilehash: de7067e6c7b825aae797d88dbd5f2ecd2f5280fa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678528"
---
# <a name="corargtype-enumeration"></a><span data-ttu-id="80087-103">CorArgType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="80087-103">CorArgType Enumeration</span></span>

<span data-ttu-id="80087-104">Contiene valores que describen el tipo nativo de un identificador en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="80087-104">Contains values that describe the native type of a runtime handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80087-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="80087-105">Syntax</span></span>  
  
```cpp  
typedef enum CorArgType {  
  
    IMAGE_CEE_CS_END        = 0x0,  
    IMAGE_CEE_CS_VOID       = 0x1,  
    IMAGE_CEE_CS_I4         = 0x2,  
    IMAGE_CEE_CS_I8         = 0x3,  
    IMAGE_CEE_CS_R4         = 0x4,  
    IMAGE_CEE_CS_R8         = 0x5,  
    IMAGE_CEE_CS_PTR        = 0x6,  
    IMAGE_CEE_CS_OBJECT     = 0x7,  
    IMAGE_CEE_CS_STRUCT4    = 0x8,  
    IMAGE_CEE_CS_STRUCT32   = 0x9,  
    IMAGE_CEE_CS_BYVALUE    = 0xA  
  
} CorArgType;  
```  
  
## <a name="requirements"></a><span data-ttu-id="80087-106">Requisitos</span><span class="sxs-lookup"><span data-stu-id="80087-106">Requirements</span></span>  

 <span data-ttu-id="80087-107">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80087-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80087-108">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="80087-108">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="80087-109">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80087-109">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80087-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="80087-110">See also</span></span>

- [<span data-ttu-id="80087-111">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="80087-111">Metadata Enumerations</span></span>](metadata-enumerations.md)
