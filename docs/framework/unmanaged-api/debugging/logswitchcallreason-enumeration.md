---
description: 'Más información sobre: enumeración Logswitchcallreason ('
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
ms.openlocfilehash: 46c457ee4c12fe9a73796aa7b7a5f599d90c9c6c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800620"
---
# <a name="logswitchcallreason-enumeration"></a><span data-ttu-id="ee50d-103">LogSwitchCallReason (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="ee50d-103">LogSwitchCallReason Enumeration</span></span>

<span data-ttu-id="ee50d-104">Indica la operación que se realizó en un conmutador de depuración/seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ee50d-104">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee50d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ee50d-105">Syntax</span></span>  
  
```cpp  
typedef enum LogSwitchCallReason {  
    SWITCH_CREATE,  
    SWITCH_MODIFY,  
    SWITCH_DELETE  
} LogSwitchCallReason;  
```  
  
## <a name="members"></a><span data-ttu-id="ee50d-106">Members</span><span class="sxs-lookup"><span data-stu-id="ee50d-106">Members</span></span>  
  
|<span data-ttu-id="ee50d-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="ee50d-107">Member</span></span>|<span data-ttu-id="ee50d-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="ee50d-108">Description</span></span>|  
|------------|-----------------|  
|`SWITCH_CREATE`|<span data-ttu-id="ee50d-109">Se creó un modificador de depuración o traza.</span><span class="sxs-lookup"><span data-stu-id="ee50d-109">A debugging/tracing switch was created.</span></span>|  
|`SWITCH_MODIFY`|<span data-ttu-id="ee50d-110">Se modificó un modificador de depuración o traza.</span><span class="sxs-lookup"><span data-stu-id="ee50d-110">A debugging/tracing switch was modified.</span></span>|  
|`SWITCH_DELETE`|<span data-ttu-id="ee50d-111">Se eliminó un modificador de depuración o traza.</span><span class="sxs-lookup"><span data-stu-id="ee50d-111">A debugging/tracing switch was deleted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ee50d-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ee50d-112">Requirements</span></span>  

 <span data-ttu-id="ee50d-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee50d-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee50d-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ee50d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ee50d-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee50d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee50d-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee50d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee50d-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="ee50d-117">See also</span></span>

- [<span data-ttu-id="ee50d-118">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="ee50d-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
