---
title: Interfaz ICorDebugDebugEvent
ms.date: 03/30/2017
ms.assetid: a226737a-cb99-4e97-bd94-9a37094ded41
ms.openlocfilehash: a66012651d4b307d06a5a3bff675a248cc0ee376
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976361"
---
# <a name="icordebugdebugevent-interface"></a><span data-ttu-id="5f8af-102">Interfaz ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="5f8af-102">ICorDebugDebugEvent Interface</span></span>
<span data-ttu-id="5f8af-103">Define la interfaz base de la que derivan todos los eventos de depuración `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="5f8af-103">Defines the base interface from which all `ICorDebug` debug events derive.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5f8af-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="5f8af-104">Methods</span></span>  
  
|<span data-ttu-id="5f8af-105">Método</span><span class="sxs-lookup"><span data-stu-id="5f8af-105">Method</span></span>|<span data-ttu-id="5f8af-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="5f8af-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5f8af-107">Método GetEventKind</span><span class="sxs-lookup"><span data-stu-id="5f8af-107">GetEventKind Method</span></span>](icordebugdebugevent-geteventkind-method.md)|<span data-ttu-id="5f8af-108">Indica el tipo de evento que este objeto `ICorDebugDebugEvent` representa.</span><span class="sxs-lookup"><span data-stu-id="5f8af-108">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>|  
|[<span data-ttu-id="5f8af-109">Método GetThread</span><span class="sxs-lookup"><span data-stu-id="5f8af-109">GetThread Method</span></span>](icordebugdebugevent-getthread-method.md)|<span data-ttu-id="5f8af-110">Obtiene el subproceso en el que se produjo el evento.</span><span class="sxs-lookup"><span data-stu-id="5f8af-110">Gets the thread on which the event occurred.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5f8af-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5f8af-111">Remarks</span></span>  
 <span data-ttu-id="5f8af-112">Las interfaces siguientes derivan de la interfaz `ICorDebugDebugEvent`:</span><span class="sxs-lookup"><span data-stu-id="5f8af-112">The following interfaces are derived from the `ICorDebugDebugEvent` interface:</span></span>  
  
- [<span data-ttu-id="5f8af-113">ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="5f8af-113">ICorDebugExceptionDebugEvent</span></span>](icordebugexceptiondebugevent-interface.md)  
  
- [<span data-ttu-id="5f8af-114">ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="5f8af-114">ICorDebugModuleDebugEvent</span></span>](icordebugmoduledebugevent-interface.md)  
  
> [!NOTE]
> <span data-ttu-id="5f8af-115">La interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="5f8af-115">The interface is available with .NET Native only.</span></span> <span data-ttu-id="5f8af-116">Al intentar llamar a `QueryInterface` para recuperar un puntero a interfaz, devuelve `E_NOINTERFACE` para escenarios de ICorDebug fuera de .NET nativo.</span><span class="sxs-lookup"><span data-stu-id="5f8af-116">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f8af-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5f8af-117">Requirements</span></span>  
 <span data-ttu-id="5f8af-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f8af-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f8af-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5f8af-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5f8af-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f8af-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f8af-121">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f8af-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f8af-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5f8af-122">See also</span></span>

- [<span data-ttu-id="5f8af-123">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="5f8af-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="5f8af-124">Depuración</span><span class="sxs-lookup"><span data-stu-id="5f8af-124">Debugging</span></span>](index.md)
