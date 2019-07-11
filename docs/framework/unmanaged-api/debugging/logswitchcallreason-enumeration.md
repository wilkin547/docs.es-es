---
title: LogSwitchCallReason (Enumeración)
ms.date: 03/30/2017
api_name:
- LogSwitchCallReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- LogSwitchCallReason
helpviewer_keywords:
- LogSwitchCallReason enumeration [.NET Framework debugging]
ms.assetid: 5bbb8d1b-bbc4-47b0-b1b1-2d54cc0be291
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 894f74f12de7ed0754dcca34eacb815efc33c766
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752576"
---
# <a name="logswitchcallreason-enumeration"></a><span data-ttu-id="c308c-102">LogSwitchCallReason (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="c308c-102">LogSwitchCallReason Enumeration</span></span>
<span data-ttu-id="c308c-103">Indica la operación que se realizó en un conmutador de depuración/seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c308c-103">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c308c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c308c-104">Syntax</span></span>  
  
```cpp  
typedef enum LogSwitchCallReason {  
    SWITCH_CREATE,  
    SWITCH_MODIFY,  
    SWITCH_DELETE  
} LogSwitchCallReason;  
```  
  
## <a name="members"></a><span data-ttu-id="c308c-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="c308c-105">Members</span></span>  
  
|<span data-ttu-id="c308c-106">Member</span><span class="sxs-lookup"><span data-stu-id="c308c-106">Member</span></span>|<span data-ttu-id="c308c-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c308c-107">Description</span></span>|  
|------------|-----------------|  
|`SWITCH_CREATE`|<span data-ttu-id="c308c-108">Se creó un conmutador de depuración y seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c308c-108">A debugging/tracing switch was created.</span></span>|  
|`SWITCH_MODIFY`|<span data-ttu-id="c308c-109">Se ha modificado un conmutador de depuración y seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c308c-109">A debugging/tracing switch was modified.</span></span>|  
|`SWITCH_DELETE`|<span data-ttu-id="c308c-110">Se ha eliminado un conmutador de depuración y seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c308c-110">A debugging/tracing switch was deleted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c308c-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c308c-111">Requirements</span></span>  
 <span data-ttu-id="c308c-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c308c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c308c-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c308c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c308c-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c308c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c308c-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c308c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c308c-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c308c-116">See also</span></span>

- [<span data-ttu-id="c308c-117">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="c308c-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
