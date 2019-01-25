---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a4049b0ed25d4c0fda00fe9b0dad5887fa4f6996
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506945"
---
# <a name="clrdebuggingversion-structure"></a><span data-ttu-id="bf18e-102">CLR_DEBUGGING_VERSION (Estructura)</span><span class="sxs-lookup"><span data-stu-id="bf18e-102">CLR_DEBUGGING_VERSION Structure</span></span>
<span data-ttu-id="bf18e-103">Define la versión de producto de Common Language Runtime (CLR) con fines de depuración.</span><span class="sxs-lookup"><span data-stu-id="bf18e-103">Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf18e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bf18e-104">Syntax</span></span>  
  
```  
typedef struct _CLR_DEBUGGING_VERSION  
{  
    WORD wStructVersion;
    WORD wMajor;
    WORD wMinor;
    WORD wBuild;
    WORD wRevision;
} CLR_DEBUGGING_VERSION;
```  
  
## <a name="members"></a><span data-ttu-id="bf18e-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="bf18e-105">Members</span></span>  
  
|<span data-ttu-id="bf18e-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="bf18e-106">Member</span></span>|<span data-ttu-id="bf18e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="bf18e-107">Description</span></span>|  
|------------|-----------------|  
|`wStructVersion`|<span data-ttu-id="bf18e-108">El número de versión de la estructura</span><span class="sxs-lookup"><span data-stu-id="bf18e-108">The structure version number</span></span>|  
|`wMajor`|<span data-ttu-id="bf18e-109">Número de versión principal.</span><span class="sxs-lookup"><span data-stu-id="bf18e-109">The major version number.</span></span>|  
|`wMinor`|<span data-ttu-id="bf18e-110">Número de versión secundaria.</span><span class="sxs-lookup"><span data-stu-id="bf18e-110">The minor version number.</span></span>|  
|`wBuild`|<span data-ttu-id="bf18e-111">El número de compilación.</span><span class="sxs-lookup"><span data-stu-id="bf18e-111">The build number.</span></span>|  
|`wRevision`|<span data-ttu-id="bf18e-112">El número de revisión.</span><span class="sxs-lookup"><span data-stu-id="bf18e-112">The revision number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf18e-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bf18e-113">Remarks</span></span>  
 <span data-ttu-id="bf18e-114">El `CLR_DEBUGGING_VERSION` estructura es igual que el COR_VERSION (estructura), sin embargo, el `CLR_DEBUGGING_VERSION` estructura proporciona un campo de versión de una estructura adicional (`wStructVersion`).</span><span class="sxs-lookup"><span data-stu-id="bf18e-114">The `CLR_DEBUGGING_VERSION` structure is the same as the COR_VERSION structure, however, the `CLR_DEBUGGING_VERSION` structure provides an additional structure version field (`wStructVersion`).</span></span> <span data-ttu-id="bf18e-115">Actualmente, este campo debe establecerse en cero.</span><span class="sxs-lookup"><span data-stu-id="bf18e-115">Currently, this field must be set to zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf18e-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bf18e-116">Requirements</span></span>  
 <span data-ttu-id="bf18e-117">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf18e-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf18e-118">**Encabezado**: CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="bf18e-118">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="bf18e-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf18e-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf18e-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf18e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf18e-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf18e-121">See also</span></span>
- [<span data-ttu-id="bf18e-122">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="bf18e-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="bf18e-123">Depuración</span><span class="sxs-lookup"><span data-stu-id="bf18e-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
