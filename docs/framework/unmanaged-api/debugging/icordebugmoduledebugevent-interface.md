---
title: ICorDebugModuleDebugEvent (Interfaz)
ms.date: 03/30/2017
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
ms.openlocfilehash: a2c7eaa8a2c811c1696024d9af4b715cc49e7caa
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792897"
---
# <a name="icordebugmoduledebugevent-interface"></a><span data-ttu-id="cd0c1-102">ICorDebugModuleDebugEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cd0c1-102">ICorDebugModuleDebugEvent Interface</span></span>
<span data-ttu-id="cd0c1-103">Extiende la interfaz [ICorDebugDebugEvent](icordebugdebugevent-interface.md) para admitir eventos de nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="cd0c1-103">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support module-level events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cd0c1-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="cd0c1-104">Methods</span></span>  
  
|<span data-ttu-id="cd0c1-105">Método</span><span class="sxs-lookup"><span data-stu-id="cd0c1-105">Method</span></span>|<span data-ttu-id="cd0c1-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="cd0c1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cd0c1-107">GetModule (método)</span><span class="sxs-lookup"><span data-stu-id="cd0c1-107">GetModule Method</span></span>](icordebugmoduledebugevent-getmodule-method.md)|<span data-ttu-id="cd0c1-108">Obtiene el módulo combinado que se acaba de cargar o descargar.</span><span class="sxs-lookup"><span data-stu-id="cd0c1-108">Gets the merged module that was just loaded or unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd0c1-109">Notas</span><span class="sxs-lookup"><span data-stu-id="cd0c1-109">Remarks</span></span>  
 <span data-ttu-id="cd0c1-110">Los tipos de evento [MODULE_LOADED](cordebugdebugeventkind-enumeration.md) y [MODULE_UNLOADED](cordebugdebugeventkind-enumeration.md) implementan esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="cd0c1-110">The [MODULE_LOADED](cordebugdebugeventkind-enumeration.md) and [MODULE_UNLOADED](cordebugdebugeventkind-enumeration.md) event types implement this interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cd0c1-111">La interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="cd0c1-111">The interface is available with .NET Native only.</span></span> <span data-ttu-id="cd0c1-112">Al intentar llamar a `QueryInterface` para recuperar un puntero a interfaz, devuelve `E_NOINTERFACE` para escenarios de ICorDebug fuera de .NET nativo.</span><span class="sxs-lookup"><span data-stu-id="cd0c1-112">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd0c1-113">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="cd0c1-113">Requirements</span></span>  
 <span data-ttu-id="cd0c1-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd0c1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd0c1-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cd0c1-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cd0c1-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd0c1-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd0c1-117">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd0c1-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd0c1-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="cd0c1-118">See also</span></span>

- [<span data-ttu-id="cd0c1-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="cd0c1-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="cd0c1-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="cd0c1-120">Debugging</span></span>](index.md)
