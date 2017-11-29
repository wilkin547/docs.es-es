---
title: COR_VERSION (Estructura)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_VERSION
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_VERSION
helpviewer_keywords: COR_VERSION structure [.NET Framework debugging]
ms.assetid: 5efaee1c-a001-4c73-9525-4160f4c71567
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bd4a878b51685befb39eb486097be2e2f2c1d409
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="corversion-structure"></a><span data-ttu-id="a383d-102">COR_VERSION (Estructura)</span><span class="sxs-lookup"><span data-stu-id="a383d-102">COR_VERSION Structure</span></span>
<span data-ttu-id="a383d-103">Almacena la versión estándar en cuatro partes de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="a383d-103">Stores the standard four-part version number of the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a383d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a383d-104">Syntax</span></span>  
  
```  
typedef struct _COR_VERSION {  
    DWORD dwMajor;  
    DWORD dwMinor;  
    DWORD dwBuild;  
    DWORD dwSubBuild;  
} COR_VERSION;  
```  
  
## <a name="members"></a><span data-ttu-id="a383d-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="a383d-105">Members</span></span>  
  
|<span data-ttu-id="a383d-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="a383d-106">Member</span></span>|<span data-ttu-id="a383d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a383d-107">Description</span></span>|  
|------------|-----------------|  
|`dwMajor`|<span data-ttu-id="a383d-108">Número de versión principal.</span><span class="sxs-lookup"><span data-stu-id="a383d-108">The major version number.</span></span>|  
|`dwMinor`|<span data-ttu-id="a383d-109">Número de versión secundaria.</span><span class="sxs-lookup"><span data-stu-id="a383d-109">The minor version number.</span></span>|  
|`dwBuild`|<span data-ttu-id="a383d-110">El número de compilación.</span><span class="sxs-lookup"><span data-stu-id="a383d-110">The build number.</span></span>|  
|`dwSubBuild`|<span data-ttu-id="a383d-111">El número de compilación secundaria.</span><span class="sxs-lookup"><span data-stu-id="a383d-111">The sub-build number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a383d-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a383d-112">Remarks</span></span>  
 <span data-ttu-id="a383d-113">Si el número de versión es 1.0.3705.288, 1 es el número de versión principal, 0 es el número de versión secundaria, 3705 es el número de compilación y 288 es el número de compilación secundaria.</span><span class="sxs-lookup"><span data-stu-id="a383d-113">If the version number is 1.0.3705.288, 1 is the major version number, 0 is the minor version number, 3705 is the build number, and 288 is the sub-build number.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a383d-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a383d-114">Requirements</span></span>  
 <span data-ttu-id="a383d-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a383d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a383d-116">**Encabezado:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="a383d-116">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="a383d-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a383d-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a383d-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a383d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a383d-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="a383d-119">See Also</span></span>  
 [<span data-ttu-id="a383d-120">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="a383d-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="a383d-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="a383d-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
