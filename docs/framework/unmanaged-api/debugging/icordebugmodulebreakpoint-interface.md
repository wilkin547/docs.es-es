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
ms.openlocfilehash: d6a43a264fcaa94ce4e629d8db504e9d416f6b89
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59179717"
---
# <a name="icordebugmodulebreakpoint-interface"></a><span data-ttu-id="e34e4-102">Interfaz ICorDebugModuleBreakpoint</span><span class="sxs-lookup"><span data-stu-id="e34e4-102">ICorDebugModuleBreakpoint Interface</span></span>

<span data-ttu-id="e34e4-103">Proporciona acceso a módulos específicos.</span><span class="sxs-lookup"><span data-stu-id="e34e4-103">Provides access to specific modules.</span></span> <span data-ttu-id="e34e4-104">Esta interfaz es una subclase de ICorDebugBreakpoint (interfaz).</span><span class="sxs-lookup"><span data-stu-id="e34e4-104">This interface is a subclass of the ICorDebugBreakpoint interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e34e4-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="e34e4-105">Methods</span></span>  
  
|<span data-ttu-id="e34e4-106">Método</span><span class="sxs-lookup"><span data-stu-id="e34e4-106">Method</span></span>|<span data-ttu-id="e34e4-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e34e4-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e34e4-108">GetModule (método)</span><span class="sxs-lookup"><span data-stu-id="e34e4-108">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodulebreakpoint-getmodule-method.md)|<span data-ttu-id="e34e4-109">Obtiene un puntero de interfaz a una instancia de ICorDebugModule que hace referencia al módulo donde se establece este punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="e34e4-109">Gets an interface pointer to an ICorDebugModule that references the module where this breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e34e4-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e34e4-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e34e4-111">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="e34e4-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e34e4-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e34e4-112">Requirements</span></span>  
 <span data-ttu-id="e34e4-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e34e4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e34e4-114">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e34e4-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e34e4-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e34e4-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e34e4-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e34e4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e34e4-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="e34e4-117">See also</span></span>

- [<span data-ttu-id="e34e4-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="e34e4-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
