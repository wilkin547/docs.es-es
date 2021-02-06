---
description: 'Más información sobre: enumeración CorDebugHandleType ('
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
ms.openlocfilehash: 294fd7b04018331489e51d12930bcbbb81ec340a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662122"
---
# <a name="cordebughandletype-enumeration"></a><span data-ttu-id="69b60-103">CorDebugHandleType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="69b60-103">CorDebugHandleType Enumeration</span></span>

<span data-ttu-id="69b60-104">Indica el tipo de control.</span><span class="sxs-lookup"><span data-stu-id="69b60-104">Indicates the handle type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69b60-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="69b60-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugHandleType {  
    HANDLE_STRONG                  = 1,  
    HANDLE_WEAK_TRACK_RESURRECTION = 2  
} CorDebugHandleType;  
```  
  
## <a name="members"></a><span data-ttu-id="69b60-106">Members</span><span class="sxs-lookup"><span data-stu-id="69b60-106">Members</span></span>  
  
|<span data-ttu-id="69b60-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="69b60-107">Member</span></span>|<span data-ttu-id="69b60-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="69b60-108">Description</span></span>|  
|------------|-----------------|  
|`HANDLE_STRONG`|<span data-ttu-id="69b60-109">El identificador es seguro, lo que impide que la recolección de elementos no utilizados recupere un objeto.</span><span class="sxs-lookup"><span data-stu-id="69b60-109">The handle is strong, which prevents an object from being reclaimed by garbage collection.</span></span>|  
|`HANDLE_WEAK_TRACK_RESURRECTION`|<span data-ttu-id="69b60-110">El identificador es débil, lo que no impide que la recolección de elementos no utilizados pueda reclamar un objeto.</span><span class="sxs-lookup"><span data-stu-id="69b60-110">The handle is weak, which does not prevent an object from being reclaimed by garbage collection.</span></span><br /><br /> <span data-ttu-id="69b60-111">El identificador deja de ser válido cuando se recopila el objeto.</span><span class="sxs-lookup"><span data-stu-id="69b60-111">The handle becomes invalid when the object is collected.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="69b60-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="69b60-112">Requirements</span></span>  

 <span data-ttu-id="69b60-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69b60-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69b60-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="69b60-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="69b60-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69b60-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="69b60-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69b60-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69b60-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="69b60-117">See also</span></span>

- [<span data-ttu-id="69b60-118">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="69b60-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
