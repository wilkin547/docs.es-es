---
title: ICorDebugModuleBreakpoint Interfaz1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModuleBreakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModuleBreakpoint
helpviewer_keywords: ICorDebugModuleBreakpoint interface [.NET Framework debugging]
ms.assetid: 34667162-f314-475f-ae1b-ce9cb0fcbb83
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cec51a7efe17c2188f12039333dd90f557b1e724
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodulebreakpoint-interface1"></a><span data-ttu-id="7e258-102">ICorDebugModuleBreakpoint Interfaz1</span><span class="sxs-lookup"><span data-stu-id="7e258-102">ICorDebugModuleBreakpoint Interface1</span></span>
<span data-ttu-id="7e258-103">Proporciona acceso a módulos concretos.</span><span class="sxs-lookup"><span data-stu-id="7e258-103">Provides access to specific modules.</span></span> <span data-ttu-id="7e258-104">Esta interfaz es una subclase de ICorDebugBreakpoint (interfaz).</span><span class="sxs-lookup"><span data-stu-id="7e258-104">This interface is a subclass of the ICorDebugBreakpoint interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7e258-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="7e258-105">Methods</span></span>  
  
|<span data-ttu-id="7e258-106">Método</span><span class="sxs-lookup"><span data-stu-id="7e258-106">Method</span></span>|<span data-ttu-id="7e258-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="7e258-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7e258-108">GetModule (método)</span><span class="sxs-lookup"><span data-stu-id="7e258-108">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodulebreakpoint-getmodule-method.md)|<span data-ttu-id="7e258-109">Obtiene un puntero de interfaz a una instancia de ICorDebugModule que hace referencia al módulo donde se ha establecido este punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="7e258-109">Gets an interface pointer to an ICorDebugModule that references the module where this breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e258-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7e258-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7e258-111">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="7e258-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e258-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7e258-112">Requirements</span></span>  
 <span data-ttu-id="7e258-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e258-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e258-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7e258-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7e258-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e258-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7e258-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e258-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e258-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e258-117">See Also</span></span>  
 [<span data-ttu-id="7e258-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="7e258-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
