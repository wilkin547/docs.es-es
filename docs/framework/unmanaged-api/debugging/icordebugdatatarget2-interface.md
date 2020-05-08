---
title: Interfaz ICorDebugDataTarget2
ms.date: 03/30/2017
ms.assetid: 13f11388-2f91-48d8-98d6-6a4a63cb5746
ms.openlocfilehash: 1c598d23cac77e50cf302e6936b88b5eb6e558c2
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976440"
---
# <a name="icordebugdatatarget2-interface"></a><span data-ttu-id="f91fc-102">Interfaz ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="f91fc-102">ICorDebugDataTarget2 Interface</span></span>
<span data-ttu-id="f91fc-103">Extiende lógicamente la interfaz [ICorDebugDataTarget](icordebugdatatarget-interface.md).</span><span class="sxs-lookup"><span data-stu-id="f91fc-103">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md)interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f91fc-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="f91fc-104">Methods</span></span>  
  
|<span data-ttu-id="f91fc-105">Método</span><span class="sxs-lookup"><span data-stu-id="f91fc-105">Method</span></span>|<span data-ttu-id="f91fc-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f91fc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f91fc-107">Método CreateVirtualUnwinder</span><span class="sxs-lookup"><span data-stu-id="f91fc-107">CreateVirtualUnwinder Method</span></span>](icordebugdatatarget2-createvirtualunwinder-method.md)|<span data-ttu-id="f91fc-108">Crea un nuevo desenredador de pila que inicia el desenredo desde un contexto inicial (que no tiene por qué ser la hoja de un subproceso).</span><span class="sxs-lookup"><span data-stu-id="f91fc-108">Creates a new stack unwinder that starts unwinding from an initial context (which isn't necessarily the leaf of a thread).</span></span>|  
|[<span data-ttu-id="f91fc-109">Método EnumerateThreadIDs</span><span class="sxs-lookup"><span data-stu-id="f91fc-109">EnumerateThreadIDs Method</span></span>](icordebugdatatarget2-enumeratethreadids-method.md)|<span data-ttu-id="f91fc-110">Devuelve una lista de identificadores de subprocesos activos.</span><span class="sxs-lookup"><span data-stu-id="f91fc-110">Returns a list of active thread IDs.</span></span>|  
|[<span data-ttu-id="f91fc-111">Método GetImageFromPointer</span><span class="sxs-lookup"><span data-stu-id="f91fc-111">GetImageFromPointer Method</span></span>](icordebugdatatarget2-getimagefrompointer-method.md)|<span data-ttu-id="f91fc-112">Devuelve el tamaño y dirección base del módulo a partir de una dirección de ese módulo.</span><span class="sxs-lookup"><span data-stu-id="f91fc-112">Returns the module base address and size from an address in that module.</span></span>|  
|[<span data-ttu-id="f91fc-113">Método GetImageLocation</span><span class="sxs-lookup"><span data-stu-id="f91fc-113">GetImageLocation Method</span></span>](icordebugdatatarget2-getimagelocation-method.md)|<span data-ttu-id="f91fc-114">Devuelve la ruta de acceso de un módulo a partir de la dirección base del módulo.</span><span class="sxs-lookup"><span data-stu-id="f91fc-114">Returns the path of a module from the module's base address.</span></span>|  
|[<span data-ttu-id="f91fc-115">Método GetSymbolProviderForImage</span><span class="sxs-lookup"><span data-stu-id="f91fc-115">GetSymbolProviderForImage Method</span></span>](icordebugdatatarget2-getsymbolproviderforimage-method.md)|<span data-ttu-id="f91fc-116">Devuelve el proveedor de símbolos de un módulo a partir de la dirección base de ese módulo.</span><span class="sxs-lookup"><span data-stu-id="f91fc-116">Returns the symbol-provider for a module from the base address of that module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f91fc-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f91fc-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f91fc-118">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f91fc-118">This interface is available with .NET Native only.</span></span> <span data-ttu-id="f91fc-119">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="f91fc-119">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f91fc-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f91fc-120">Requirements</span></span>  
 <span data-ttu-id="f91fc-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f91fc-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f91fc-122">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f91fc-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f91fc-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f91fc-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f91fc-124">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f91fc-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f91fc-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f91fc-125">See also</span></span>

- [<span data-ttu-id="f91fc-126">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="f91fc-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="f91fc-127">Depuración</span><span class="sxs-lookup"><span data-stu-id="f91fc-127">Debugging</span></span>](index.md)
