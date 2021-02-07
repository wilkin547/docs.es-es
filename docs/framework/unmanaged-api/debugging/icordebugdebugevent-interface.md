---
description: 'Más información acerca de: interfaz ICorDebugDebugEvent'
title: Interfaz ICorDebugDebugEvent
ms.date: 03/30/2017
ms.assetid: a226737a-cb99-4e97-bd94-9a37094ded41
ms.openlocfilehash: 5735be22b76e9f74847bb5138c00130f28dbfc96
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764312"
---
# <a name="icordebugdebugevent-interface"></a><span data-ttu-id="e804b-103">Interfaz ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="e804b-103">ICorDebugDebugEvent Interface</span></span>

<span data-ttu-id="e804b-104">Define la interfaz base de la que derivan todos los eventos de depuración `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="e804b-104">Defines the base interface from which all `ICorDebug` debug events derive.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e804b-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="e804b-105">Methods</span></span>  
  
|<span data-ttu-id="e804b-106">Método</span><span class="sxs-lookup"><span data-stu-id="e804b-106">Method</span></span>|<span data-ttu-id="e804b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e804b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e804b-108">Método GetEventKind</span><span class="sxs-lookup"><span data-stu-id="e804b-108">GetEventKind Method</span></span>](icordebugdebugevent-geteventkind-method.md)|<span data-ttu-id="e804b-109">Indica el tipo de evento que este objeto `ICorDebugDebugEvent` representa.</span><span class="sxs-lookup"><span data-stu-id="e804b-109">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>|  
|[<span data-ttu-id="e804b-110">Método GetThread</span><span class="sxs-lookup"><span data-stu-id="e804b-110">GetThread Method</span></span>](icordebugdebugevent-getthread-method.md)|<span data-ttu-id="e804b-111">Obtiene el subproceso en el que se produjo el evento.</span><span class="sxs-lookup"><span data-stu-id="e804b-111">Gets the thread on which the event occurred.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e804b-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e804b-112">Remarks</span></span>  

 <span data-ttu-id="e804b-113">Las interfaces siguientes derivan de la interfaz `ICorDebugDebugEvent`:</span><span class="sxs-lookup"><span data-stu-id="e804b-113">The following interfaces are derived from the `ICorDebugDebugEvent` interface:</span></span>  
  
- [<span data-ttu-id="e804b-114">ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="e804b-114">ICorDebugExceptionDebugEvent</span></span>](icordebugexceptiondebugevent-interface.md)  
  
- [<span data-ttu-id="e804b-115">ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="e804b-115">ICorDebugModuleDebugEvent</span></span>](icordebugmoduledebugevent-interface.md)  
  
> [!NOTE]
> <span data-ttu-id="e804b-116">La interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e804b-116">The interface is available with .NET Native only.</span></span> <span data-ttu-id="e804b-117">Al intentar llamar a `QueryInterface` para recuperar un puntero a interfaz, devuelve `E_NOINTERFACE` para escenarios de ICorDebug fuera de .NET nativo.</span><span class="sxs-lookup"><span data-stu-id="e804b-117">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e804b-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e804b-118">Requirements</span></span>  

 <span data-ttu-id="e804b-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e804b-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e804b-120">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e804b-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e804b-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e804b-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e804b-122">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e804b-122">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e804b-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="e804b-123">See also</span></span>

- [<span data-ttu-id="e804b-124">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="e804b-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="e804b-125">Depuración</span><span class="sxs-lookup"><span data-stu-id="e804b-125">Debugging</span></span>](index.md)
