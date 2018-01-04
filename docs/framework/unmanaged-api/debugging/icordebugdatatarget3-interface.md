---
title: Interfaz de ICorDebugDataTarget3
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: f477af85-994f-4df0-ae78-404ed252bf49
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c65bbfa033a3a585cdcfdb42cdda95f1de4aa412
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugdatatarget3-interface"></a><span data-ttu-id="91e79-102">Interfaz de ICorDebugDataTarget3</span><span class="sxs-lookup"><span data-stu-id="91e79-102">ICorDebugDataTarget3 Interface</span></span>
<span data-ttu-id="91e79-103">Extiende lógicamente la [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interfaz para proporcionar información sobre los módulos cargados.</span><span class="sxs-lookup"><span data-stu-id="91e79-103">Logically extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span>  
  
## <a name="method"></a><span data-ttu-id="91e79-104">Método</span><span class="sxs-lookup"><span data-stu-id="91e79-104">Method</span></span>  
  
|<span data-ttu-id="91e79-105">Método</span><span class="sxs-lookup"><span data-stu-id="91e79-105">Method</span></span>|<span data-ttu-id="91e79-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="91e79-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="91e79-107">GetLoadedModules (método)</span><span class="sxs-lookup"><span data-stu-id="91e79-107">GetLoadedModules Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-getloadedmodules-method.md)|<span data-ttu-id="91e79-108">Obtiene una lista de los módulos que se han cargado hasta ahora.</span><span class="sxs-lookup"><span data-stu-id="91e79-108">Gets a list of the modules that have been loaded so far.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91e79-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="91e79-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="91e79-110">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="91e79-110">This interface is available with .NET Native only.</span></span> <span data-ttu-id="91e79-111">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="91e79-111">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91e79-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="91e79-112">Requirements</span></span>  
 <span data-ttu-id="91e79-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91e79-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91e79-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="91e79-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="91e79-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="91e79-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="91e79-116">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91e79-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91e79-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="91e79-117">See Also</span></span>  
 [<span data-ttu-id="91e79-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="91e79-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="91e79-119">Depuración</span><span class="sxs-lookup"><span data-stu-id="91e79-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
