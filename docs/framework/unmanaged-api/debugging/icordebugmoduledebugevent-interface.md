---
title: Interfaz ICorDebugModuleDebugEvent
ms.date: 03/30/2017
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
ms.openlocfilehash: cca181c6af6db9f35ff7913e045a30e37e07a5e6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73110250"
---
# <a name="icordebugmoduledebugevent-interface"></a><span data-ttu-id="0ec3e-102">Interfaz ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="0ec3e-102">ICorDebugModuleDebugEvent Interface</span></span>
<span data-ttu-id="0ec3e-103">Extiende la interfaz [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) para admitir eventos de nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="0ec3e-103">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support module-level events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0ec3e-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="0ec3e-104">Methods</span></span>  
  
|<span data-ttu-id="0ec3e-105">Método</span><span class="sxs-lookup"><span data-stu-id="0ec3e-105">Method</span></span>|<span data-ttu-id="0ec3e-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="0ec3e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0ec3e-107">GetModule (método)</span><span class="sxs-lookup"><span data-stu-id="0ec3e-107">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-getmodule-method.md)|<span data-ttu-id="0ec3e-108">Obtiene el módulo combinado que se acaba de cargar o descargar.</span><span class="sxs-lookup"><span data-stu-id="0ec3e-108">Gets the merged module that was just loaded or unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ec3e-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0ec3e-109">Remarks</span></span>  
 <span data-ttu-id="0ec3e-110">Los tipos de eventos [MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) y [MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) implementan esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="0ec3e-110">The [MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) and [MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) event types implement this interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0ec3e-111">La interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="0ec3e-111">The interface is available with .NET Native only.</span></span> <span data-ttu-id="0ec3e-112">Al intentar llamar a `QueryInterface` para recuperar un puntero a interfaz, devuelve `E_NOINTERFACE` para escenarios de ICorDebug fuera de .NET nativo.</span><span class="sxs-lookup"><span data-stu-id="0ec3e-112">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ec3e-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0ec3e-113">Requirements</span></span>  
 <span data-ttu-id="0ec3e-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ec3e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ec3e-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0ec3e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0ec3e-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ec3e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ec3e-117">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ec3e-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ec3e-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ec3e-118">See also</span></span>

- [<span data-ttu-id="0ec3e-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="0ec3e-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="0ec3e-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="0ec3e-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
