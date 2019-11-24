---
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
ms.openlocfilehash: 0f870d9d7d1bc292b213d690df508a6c28bac2ab
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450099"
---
# <a name="corsavesize-enumeration"></a><span data-ttu-id="f1c1e-102">CorSaveSize (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="f1c1e-102">CorSaveSize Enumeration</span></span>
<span data-ttu-id="f1c1e-103">Contiene valores que indican el nivel de precisión necesario al consultar el tamaño de una operación de guardar.</span><span class="sxs-lookup"><span data-stu-id="f1c1e-103">Contains values indicating the level of precision required when querying for the size of a save operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1c1e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f1c1e-104">Syntax</span></span>  
  
```cpp  
typedef enum CorSaveSize {  
    cssAccurate                = 0x0000,   
    cssQuick                   = 0x0001,   
    cssDiscardTransientCAs     = 0x0002  
} CorSaveSize;  
```  
  
## <a name="members"></a><span data-ttu-id="f1c1e-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="f1c1e-105">Members</span></span>  
  
|<span data-ttu-id="f1c1e-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="f1c1e-106">Member</span></span>|<span data-ttu-id="f1c1e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f1c1e-107">Description</span></span>|  
|------------|-----------------|  
|`cssAccurate`|<span data-ttu-id="f1c1e-108">Specifies that the return value should be exact.</span><span class="sxs-lookup"><span data-stu-id="f1c1e-108">Specifies that the return value should be exact.</span></span>|  
|`cssQuick`|<span data-ttu-id="f1c1e-109">Specifies that the return value should be estimated.</span><span class="sxs-lookup"><span data-stu-id="f1c1e-109">Specifies that the return value should be estimated.</span></span>|  
|`cssDiscardTransientCAs`|<span data-ttu-id="f1c1e-110">Specifies that discardable types should be removed.</span><span class="sxs-lookup"><span data-stu-id="f1c1e-110">Specifies that discardable types should be removed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f1c1e-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f1c1e-111">Requirements</span></span>  
 <span data-ttu-id="f1c1e-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1c1e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1c1e-113">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="f1c1e-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="f1c1e-114">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f1c1e-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f1c1e-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1c1e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1c1e-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1c1e-116">See also</span></span>

- [<span data-ttu-id="f1c1e-117">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="f1c1e-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
