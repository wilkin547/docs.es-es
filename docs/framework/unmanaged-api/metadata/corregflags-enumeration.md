---
title: CorRegFlags (Enumeración)
ms.date: 03/30/2017
api_name:
- CorRegFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRegFlags
helpviewer_keywords:
- CorRegFlags enumeration [.NET Framework metadata]
ms.assetid: 8d3080ee-39fe-4c57-8950-51323632d045
topic_type:
- apiref
ms.openlocfilehash: 79a9e4513a98a29edc11cc76c599f03c9c3a72b4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450116"
---
# <a name="corregflags-enumeration"></a><span data-ttu-id="19e61-102">CorRegFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="19e61-102">CorRegFlags Enumeration</span></span>
<span data-ttu-id="19e61-103">Provides flag values used for registration when installing a module or composite image.</span><span class="sxs-lookup"><span data-stu-id="19e61-103">Provides flag values used for registration when installing a module or composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19e61-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="19e61-104">Syntax</span></span>  
  
```cpp  
typedef enum   
{  
    regNoCopy  = 0x00000001,  
    regConfig  = 0x00000002,  
    regHasRefs = 0x00000004  
} CorRegFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="19e61-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="19e61-105">Members</span></span>  
  
|<span data-ttu-id="19e61-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="19e61-106">Member</span></span>|<span data-ttu-id="19e61-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="19e61-107">Description</span></span>|  
|------------|-----------------|  
|`regNoCopy`|<span data-ttu-id="19e61-108">Specifies that files should not be copied into the destination.</span><span class="sxs-lookup"><span data-stu-id="19e61-108">Specifies that files should not be copied into the destination.</span></span>|  
|`regConfig`|<span data-ttu-id="19e61-109">Specifies that the module or composite is a configuration.</span><span class="sxs-lookup"><span data-stu-id="19e61-109">Specifies that the module or composite is a configuration.</span></span>|  
|`regHasRefs`|<span data-ttu-id="19e61-110">Specifies that the module or composite has class references.</span><span class="sxs-lookup"><span data-stu-id="19e61-110">Specifies that the module or composite has class references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="19e61-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="19e61-111">Requirements</span></span>  
 <span data-ttu-id="19e61-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19e61-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19e61-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="19e61-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="19e61-114">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="19e61-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="19e61-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19e61-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19e61-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="19e61-116">See also</span></span>

- [<span data-ttu-id="19e61-117">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="19e61-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
