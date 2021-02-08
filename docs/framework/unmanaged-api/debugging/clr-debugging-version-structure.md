---
description: 'Más información acerca de: estructura de CLR_DEBUGGING_VERSION'
title: CLR_DEBUGGING_VERSION (Estructura)
ms.date: 03/30/2017
api_name:
- CLR_DEBUGGING_VERSION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLR_DEBUGGING_VERSION
helpviewer_keywords:
- CLR_DEBUGGING_VERSION structure [.NET Framework debugging]
ms.assetid: 4d821186-3ddf-405a-ac44-d79438a9f7f3
topic_type:
- apiref
ms.openlocfilehash: 2d274a91948b98dc309cd5670c3dd3bf6cd01e2b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772788"
---
# <a name="clr_debugging_version-structure"></a><span data-ttu-id="cb8c1-103">CLR_DEBUGGING_VERSION (Estructura)</span><span class="sxs-lookup"><span data-stu-id="cb8c1-103">CLR_DEBUGGING_VERSION Structure</span></span>

<span data-ttu-id="cb8c1-104">Define la versión de producto de Common Language Runtime (CLR) con fines de depuración.</span><span class="sxs-lookup"><span data-stu-id="cb8c1-104">Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb8c1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cb8c1-105">Syntax</span></span>  
  
```cpp  
typedef struct _CLR_DEBUGGING_VERSION  
{  
    WORD wStructVersion;
    WORD wMajor;
    WORD wMinor;
    WORD wBuild;
    WORD wRevision;
} CLR_DEBUGGING_VERSION;
```  
  
## <a name="members"></a><span data-ttu-id="cb8c1-106">Members</span><span class="sxs-lookup"><span data-stu-id="cb8c1-106">Members</span></span>  
  
|<span data-ttu-id="cb8c1-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="cb8c1-107">Member</span></span>|<span data-ttu-id="cb8c1-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="cb8c1-108">Description</span></span>|  
|------------|-----------------|  
|`wStructVersion`|<span data-ttu-id="cb8c1-109">El número de versión de la estructura</span><span class="sxs-lookup"><span data-stu-id="cb8c1-109">The structure version number</span></span>|  
|`wMajor`|<span data-ttu-id="cb8c1-110">Número de versión principal.</span><span class="sxs-lookup"><span data-stu-id="cb8c1-110">The major version number.</span></span>|  
|`wMinor`|<span data-ttu-id="cb8c1-111">Número de versión secundaria.</span><span class="sxs-lookup"><span data-stu-id="cb8c1-111">The minor version number.</span></span>|  
|`wBuild`|<span data-ttu-id="cb8c1-112">Número de compilación.</span><span class="sxs-lookup"><span data-stu-id="cb8c1-112">The build number.</span></span>|  
|`wRevision`|<span data-ttu-id="cb8c1-113">Número de revisión.</span><span class="sxs-lookup"><span data-stu-id="cb8c1-113">The revision number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb8c1-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cb8c1-114">Remarks</span></span>  

 <span data-ttu-id="cb8c1-115">La `CLR_DEBUGGING_VERSION` estructura es la misma que la estructura de COR_VERSION, sin embargo, la `CLR_DEBUGGING_VERSION` estructura proporciona un campo de versión de la estructura adicional ( `wStructVersion` ).</span><span class="sxs-lookup"><span data-stu-id="cb8c1-115">The `CLR_DEBUGGING_VERSION` structure is the same as the COR_VERSION structure, however, the `CLR_DEBUGGING_VERSION` structure provides an additional structure version field (`wStructVersion`).</span></span> <span data-ttu-id="cb8c1-116">Actualmente, este campo debe establecerse en cero.</span><span class="sxs-lookup"><span data-stu-id="cb8c1-116">Currently, this field must be set to zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb8c1-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cb8c1-117">Requirements</span></span>  

 <span data-ttu-id="cb8c1-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb8c1-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb8c1-119">**Encabezado:** Cordebug. idl</span><span class="sxs-lookup"><span data-stu-id="cb8c1-119">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="cb8c1-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb8c1-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb8c1-121">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb8c1-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb8c1-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb8c1-122">See also</span></span>

- [<span data-ttu-id="cb8c1-123">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="cb8c1-123">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="cb8c1-124">Depuración</span><span class="sxs-lookup"><span data-stu-id="cb8c1-124">Debugging</span></span>](index.md)
