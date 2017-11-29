---
title: "CorDebugHandleType (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugHandleType
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugHandleType
helpviewer_keywords: CorDebugHandleType enumeration [.NET Framework debugging]
ms.assetid: 84296b55-c2c5-424c-ac9c-8e28e2895945
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ef0b892d8dc277286114e8f9eda8d0f16833e1d8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="cordebughandletype-enumeration"></a><span data-ttu-id="6968e-102">CorDebugHandleType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="6968e-102">CorDebugHandleType Enumeration</span></span>
<span data-ttu-id="6968e-103">Indica el tipo de control.</span><span class="sxs-lookup"><span data-stu-id="6968e-103">Indicates the handle type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6968e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6968e-104">Syntax</span></span>  
  
```  
typedef enum CorDebugHandleType {  
    HANDLE_STRONG                  = 1,  
    HANDLE_WEAK_TRACK_RESURRECTION = 2  
} CorDebugHandleType;  
```  
  
## <a name="members"></a><span data-ttu-id="6968e-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="6968e-105">Members</span></span>  
  
|<span data-ttu-id="6968e-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="6968e-106">Member</span></span>|<span data-ttu-id="6968e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="6968e-107">Description</span></span>|  
|------------|-----------------|  
|`HANDLE_STRONG`|<span data-ttu-id="6968e-108">El controlador es seguro, lo que impide que un objeto que se va a reclamado por la recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="6968e-108">The handle is strong, which prevents an object from being reclaimed by garbage collection.</span></span>|  
|`HANDLE_WEAK_TRACK_RESURRECTION`|<span data-ttu-id="6968e-109">El identificador es débil, que no impide que un objeto que se va a reclamado por la recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="6968e-109">The handle is weak, which does not prevent an object from being reclaimed by garbage collection.</span></span><br /><br /> <span data-ttu-id="6968e-110">El identificador deja de ser válido cuando el objeto se recopila.</span><span class="sxs-lookup"><span data-stu-id="6968e-110">The handle becomes invalid when the object is collected.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6968e-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6968e-111">Requirements</span></span>  
 <span data-ttu-id="6968e-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6968e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6968e-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6968e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6968e-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6968e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6968e-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6968e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6968e-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="6968e-116">See Also</span></span>  
 [<span data-ttu-id="6968e-117">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="6968e-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
