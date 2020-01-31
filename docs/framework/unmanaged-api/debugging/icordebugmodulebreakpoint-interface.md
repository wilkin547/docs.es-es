---
title: Interfaz ICorDebugModuleBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugModuleBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleBreakpoint
helpviewer_keywords:
- ICorDebugModuleBreakpoint interface [.NET Framework debugging]
ms.assetid: 34667162-f314-475f-ae1b-ce9cb0fcbb83
topic_type:
- apiref
ms.openlocfilehash: df3ad3fa4ef4eeee7e23ca1629da7a8b8ce09711
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792922"
---
# <a name="icordebugmodulebreakpoint-interface"></a><span data-ttu-id="be2a5-102">Interfaz ICorDebugModuleBreakpoint</span><span class="sxs-lookup"><span data-stu-id="be2a5-102">ICorDebugModuleBreakpoint Interface</span></span>

<span data-ttu-id="be2a5-103">Proporciona acceso a módulos específicos.</span><span class="sxs-lookup"><span data-stu-id="be2a5-103">Provides access to specific modules.</span></span> <span data-ttu-id="be2a5-104">Esta interfaz es una subclase de la interfaz ICorDebugBreakpoint.</span><span class="sxs-lookup"><span data-stu-id="be2a5-104">This interface is a subclass of the ICorDebugBreakpoint interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="be2a5-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="be2a5-105">Methods</span></span>  
  
|<span data-ttu-id="be2a5-106">Método</span><span class="sxs-lookup"><span data-stu-id="be2a5-106">Method</span></span>|<span data-ttu-id="be2a5-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="be2a5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="be2a5-108">GetModule (método)</span><span class="sxs-lookup"><span data-stu-id="be2a5-108">GetModule Method</span></span>](icordebugmodulebreakpoint-getmodule-method.md)|<span data-ttu-id="be2a5-109">Obtiene un puntero de interfaz a una ICorDebugModule que hace referencia al módulo donde se establece este punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="be2a5-109">Gets an interface pointer to an ICorDebugModule that references the module where this breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be2a5-110">Notas</span><span class="sxs-lookup"><span data-stu-id="be2a5-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="be2a5-111">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="be2a5-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be2a5-112">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="be2a5-112">Requirements</span></span>  
 <span data-ttu-id="be2a5-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be2a5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be2a5-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="be2a5-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="be2a5-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be2a5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="be2a5-116">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be2a5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be2a5-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="be2a5-117">See also</span></span>

- [<span data-ttu-id="be2a5-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="be2a5-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
