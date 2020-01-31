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
ms.openlocfilehash: 15572037940f7c45ec5dcb7e34599756e15fd3bd
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793908"
---
# <a name="cordebughandletype-enumeration"></a><span data-ttu-id="35411-102">CorDebugHandleType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="35411-102">CorDebugHandleType Enumeration</span></span>
<span data-ttu-id="35411-103">Indica el tipo de control.</span><span class="sxs-lookup"><span data-stu-id="35411-103">Indicates the handle type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35411-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="35411-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugHandleType {  
    HANDLE_STRONG                  = 1,  
    HANDLE_WEAK_TRACK_RESURRECTION = 2  
} CorDebugHandleType;  
```  
  
## <a name="members"></a><span data-ttu-id="35411-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="35411-105">Members</span></span>  
  
|<span data-ttu-id="35411-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="35411-106">Member</span></span>|<span data-ttu-id="35411-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="35411-107">Description</span></span>|  
|------------|-----------------|  
|`HANDLE_STRONG`|<span data-ttu-id="35411-108">El identificador es seguro, lo que impide que la recolección de elementos no utilizados recupere un objeto.</span><span class="sxs-lookup"><span data-stu-id="35411-108">The handle is strong, which prevents an object from being reclaimed by garbage collection.</span></span>|  
|`HANDLE_WEAK_TRACK_RESURRECTION`|<span data-ttu-id="35411-109">El identificador es débil, lo que no impide que la recolección de elementos no utilizados pueda reclamar un objeto.</span><span class="sxs-lookup"><span data-stu-id="35411-109">The handle is weak, which does not prevent an object from being reclaimed by garbage collection.</span></span><br /><br /> <span data-ttu-id="35411-110">El identificador deja de ser válido cuando se recopila el objeto.</span><span class="sxs-lookup"><span data-stu-id="35411-110">The handle becomes invalid when the object is collected.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="35411-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="35411-111">Requirements</span></span>  
 <span data-ttu-id="35411-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35411-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35411-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="35411-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="35411-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35411-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35411-115">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35411-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35411-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="35411-116">See also</span></span>

- [<span data-ttu-id="35411-117">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="35411-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
