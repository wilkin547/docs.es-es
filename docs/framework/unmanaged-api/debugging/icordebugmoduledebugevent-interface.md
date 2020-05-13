---
title: Interfaz ICorDebugModuleDebugEvent
ms.date: 03/30/2017
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
ms.openlocfilehash: ec6bad730d807b9a36ce5bba1c6f5d80da375f6d
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213338"
---
# <a name="icordebugmoduledebugevent-interface"></a><span data-ttu-id="fa891-102">Interfaz ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="fa891-102">ICorDebugModuleDebugEvent Interface</span></span>
<span data-ttu-id="fa891-103">Extiende la interfaz [ICorDebugDebugEvent](icordebugdebugevent-interface.md) para admitir eventos de nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="fa891-103">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support module-level events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fa891-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="fa891-104">Methods</span></span>  
  
|<span data-ttu-id="fa891-105">Método</span><span class="sxs-lookup"><span data-stu-id="fa891-105">Method</span></span>|<span data-ttu-id="fa891-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="fa891-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fa891-107">GetModule (Método)</span><span class="sxs-lookup"><span data-stu-id="fa891-107">GetModule Method</span></span>](icordebugmoduledebugevent-getmodule-method.md)|<span data-ttu-id="fa891-108">Obtiene el módulo combinado que se acaba de cargar o descargar.</span><span class="sxs-lookup"><span data-stu-id="fa891-108">Gets the merged module that was just loaded or unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa891-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fa891-109">Remarks</span></span>  
 <span data-ttu-id="fa891-110">Los tipos de evento [MODULE_LOADED](cordebugdebugeventkind-enumeration.md) y [MODULE_UNLOADED](cordebugdebugeventkind-enumeration.md) implementan esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="fa891-110">The [MODULE_LOADED](cordebugdebugeventkind-enumeration.md) and [MODULE_UNLOADED](cordebugdebugeventkind-enumeration.md) event types implement this interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fa891-111">La interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="fa891-111">The interface is available with .NET Native only.</span></span> <span data-ttu-id="fa891-112">Al intentar llamar a `QueryInterface` para recuperar un puntero a interfaz, devuelve `E_NOINTERFACE` para escenarios de ICorDebug fuera de .NET nativo.</span><span class="sxs-lookup"><span data-stu-id="fa891-112">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa891-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fa891-113">Requirements</span></span>  
 <span data-ttu-id="fa891-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa891-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa891-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fa891-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fa891-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa891-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa891-117">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa891-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa891-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fa891-118">See also</span></span>

- [<span data-ttu-id="fa891-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="fa891-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="fa891-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="fa891-120">Debugging</span></span>](index.md)
