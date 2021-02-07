---
description: 'Más información acerca de: interfaz método icordebugdatatarget2'
title: Interfaz ICorDebugDataTarget2
ms.date: 03/30/2017
ms.assetid: 13f11388-2f91-48d8-98d6-6a4a63cb5746
ms.openlocfilehash: 13a83ee99f0158f32f466f9ae29af3d917248f95
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710470"
---
# <a name="icordebugdatatarget2-interface"></a><span data-ttu-id="e9795-103">Interfaz ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="e9795-103">ICorDebugDataTarget2 Interface</span></span>

<span data-ttu-id="e9795-104">Extiende lógicamente la interfaz [ICorDebugDataTarget](icordebugdatatarget-interface.md).</span><span class="sxs-lookup"><span data-stu-id="e9795-104">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md)interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e9795-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="e9795-105">Methods</span></span>  
  
|<span data-ttu-id="e9795-106">Método</span><span class="sxs-lookup"><span data-stu-id="e9795-106">Method</span></span>|<span data-ttu-id="e9795-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e9795-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e9795-108">Método CreateVirtualUnwinder</span><span class="sxs-lookup"><span data-stu-id="e9795-108">CreateVirtualUnwinder Method</span></span>](icordebugdatatarget2-createvirtualunwinder-method.md)|<span data-ttu-id="e9795-109">Crea un nuevo desenredador de pila que inicia el desenredo desde un contexto inicial (que no tiene por qué ser la hoja de un subproceso).</span><span class="sxs-lookup"><span data-stu-id="e9795-109">Creates a new stack unwinder that starts unwinding from an initial context (which isn't necessarily the leaf of a thread).</span></span>|  
|[<span data-ttu-id="e9795-110">Método EnumerateThreadIDs</span><span class="sxs-lookup"><span data-stu-id="e9795-110">EnumerateThreadIDs Method</span></span>](icordebugdatatarget2-enumeratethreadids-method.md)|<span data-ttu-id="e9795-111">Devuelve una lista de identificadores de subprocesos activos.</span><span class="sxs-lookup"><span data-stu-id="e9795-111">Returns a list of active thread IDs.</span></span>|  
|[<span data-ttu-id="e9795-112">Método GetImageFromPointer</span><span class="sxs-lookup"><span data-stu-id="e9795-112">GetImageFromPointer Method</span></span>](icordebugdatatarget2-getimagefrompointer-method.md)|<span data-ttu-id="e9795-113">Devuelve el tamaño y dirección base del módulo a partir de una dirección de ese módulo.</span><span class="sxs-lookup"><span data-stu-id="e9795-113">Returns the module base address and size from an address in that module.</span></span>|  
|[<span data-ttu-id="e9795-114">Método GetImageLocation</span><span class="sxs-lookup"><span data-stu-id="e9795-114">GetImageLocation Method</span></span>](icordebugdatatarget2-getimagelocation-method.md)|<span data-ttu-id="e9795-115">Devuelve la ruta de acceso de un módulo a partir de la dirección base del módulo.</span><span class="sxs-lookup"><span data-stu-id="e9795-115">Returns the path of a module from the module's base address.</span></span>|  
|[<span data-ttu-id="e9795-116">Método GetSymbolProviderForImage</span><span class="sxs-lookup"><span data-stu-id="e9795-116">GetSymbolProviderForImage Method</span></span>](icordebugdatatarget2-getsymbolproviderforimage-method.md)|<span data-ttu-id="e9795-117">Devuelve el proveedor de símbolos de un módulo a partir de la dirección base de ese módulo.</span><span class="sxs-lookup"><span data-stu-id="e9795-117">Returns the symbol-provider for a module from the base address of that module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9795-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e9795-118">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e9795-119">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e9795-119">This interface is available with .NET Native only.</span></span> <span data-ttu-id="e9795-120">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="e9795-120">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9795-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e9795-121">Requirements</span></span>  

 <span data-ttu-id="e9795-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9795-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9795-123">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e9795-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e9795-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9795-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9795-125">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9795-125">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9795-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9795-126">See also</span></span>

- [<span data-ttu-id="e9795-127">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="e9795-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="e9795-128">Depuración</span><span class="sxs-lookup"><span data-stu-id="e9795-128">Debugging</span></span>](index.md)
