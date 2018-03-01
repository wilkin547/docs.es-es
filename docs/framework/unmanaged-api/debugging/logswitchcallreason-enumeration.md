---
title: "LogSwitchCallReason (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3dcd91001dfd823416b08ba49ba4ed12a2c4d058
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="logswitchcallreason-enumeration"></a><span data-ttu-id="c4465-102">LogSwitchCallReason (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="c4465-102">LogSwitchCallReason Enumeration</span></span>
<span data-ttu-id="c4465-103">Indica la operación que se realizó en un conmutador de depuración/seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c4465-103">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4465-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c4465-104">Syntax</span></span>  
  
```  
typedef enum LogSwitchCallReason {  
    SWITCH_CREATE,  
    SWITCH_MODIFY,  
    SWITCH_DELETE  
} LogSwitchCallReason;  
```  
  
## <a name="members"></a><span data-ttu-id="c4465-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="c4465-105">Members</span></span>  
  
|<span data-ttu-id="c4465-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="c4465-106">Member</span></span>|<span data-ttu-id="c4465-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c4465-107">Description</span></span>|  
|------------|-----------------|  
|`SWITCH_CREATE`|<span data-ttu-id="c4465-108">Se creó un conmutador de depuración/seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c4465-108">A debugging/tracing switch was created.</span></span>|  
|`SWITCH_MODIFY`|<span data-ttu-id="c4465-109">Se ha modificado un conmutador de depuración/seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c4465-109">A debugging/tracing switch was modified.</span></span>|  
|`SWITCH_DELETE`|<span data-ttu-id="c4465-110">Se eliminó un modificador de depuración o traza.</span><span class="sxs-lookup"><span data-stu-id="c4465-110">A debugging/tracing switch was deleted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c4465-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c4465-111">Requirements</span></span>  
 <span data-ttu-id="c4465-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4465-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4465-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c4465-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4465-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4465-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4465-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4465-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4465-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4465-116">See Also</span></span>  
 [<span data-ttu-id="c4465-117">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="c4465-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
