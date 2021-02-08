---
description: 'Más información acerca de: enumeración CLSID_RESOLUTION_FLAGS'
title: CLSID_RESOLUTION_FLAGS (Enumeración)
ms.date: 03/30/2017
api_name:
- CLSID_RESOLUTION_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CLSID_RESOLUTION_FLAGS
helpviewer_keywords:
- CLSID_RESOLUTION_FLAGS enumeration [.NET Framework hosting]
ms.assetid: cd8b9879-962a-4811-aa46-2e2b6bae0d84
topic_type:
- apiref
ms.openlocfilehash: 54d334147e13217f8ce20dae1b139cdc6d11a3b8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799881"
---
# <a name="clsid_resolution_flags-enumeration"></a><span data-ttu-id="26be7-103">CLSID_RESOLUTION_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="26be7-103">CLSID_RESOLUTION_FLAGS Enumeration</span></span>

<span data-ttu-id="26be7-104">Contiene valores que indican cómo debe resolver el Common Language Runtime (CLR) `CLSID` .</span><span class="sxs-lookup"><span data-stu-id="26be7-104">Contains values that indicate how the common language runtime (CLR) should resolve a `CLSID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26be7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="26be7-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    CLSID_RESOLUTION_DEFAULT      = 0x0,  
    CLSID_RESOLUTION_REGISTERED   = 0x1  
} CLSID_RESOLUTION_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="26be7-106">Members</span><span class="sxs-lookup"><span data-stu-id="26be7-106">Members</span></span>  
  
|<span data-ttu-id="26be7-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="26be7-107">Member</span></span>|<span data-ttu-id="26be7-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="26be7-108">Description</span></span>|  
|------------|-----------------|  
|`CLSID_RESOLUTION_DEFAULT`|<span data-ttu-id="26be7-109">Indica el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="26be7-109">Indicates the default behavior.</span></span>|  
|`CLSID_RESOLUTION_REGISTERED`|<span data-ttu-id="26be7-110">Indica que el tiempo de ejecución busca en el registro y aplica la Directiva de correcciones de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="26be7-110">Indicates that the runtime searches the registry and applies shim policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="26be7-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="26be7-111">Requirements</span></span>  

 <span data-ttu-id="26be7-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26be7-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26be7-113">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="26be7-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="26be7-114">**.NET Framework versiones:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26be7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26be7-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="26be7-115">See also</span></span>

- [<span data-ttu-id="26be7-116">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="26be7-116">Hosting Enumerations</span></span>](hosting-enumerations.md)
