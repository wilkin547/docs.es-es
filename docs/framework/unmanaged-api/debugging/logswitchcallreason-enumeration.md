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
ms.openlocfilehash: 7eadb595eb62b4f1a9dcc888225cbb7454119c7c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59198496"
---
# <a name="logswitchcallreason-enumeration"></a><span data-ttu-id="f23eb-102">LogSwitchCallReason (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="f23eb-102">LogSwitchCallReason Enumeration</span></span>
<span data-ttu-id="f23eb-103">Indica la operación que se realizó en un conmutador de depuración/seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f23eb-103">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f23eb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f23eb-104">Syntax</span></span>  
  
```  
typedef enum LogSwitchCallReason {  
    SWITCH_CREATE,  
    SWITCH_MODIFY,  
    SWITCH_DELETE  
} LogSwitchCallReason;  
```  
  
## <a name="members"></a><span data-ttu-id="f23eb-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="f23eb-105">Members</span></span>  
  
|<span data-ttu-id="f23eb-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="f23eb-106">Member</span></span>|<span data-ttu-id="f23eb-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f23eb-107">Description</span></span>|  
|------------|-----------------|  
|`SWITCH_CREATE`|<span data-ttu-id="f23eb-108">Se creó un conmutador de depuración y seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f23eb-108">A debugging/tracing switch was created.</span></span>|  
|`SWITCH_MODIFY`|<span data-ttu-id="f23eb-109">Se ha modificado un conmutador de depuración y seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f23eb-109">A debugging/tracing switch was modified.</span></span>|  
|`SWITCH_DELETE`|<span data-ttu-id="f23eb-110">Se ha eliminado un conmutador de depuración y seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f23eb-110">A debugging/tracing switch was deleted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f23eb-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f23eb-111">Requirements</span></span>  
 <span data-ttu-id="f23eb-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f23eb-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f23eb-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f23eb-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f23eb-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f23eb-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f23eb-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f23eb-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f23eb-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="f23eb-116">See also</span></span>

- [<span data-ttu-id="f23eb-117">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="f23eb-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
