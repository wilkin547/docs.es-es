---
title: Interfaz ICorDebugDataTarget2
ms.date: 03/30/2017
ms.assetid: 13f11388-2f91-48d8-98d6-6a4a63cb5746
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a74ba2b5c1dc2340d20a793bcf3b14e2af234b4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59149622"
---
# <a name="icordebugdatatarget2-interface"></a><span data-ttu-id="e3af4-102">Interfaz ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="e3af4-102">ICorDebugDataTarget2 Interface</span></span>
<span data-ttu-id="e3af4-103">Extiende lógicamente la [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)interfaz.</span><span class="sxs-lookup"><span data-stu-id="e3af4-103">Logically extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e3af4-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="e3af4-104">Methods</span></span>  
  
|<span data-ttu-id="e3af4-105">Método</span><span class="sxs-lookup"><span data-stu-id="e3af4-105">Method</span></span>|<span data-ttu-id="e3af4-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e3af4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e3af4-107">CreateVirtualUnwinder (método)</span><span class="sxs-lookup"><span data-stu-id="e3af4-107">CreateVirtualUnwinder Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-createvirtualunwinder-method.md)|<span data-ttu-id="e3af4-108">Crea un nuevo desenredador de pila que inicia el desenredo desde un contexto inicial (que no tiene por qué ser la hoja de un subproceso).</span><span class="sxs-lookup"><span data-stu-id="e3af4-108">Creates a new stack unwinder that starts unwinding from an initial context (which isn't necessarily the leaf of a thread).</span></span>|  
|[<span data-ttu-id="e3af4-109">EnumerateThreadIDs (método)</span><span class="sxs-lookup"><span data-stu-id="e3af4-109">EnumerateThreadIDs Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-enumeratethreadids-method.md)|<span data-ttu-id="e3af4-110">Devuelve una lista de identificadores de subprocesos activos.</span><span class="sxs-lookup"><span data-stu-id="e3af4-110">Returns a list of active thread IDs.</span></span>|  
|[<span data-ttu-id="e3af4-111">GetImageFromPointer (método)</span><span class="sxs-lookup"><span data-stu-id="e3af4-111">GetImageFromPointer Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-getimagefrompointer-method.md)|<span data-ttu-id="e3af4-112">Devuelve el tamaño y dirección base del módulo a partir de una dirección de ese módulo.</span><span class="sxs-lookup"><span data-stu-id="e3af4-112">Returns the module base address and size from an address in that module.</span></span>|  
|[<span data-ttu-id="e3af4-113">GetImageLocation (método)</span><span class="sxs-lookup"><span data-stu-id="e3af4-113">GetImageLocation Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-getimagelocation-method.md)|<span data-ttu-id="e3af4-114">Devuelve la ruta de acceso de un módulo a partir de la dirección base del módulo.</span><span class="sxs-lookup"><span data-stu-id="e3af4-114">Returns the path of a module from the module's base address.</span></span>|  
|[<span data-ttu-id="e3af4-115">GetSymbolProviderForImage (método)</span><span class="sxs-lookup"><span data-stu-id="e3af4-115">GetSymbolProviderForImage Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-getsymbolproviderforimage-method.md)|<span data-ttu-id="e3af4-116">Devuelve el proveedor de símbolos de un módulo a partir de la dirección base de ese módulo.</span><span class="sxs-lookup"><span data-stu-id="e3af4-116">Returns the symbol-provider for a module from the base address of that module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e3af4-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e3af4-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e3af4-118">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e3af4-118">This interface is available with .NET Native only.</span></span> <span data-ttu-id="e3af4-119">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="e3af4-119">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3af4-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e3af4-120">Requirements</span></span>  
 <span data-ttu-id="e3af4-121">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3af4-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3af4-122">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e3af4-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e3af4-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3af4-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3af4-124">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3af4-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3af4-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="e3af4-125">See also</span></span>

- [<span data-ttu-id="e3af4-126">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="e3af4-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="e3af4-127">Depuración</span><span class="sxs-lookup"><span data-stu-id="e3af4-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
