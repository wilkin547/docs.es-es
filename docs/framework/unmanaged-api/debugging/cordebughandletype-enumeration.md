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
ms.openlocfilehash: 5a957a042875b546a18a17422f355b712756e91c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73098170"
---
# <a name="cordebughandletype-enumeration"></a><span data-ttu-id="b2aab-102">CorDebugHandleType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="b2aab-102">CorDebugHandleType Enumeration</span></span>
<span data-ttu-id="b2aab-103">Indica el tipo de control.</span><span class="sxs-lookup"><span data-stu-id="b2aab-103">Indicates the handle type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2aab-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b2aab-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugHandleType {  
    HANDLE_STRONG                  = 1,  
    HANDLE_WEAK_TRACK_RESURRECTION = 2  
} CorDebugHandleType;  
```  
  
## <a name="members"></a><span data-ttu-id="b2aab-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="b2aab-105">Members</span></span>  
  
|<span data-ttu-id="b2aab-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="b2aab-106">Member</span></span>|<span data-ttu-id="b2aab-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b2aab-107">Description</span></span>|  
|------------|-----------------|  
|`HANDLE_STRONG`|<span data-ttu-id="b2aab-108">El identificador es seguro, lo que impide que la recolección de elementos no utilizados recupere un objeto.</span><span class="sxs-lookup"><span data-stu-id="b2aab-108">The handle is strong, which prevents an object from being reclaimed by garbage collection.</span></span>|  
|`HANDLE_WEAK_TRACK_RESURRECTION`|<span data-ttu-id="b2aab-109">El identificador es débil, lo que no impide que la recolección de elementos no utilizados pueda reclamar un objeto.</span><span class="sxs-lookup"><span data-stu-id="b2aab-109">The handle is weak, which does not prevent an object from being reclaimed by garbage collection.</span></span><br /><br /> <span data-ttu-id="b2aab-110">El identificador deja de ser válido cuando se recopila el objeto.</span><span class="sxs-lookup"><span data-stu-id="b2aab-110">The handle becomes invalid when the object is collected.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b2aab-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b2aab-111">Requirements</span></span>  
 <span data-ttu-id="b2aab-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2aab-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2aab-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2aab-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2aab-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2aab-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2aab-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2aab-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2aab-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2aab-116">See also</span></span>

- [<span data-ttu-id="b2aab-117">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="b2aab-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
