---
title: ICorDebugModuleBreakpoint (Interfaz)
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
ms.openlocfilehash: 3916bf8f7792e82ba905554bb32696f81634f819
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56971525"
---
# <a name="icordebugmodulebreakpoint-interface"></a><span data-ttu-id="46c7f-102">ICorDebugModuleBreakpoint (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="46c7f-102">ICorDebugModuleBreakpoint Interface</span></span>

<span data-ttu-id="46c7f-103">Proporciona acceso a módulos específicos.</span><span class="sxs-lookup"><span data-stu-id="46c7f-103">Provides access to specific modules.</span></span> <span data-ttu-id="46c7f-104">Esta interfaz es una subclase de ICorDebugBreakpoint (interfaz).</span><span class="sxs-lookup"><span data-stu-id="46c7f-104">This interface is a subclass of the ICorDebugBreakpoint interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="46c7f-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="46c7f-105">Methods</span></span>  
  
|<span data-ttu-id="46c7f-106">Método</span><span class="sxs-lookup"><span data-stu-id="46c7f-106">Method</span></span>|<span data-ttu-id="46c7f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="46c7f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="46c7f-108">GetModule (método)</span><span class="sxs-lookup"><span data-stu-id="46c7f-108">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodulebreakpoint-getmodule-method.md)|<span data-ttu-id="46c7f-109">Obtiene un puntero de interfaz a una instancia de ICorDebugModule que hace referencia al módulo donde se establece este punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="46c7f-109">Gets an interface pointer to an ICorDebugModule that references the module where this breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46c7f-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="46c7f-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="46c7f-111">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="46c7f-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46c7f-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="46c7f-112">Requirements</span></span>  
 <span data-ttu-id="46c7f-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46c7f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46c7f-114">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="46c7f-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="46c7f-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46c7f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46c7f-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46c7f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46c7f-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="46c7f-117">See also</span></span>
- [<span data-ttu-id="46c7f-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="46c7f-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
