---
title: Interfaz ICorDebugDebugEvent
ms.date: 03/30/2017
ms.assetid: a226737a-cb99-4e97-bd94-9a37094ded41
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 550cb6379ef0d5d17a3446b3f21120208b5a3dad
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59110193"
---
# <a name="icordebugdebugevent-interface"></a><span data-ttu-id="052a4-102">Interfaz ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="052a4-102">ICorDebugDebugEvent Interface</span></span>
<span data-ttu-id="052a4-103">Define la interfaz base de la que derivan todos los eventos de depuración `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="052a4-103">Defines the base interface from which all `ICorDebug` debug events derive.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="052a4-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="052a4-104">Methods</span></span>  
  
|<span data-ttu-id="052a4-105">Método</span><span class="sxs-lookup"><span data-stu-id="052a4-105">Method</span></span>|<span data-ttu-id="052a4-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="052a4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="052a4-107">Método GetEventKind</span><span class="sxs-lookup"><span data-stu-id="052a4-107">GetEventKind Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md)|<span data-ttu-id="052a4-108">Indica el tipo de evento que este objeto `ICorDebugDebugEvent` representa.</span><span class="sxs-lookup"><span data-stu-id="052a4-108">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>|  
|[<span data-ttu-id="052a4-109">Método GetThread</span><span class="sxs-lookup"><span data-stu-id="052a4-109">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-getthread-method.md)|<span data-ttu-id="052a4-110">Obtiene el subproceso en el que se produjo el evento.</span><span class="sxs-lookup"><span data-stu-id="052a4-110">Gets the thread on which the event occurred.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="052a4-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="052a4-111">Remarks</span></span>  
 <span data-ttu-id="052a4-112">Las interfaces siguientes derivan de la interfaz `ICorDebugDebugEvent`:</span><span class="sxs-lookup"><span data-stu-id="052a4-112">The following interfaces are derived from the `ICorDebugDebugEvent` interface:</span></span>  
  
-   [<span data-ttu-id="052a4-113">ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="052a4-113">ICorDebugExceptionDebugEvent</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
  
-   [<span data-ttu-id="052a4-114">ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="052a4-114">ICorDebugModuleDebugEvent</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)  
  
> [!NOTE]
>  <span data-ttu-id="052a4-115">La interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="052a4-115">The interface is available with .NET Native only.</span></span> <span data-ttu-id="052a4-116">Al intentar llamar a `QueryInterface` para recuperar un puntero a interfaz, devuelve `E_NOINTERFACE` para escenarios de ICorDebug fuera de .NET nativo.</span><span class="sxs-lookup"><span data-stu-id="052a4-116">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="052a4-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="052a4-117">Requirements</span></span>  
 <span data-ttu-id="052a4-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="052a4-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="052a4-119">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="052a4-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="052a4-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="052a4-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="052a4-121">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="052a4-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="052a4-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="052a4-122">See also</span></span>

- [<span data-ttu-id="052a4-123">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="052a4-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="052a4-124">Depuración</span><span class="sxs-lookup"><span data-stu-id="052a4-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
