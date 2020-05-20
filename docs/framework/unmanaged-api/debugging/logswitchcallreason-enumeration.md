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
ms.openlocfilehash: 4d29bb3886ffb51e1dfb9654f4d70ef7c568fd43
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420713"
---
# <a name="logswitchcallreason-enumeration"></a><span data-ttu-id="69e98-102">LogSwitchCallReason (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="69e98-102">LogSwitchCallReason Enumeration</span></span>
<span data-ttu-id="69e98-103">Indica la operación que se realizó en un conmutador de depuración/seguimiento.</span><span class="sxs-lookup"><span data-stu-id="69e98-103">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69e98-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="69e98-104">Syntax</span></span>  
  
```cpp  
typedef enum LogSwitchCallReason {  
    SWITCH_CREATE,  
    SWITCH_MODIFY,  
    SWITCH_DELETE  
} LogSwitchCallReason;  
```  
  
## <a name="members"></a><span data-ttu-id="69e98-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="69e98-105">Members</span></span>  
  
|<span data-ttu-id="69e98-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="69e98-106">Member</span></span>|<span data-ttu-id="69e98-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="69e98-107">Description</span></span>|  
|------------|-----------------|  
|`SWITCH_CREATE`|<span data-ttu-id="69e98-108">Se creó un modificador de depuración o traza.</span><span class="sxs-lookup"><span data-stu-id="69e98-108">A debugging/tracing switch was created.</span></span>|  
|`SWITCH_MODIFY`|<span data-ttu-id="69e98-109">Se modificó un modificador de depuración o traza.</span><span class="sxs-lookup"><span data-stu-id="69e98-109">A debugging/tracing switch was modified.</span></span>|  
|`SWITCH_DELETE`|<span data-ttu-id="69e98-110">Se eliminó un modificador de depuración o traza.</span><span class="sxs-lookup"><span data-stu-id="69e98-110">A debugging/tracing switch was deleted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="69e98-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="69e98-111">Requirements</span></span>  
 <span data-ttu-id="69e98-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69e98-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69e98-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="69e98-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="69e98-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69e98-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="69e98-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69e98-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69e98-116">Consulta también</span><span class="sxs-lookup"><span data-stu-id="69e98-116">See also</span></span>

- [<span data-ttu-id="69e98-117">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="69e98-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
