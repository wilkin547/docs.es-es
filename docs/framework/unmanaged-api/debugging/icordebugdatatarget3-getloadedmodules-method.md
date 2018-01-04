---
title: "Método de ICorDebugDataTarget3::GetLoadedModules"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 9a48c05b-1949-416e-933c-52549b6fcf5e
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3db6449abee4eed4a8e5d6c691834c52dc0717e2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugdatatarget3getloadedmodules-method"></a><span data-ttu-id="1ba4e-102">Método de ICorDebugDataTarget3::GetLoadedModules</span><span class="sxs-lookup"><span data-stu-id="1ba4e-102">ICorDebugDataTarget3::GetLoadedModules Method</span></span>
<span data-ttu-id="1ba4e-103">Obtiene una lista de los módulos que se han cargado hasta ahora.</span><span class="sxs-lookup"><span data-stu-id="1ba4e-103">Gets a list of the modules that have been loaded so far.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ba4e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1ba4e-104">Syntax</span></span>  
  
```  
HRESULT GetLoadedModules(  
   [in] ULONG32 cRequestedModules,  
   [out] ULONG32 *pcFetchedModules,  
   [out, size_is(cRequestedModules), length_is(*pcFetchedModules)] ICorDebugLoadedModule *pLoadedModules[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1ba4e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1ba4e-105">Parameters</span></span>  
 `cRequestedModules`  
 <span data-ttu-id="1ba4e-106">[in] Número de módulos para los que se solicita información.</span><span class="sxs-lookup"><span data-stu-id="1ba4e-106">[in] The number of modules for which information is requested.</span></span>  
  
 `pcFetchedModules`  
 <span data-ttu-id="1ba4e-107">[out] Puntero al número de módulos sobre qué información se devolvió.</span><span class="sxs-lookup"><span data-stu-id="1ba4e-107">[out] A pointer to the number of modules about which information was returned.</span></span>  
  
 `pLoadedModules`  
 <span data-ttu-id="1ba4e-108">[out] Un puntero a una matriz de [ICorDebugLoadedModule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md) objetos que proporcionan información acerca de los módulos cargan.</span><span class="sxs-lookup"><span data-stu-id="1ba4e-108">[out] A pointer to an array of [ICorDebugLoadedModule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md) objects that provide information about loaded modules.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ba4e-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1ba4e-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1ba4e-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="1ba4e-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ba4e-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1ba4e-111">Requirements</span></span>  
 <span data-ttu-id="1ba4e-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ba4e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ba4e-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1ba4e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1ba4e-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1ba4e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1ba4e-115">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ba4e-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ba4e-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ba4e-116">See Also</span></span>  
 [<span data-ttu-id="1ba4e-117">ICorDebugDataTarget3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1ba4e-117">ICorDebugDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-interface.md)  
 [<span data-ttu-id="1ba4e-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="1ba4e-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
