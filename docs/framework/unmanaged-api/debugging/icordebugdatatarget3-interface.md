---
description: 'Más información acerca de: interfaz ICorDebugDataTarget3'
title: Interfaz de ICorDebugDataTarget3
ms.date: 03/30/2017
ms.assetid: f477af85-994f-4df0-ae78-404ed252bf49
ms.openlocfilehash: fa786b920d1a2e72dc2a7918e0514773862a0e85
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710444"
---
# <a name="icordebugdatatarget3-interface"></a><span data-ttu-id="f4308-103">Interfaz de ICorDebugDataTarget3</span><span class="sxs-lookup"><span data-stu-id="f4308-103">ICorDebugDataTarget3 Interface</span></span>

<span data-ttu-id="f4308-104">Extiende lógicamente la interfaz [ICorDebugDataTarget](icordebugdatatarget-interface.md) para proporcionar información sobre los módulos cargados.</span><span class="sxs-lookup"><span data-stu-id="f4308-104">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span>  
  
## <a name="method"></a><span data-ttu-id="f4308-105">Método</span><span class="sxs-lookup"><span data-stu-id="f4308-105">Method</span></span>  
  
|<span data-ttu-id="f4308-106">Método</span><span class="sxs-lookup"><span data-stu-id="f4308-106">Method</span></span>|<span data-ttu-id="f4308-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f4308-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f4308-108">Método GetLoadedModules</span><span class="sxs-lookup"><span data-stu-id="f4308-108">GetLoadedModules Method</span></span>](icordebugdatatarget3-getloadedmodules-method.md)|<span data-ttu-id="f4308-109">Obtiene una lista de los módulos que se han cargado hasta ahora.</span><span class="sxs-lookup"><span data-stu-id="f4308-109">Gets a list of the modules that have been loaded so far.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f4308-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f4308-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f4308-111">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f4308-111">This interface is available with .NET Native only.</span></span> <span data-ttu-id="f4308-112">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="f4308-112">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4308-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f4308-113">Requirements</span></span>  

 <span data-ttu-id="f4308-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4308-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4308-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f4308-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f4308-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4308-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4308-117">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4308-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4308-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4308-118">See also</span></span>

- [<span data-ttu-id="f4308-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="f4308-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="f4308-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="f4308-120">Debugging</span></span>](index.md)
