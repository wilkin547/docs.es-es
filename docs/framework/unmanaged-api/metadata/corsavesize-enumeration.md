---
description: 'Más información sobre: enumeración CorSaveSize ('
title: CorSaveSize (Enumeración)
ms.date: 03/30/2017
api_name:
- CorSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSaveSize
helpviewer_keywords:
- CorSaveSize enumeration [.NET Framework metadata]
ms.assetid: eb95ce39-5688-43c1-a34d-578794b32faa
topic_type:
- apiref
ms.openlocfilehash: 47e2d4d77f58f8f1c2135da5867dfa47cedfd83d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784228"
---
# <a name="corsavesize-enumeration"></a><span data-ttu-id="6eba9-103">CorSaveSize (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="6eba9-103">CorSaveSize Enumeration</span></span>

<span data-ttu-id="6eba9-104">Contiene valores que indican el nivel de precisión necesario al consultar el tamaño de una operación de guardar.</span><span class="sxs-lookup"><span data-stu-id="6eba9-104">Contains values indicating the level of precision required when querying for the size of a save operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6eba9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6eba9-105">Syntax</span></span>  
  
```cpp  
typedef enum CorSaveSize {  
    cssAccurate                = 0x0000,
    cssQuick                   = 0x0001,
    cssDiscardTransientCAs     = 0x0002  
} CorSaveSize;  
```  
  
## <a name="members"></a><span data-ttu-id="6eba9-106">Members</span><span class="sxs-lookup"><span data-stu-id="6eba9-106">Members</span></span>  
  
|<span data-ttu-id="6eba9-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="6eba9-107">Member</span></span>|<span data-ttu-id="6eba9-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="6eba9-108">Description</span></span>|  
|------------|-----------------|  
|`cssAccurate`|<span data-ttu-id="6eba9-109">Especifica que el valor devuelto debe ser exacto.</span><span class="sxs-lookup"><span data-stu-id="6eba9-109">Specifies that the return value should be exact.</span></span>|  
|`cssQuick`|<span data-ttu-id="6eba9-110">Especifica que se debe estimar el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="6eba9-110">Specifies that the return value should be estimated.</span></span>|  
|`cssDiscardTransientCAs`|<span data-ttu-id="6eba9-111">Especifica que deben quitarse los tipos que se pueden descartar.</span><span class="sxs-lookup"><span data-stu-id="6eba9-111">Specifies that discardable types should be removed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6eba9-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6eba9-112">Requirements</span></span>  

 <span data-ttu-id="6eba9-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6eba9-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6eba9-114">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="6eba9-114">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="6eba9-115">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6eba9-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6eba9-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6eba9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6eba9-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="6eba9-117">See also</span></span>

- [<span data-ttu-id="6eba9-118">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="6eba9-118">Metadata Enumerations</span></span>](metadata-enumerations.md)
