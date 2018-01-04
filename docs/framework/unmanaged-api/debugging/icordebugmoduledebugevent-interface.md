---
title: ICorDebugModuleDebugEvent (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 86cf571180b2df15077547fac3d5dd058dbee83b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmoduledebugevent-interface"></a><span data-ttu-id="1de18-102">ICorDebugModuleDebugEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1de18-102">ICorDebugModuleDebugEvent Interface</span></span>
<span data-ttu-id="1de18-103">Extiende la [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interfaz para admitir eventos de nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="1de18-103">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support module-level events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1de18-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="1de18-104">Methods</span></span>  
  
|<span data-ttu-id="1de18-105">Método</span><span class="sxs-lookup"><span data-stu-id="1de18-105">Method</span></span>|<span data-ttu-id="1de18-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="1de18-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1de18-107">GetModule (método)</span><span class="sxs-lookup"><span data-stu-id="1de18-107">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-getmodule-method.md)|<span data-ttu-id="1de18-108">Obtiene el módulo combinado que se acaba de cargar o descargar.</span><span class="sxs-lookup"><span data-stu-id="1de18-108">Gets the merged module that was just loaded or unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1de18-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1de18-109">Remarks</span></span>  
 <span data-ttu-id="1de18-110">El [MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) y [MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) tipos de evento implementan esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="1de18-110">The [MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) and [MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) event types implement this interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1de18-111">La interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="1de18-111">The interface is available with .NET Native only.</span></span> <span data-ttu-id="1de18-112">Al intentar llamar a `QueryInterface` para recuperar un puntero a interfaz, devuelve `E_NOINTERFACE` para escenarios de ICorDebug fuera de .NET nativo.</span><span class="sxs-lookup"><span data-stu-id="1de18-112">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1de18-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1de18-113">Requirements</span></span>  
 <span data-ttu-id="1de18-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1de18-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1de18-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1de18-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1de18-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1de18-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1de18-117">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1de18-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1de18-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="1de18-118">See Also</span></span>  
 [<span data-ttu-id="1de18-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="1de18-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="1de18-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="1de18-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
