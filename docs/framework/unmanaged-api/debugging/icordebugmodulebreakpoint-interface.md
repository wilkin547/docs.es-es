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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03616f2756830e180155102492b15e18fee1085c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965127"
---
# <a name="icordebugmodulebreakpoint-interface"></a><span data-ttu-id="3e9e6-102">Interfaz ICorDebugModuleBreakpoint</span><span class="sxs-lookup"><span data-stu-id="3e9e6-102">ICorDebugModuleBreakpoint Interface</span></span>

<span data-ttu-id="3e9e6-103">Proporciona acceso a módulos específicos.</span><span class="sxs-lookup"><span data-stu-id="3e9e6-103">Provides access to specific modules.</span></span> <span data-ttu-id="3e9e6-104">Esta interfaz es una subclase de la interfaz ICorDebugBreakpoint.</span><span class="sxs-lookup"><span data-stu-id="3e9e6-104">This interface is a subclass of the ICorDebugBreakpoint interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3e9e6-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="3e9e6-105">Methods</span></span>  
  
|<span data-ttu-id="3e9e6-106">Método</span><span class="sxs-lookup"><span data-stu-id="3e9e6-106">Method</span></span>|<span data-ttu-id="3e9e6-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3e9e6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3e9e6-108">GetModule (método)</span><span class="sxs-lookup"><span data-stu-id="3e9e6-108">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodulebreakpoint-getmodule-method.md)|<span data-ttu-id="3e9e6-109">Obtiene un puntero de interfaz a una ICorDebugModule que hace referencia al módulo donde se establece este punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="3e9e6-109">Gets an interface pointer to an ICorDebugModule that references the module where this breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e9e6-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3e9e6-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3e9e6-111">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="3e9e6-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e9e6-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3e9e6-112">Requirements</span></span>  
 <span data-ttu-id="3e9e6-113">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e9e6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e9e6-114">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="3e9e6-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3e9e6-115">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e9e6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3e9e6-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e9e6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e9e6-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e9e6-117">See also</span></span>

- [<span data-ttu-id="3e9e6-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="3e9e6-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
