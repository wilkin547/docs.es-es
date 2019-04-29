---
title: CorDebugHandleType (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugHandleType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugHandleType
helpviewer_keywords:
- CorDebugHandleType enumeration [.NET Framework debugging]
ms.assetid: 84296b55-c2c5-424c-ac9c-8e28e2895945
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 513fc93bdac71e2a3ba59ebb53fdde44f1659af5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651731"
---
# <a name="cordebughandletype-enumeration"></a><span data-ttu-id="f2805-102">CorDebugHandleType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="f2805-102">CorDebugHandleType Enumeration</span></span>
<span data-ttu-id="f2805-103">Indica el tipo de control.</span><span class="sxs-lookup"><span data-stu-id="f2805-103">Indicates the handle type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2805-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f2805-104">Syntax</span></span>  
  
```  
typedef enum CorDebugHandleType {  
    HANDLE_STRONG                  = 1,  
    HANDLE_WEAK_TRACK_RESURRECTION = 2  
} CorDebugHandleType;  
```  
  
## <a name="members"></a><span data-ttu-id="f2805-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="f2805-105">Members</span></span>  
  
|<span data-ttu-id="f2805-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="f2805-106">Member</span></span>|<span data-ttu-id="f2805-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f2805-107">Description</span></span>|  
|------------|-----------------|  
|`HANDLE_STRONG`|<span data-ttu-id="f2805-108">El controlador es seguro, lo que impide que un objeto que se va a reclamado por la recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="f2805-108">The handle is strong, which prevents an object from being reclaimed by garbage collection.</span></span>|  
|`HANDLE_WEAK_TRACK_RESURRECTION`|<span data-ttu-id="f2805-109">El identificador es débil, que no impide que un objeto que se va a reclamado por la recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="f2805-109">The handle is weak, which does not prevent an object from being reclaimed by garbage collection.</span></span><br /><br /> <span data-ttu-id="f2805-110">El identificador deja de ser válido cuando el objeto se recopila.</span><span class="sxs-lookup"><span data-stu-id="f2805-110">The handle becomes invalid when the object is collected.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f2805-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f2805-111">Requirements</span></span>  
 <span data-ttu-id="f2805-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2805-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2805-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f2805-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f2805-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2805-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2805-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2805-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2805-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2805-116">See also</span></span>

- [<span data-ttu-id="f2805-117">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="f2805-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
