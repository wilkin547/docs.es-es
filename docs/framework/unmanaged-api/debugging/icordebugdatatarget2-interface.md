---
title: ICorDebugDataTarget2 (Interfaz)
ms.date: 03/30/2017
ms.assetid: 13f11388-2f91-48d8-98d6-6a4a63cb5746
ms.openlocfilehash: 472ea0b3d54c025cdd69957765ad2663c7288b15
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783573"
---
# <a name="icordebugdatatarget2-interface"></a><span data-ttu-id="a5225-102">ICorDebugDataTarget2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a5225-102">ICorDebugDataTarget2 Interface</span></span>
<span data-ttu-id="a5225-103">Extiende lógicamente la interfaz [ICorDebugDataTarget](icordebugdatatarget-interface.md).</span><span class="sxs-lookup"><span data-stu-id="a5225-103">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md)interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a5225-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="a5225-104">Methods</span></span>  
  
|<span data-ttu-id="a5225-105">Método</span><span class="sxs-lookup"><span data-stu-id="a5225-105">Method</span></span>|<span data-ttu-id="a5225-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="a5225-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a5225-107">CreateVirtualUnwinder (método)</span><span class="sxs-lookup"><span data-stu-id="a5225-107">CreateVirtualUnwinder Method</span></span>](icordebugdatatarget2-createvirtualunwinder-method.md)|<span data-ttu-id="a5225-108">Crea un nuevo desenredador de pila que inicia el desenredo desde un contexto inicial (que no tiene por qué ser la hoja de un subproceso).</span><span class="sxs-lookup"><span data-stu-id="a5225-108">Creates a new stack unwinder that starts unwinding from an initial context (which isn't necessarily the leaf of a thread).</span></span>|  
|[<span data-ttu-id="a5225-109">EnumerateThreadIDs (método)</span><span class="sxs-lookup"><span data-stu-id="a5225-109">EnumerateThreadIDs Method</span></span>](icordebugdatatarget2-enumeratethreadids-method.md)|<span data-ttu-id="a5225-110">Devuelve una lista de identificadores de subprocesos activos.</span><span class="sxs-lookup"><span data-stu-id="a5225-110">Returns a list of active thread IDs.</span></span>|  
|[<span data-ttu-id="a5225-111">GetImageFromPointer (método)</span><span class="sxs-lookup"><span data-stu-id="a5225-111">GetImageFromPointer Method</span></span>](icordebugdatatarget2-getimagefrompointer-method.md)|<span data-ttu-id="a5225-112">Devuelve el tamaño y dirección base del módulo a partir de una dirección de ese módulo.</span><span class="sxs-lookup"><span data-stu-id="a5225-112">Returns the module base address and size from an address in that module.</span></span>|  
|[<span data-ttu-id="a5225-113">GetImageLocation (método)</span><span class="sxs-lookup"><span data-stu-id="a5225-113">GetImageLocation Method</span></span>](icordebugdatatarget2-getimagelocation-method.md)|<span data-ttu-id="a5225-114">Devuelve la ruta de acceso de un módulo a partir de la dirección base del módulo.</span><span class="sxs-lookup"><span data-stu-id="a5225-114">Returns the path of a module from the module's base address.</span></span>|  
|[<span data-ttu-id="a5225-115">GetSymbolProviderForImage (método)</span><span class="sxs-lookup"><span data-stu-id="a5225-115">GetSymbolProviderForImage Method</span></span>](icordebugdatatarget2-getsymbolproviderforimage-method.md)|<span data-ttu-id="a5225-116">Devuelve el proveedor de símbolos de un módulo a partir de la dirección base de ese módulo.</span><span class="sxs-lookup"><span data-stu-id="a5225-116">Returns the symbol-provider for a module from the base address of that module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5225-117">Notas</span><span class="sxs-lookup"><span data-stu-id="a5225-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a5225-118">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a5225-118">This interface is available with .NET Native only.</span></span> <span data-ttu-id="a5225-119">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="a5225-119">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5225-120">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="a5225-120">Requirements</span></span>  
 <span data-ttu-id="a5225-121">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5225-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5225-122">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a5225-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a5225-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5225-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5225-124">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5225-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5225-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5225-125">See also</span></span>

- [<span data-ttu-id="a5225-126">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="a5225-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="a5225-127">Depuración</span><span class="sxs-lookup"><span data-stu-id="a5225-127">Debugging</span></span>](index.md)
