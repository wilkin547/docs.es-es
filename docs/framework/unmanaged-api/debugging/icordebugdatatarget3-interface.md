---
title: ICorDebugDataTarget3 (Interfaz)
ms.date: 03/30/2017
ms.assetid: f477af85-994f-4df0-ae78-404ed252bf49
ms.openlocfilehash: 04e7b9a064d4a06a06b8a1518f06092ba79a3561
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783485"
---
# <a name="icordebugdatatarget3-interface"></a><span data-ttu-id="d292e-102">ICorDebugDataTarget3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d292e-102">ICorDebugDataTarget3 Interface</span></span>
<span data-ttu-id="d292e-103">Extiende lógicamente la interfaz [ICorDebugDataTarget](icordebugdatatarget-interface.md) para proporcionar información sobre los módulos cargados.</span><span class="sxs-lookup"><span data-stu-id="d292e-103">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span>  
  
## <a name="method"></a><span data-ttu-id="d292e-104">Método</span><span class="sxs-lookup"><span data-stu-id="d292e-104">Method</span></span>  
  
|<span data-ttu-id="d292e-105">Método</span><span class="sxs-lookup"><span data-stu-id="d292e-105">Method</span></span>|<span data-ttu-id="d292e-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="d292e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d292e-107">GetLoadedModules (método)</span><span class="sxs-lookup"><span data-stu-id="d292e-107">GetLoadedModules Method</span></span>](icordebugdatatarget3-getloadedmodules-method.md)|<span data-ttu-id="d292e-108">Obtiene una lista de los módulos que se han cargado hasta ahora.</span><span class="sxs-lookup"><span data-stu-id="d292e-108">Gets a list of the modules that have been loaded so far.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d292e-109">Notas</span><span class="sxs-lookup"><span data-stu-id="d292e-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d292e-110">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="d292e-110">This interface is available with .NET Native only.</span></span> <span data-ttu-id="d292e-111">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="d292e-111">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d292e-112">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="d292e-112">Requirements</span></span>  
 <span data-ttu-id="d292e-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d292e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d292e-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d292e-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d292e-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d292e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d292e-116">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d292e-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d292e-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="d292e-117">See also</span></span>

- [<span data-ttu-id="d292e-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="d292e-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="d292e-119">Depuración</span><span class="sxs-lookup"><span data-stu-id="d292e-119">Debugging</span></span>](index.md)
