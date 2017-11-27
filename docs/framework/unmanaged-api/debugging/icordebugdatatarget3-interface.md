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
ms.openlocfilehash: a1ab94e792265916e29ed24239e25cb5d57d1313
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdatatarget3-interface"></a><span data-ttu-id="41af4-102">Interfaz de ICorDebugDataTarget3</span><span class="sxs-lookup"><span data-stu-id="41af4-102">ICorDebugDataTarget3 Interface</span></span>
<span data-ttu-id="41af4-103">Extiende lógicamente la [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interfaz para proporcionar información sobre los módulos cargados.</span><span class="sxs-lookup"><span data-stu-id="41af4-103">Logically extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span>  
  
## <a name="method"></a><span data-ttu-id="41af4-104">Método</span><span class="sxs-lookup"><span data-stu-id="41af4-104">Method</span></span>  
  
|<span data-ttu-id="41af4-105">Método</span><span class="sxs-lookup"><span data-stu-id="41af4-105">Method</span></span>|<span data-ttu-id="41af4-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="41af4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="41af4-107">Método de GetLoadedModules</span><span class="sxs-lookup"><span data-stu-id="41af4-107">GetLoadedModules Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-getloadedmodules-method.md)|<span data-ttu-id="41af4-108">Obtiene una lista de los módulos que se han cargado hasta ahora.</span><span class="sxs-lookup"><span data-stu-id="41af4-108">Gets a list of the modules that have been loaded so far.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="41af4-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="41af4-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="41af4-110">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="41af4-110">This interface is available with .NET Native only.</span></span> <span data-ttu-id="41af4-111">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="41af4-111">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41af4-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="41af4-112">Requirements</span></span>  
 <span data-ttu-id="41af4-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41af4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41af4-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="41af4-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="41af4-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41af4-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41af4-116">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41af4-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41af4-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="41af4-117">See Also</span></span>  
 [<span data-ttu-id="41af4-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="41af4-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="41af4-119">Depuración</span><span class="sxs-lookup"><span data-stu-id="41af4-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
