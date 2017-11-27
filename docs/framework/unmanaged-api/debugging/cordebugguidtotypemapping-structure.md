---
title: CorDebugGuidToTypeMapping (Estructura)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: CorDebugGuidToTypeMapping
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugGuidToTypeMapping
helpviewer_keywords: CorDebugGuidToTypeMapping structure [.NET Framework debugging]
ms.assetid: 57dbccd9-b16d-4da3-ae25-7a2cf9adf679
topic_type: apiref
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e4c829f4a74c3d2e84a070dfbe5d35d89b1b7ae6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugguidtotypemapping-structure"></a><span data-ttu-id="3354d-102">CorDebugGuidToTypeMapping (Estructura)</span><span class="sxs-lookup"><span data-stu-id="3354d-102">CorDebugGuidToTypeMapping Structure</span></span>
<span data-ttu-id="3354d-103">Se asigna un [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID a su objeto ICorDebugType correspondiente.</span><span class="sxs-lookup"><span data-stu-id="3354d-103">Maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding ICorDebugType object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3354d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3354d-104">Syntax</span></span>  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="3354d-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="3354d-105">Members</span></span>  
  
|<span data-ttu-id="3354d-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="3354d-106">Member</span></span>|<span data-ttu-id="3354d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="3354d-107">Description</span></span>|  
|------------|-----------------|  
|`iid`|<span data-ttu-id="3354d-108">El GUID de la caché [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipo.</span><span class="sxs-lookup"><span data-stu-id="3354d-108">The GUID of the cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] type.</span></span>|  
|`pType`|<span data-ttu-id="3354d-109">Un puntero a un objeto ICorDebugType que proporciona información sobre el tipo almacenado en caché.</span><span class="sxs-lookup"><span data-stu-id="3354d-109">A pointer to an ICorDebugType object that provides information about the cached type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3354d-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3354d-110">Requirements</span></span>  
 <span data-ttu-id="3354d-111">**Plataformas:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3354d-111">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)].</span></span>  
  
 <span data-ttu-id="3354d-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3354d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3354d-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3354d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3354d-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3354d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3354d-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="3354d-115">See Also</span></span>  
 [<span data-ttu-id="3354d-116">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="3354d-116">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="3354d-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="3354d-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
