---
title: Método de ICorDebugDataTarget3::GetLoadedModules
ms.date: 03/30/2017
ms.assetid: 9a48c05b-1949-416e-933c-52549b6fcf5e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c51ce8ff76e0fc1588cdd136de83b77dcab0f10
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413500"
---
# <a name="icordebugdatatarget3getloadedmodules-method"></a><span data-ttu-id="3c65f-102">Método de ICorDebugDataTarget3::GetLoadedModules</span><span class="sxs-lookup"><span data-stu-id="3c65f-102">ICorDebugDataTarget3::GetLoadedModules Method</span></span>
<span data-ttu-id="3c65f-103">Obtiene una lista de los módulos que se han cargado hasta ahora.</span><span class="sxs-lookup"><span data-stu-id="3c65f-103">Gets a list of the modules that have been loaded so far.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c65f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3c65f-104">Syntax</span></span>  
  
```  
HRESULT GetLoadedModules(  
   [in] ULONG32 cRequestedModules,  
   [out] ULONG32 *pcFetchedModules,  
   [out, size_is(cRequestedModules), length_is(*pcFetchedModules)] ICorDebugLoadedModule *pLoadedModules[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3c65f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3c65f-105">Parameters</span></span>  
 `cRequestedModules`  
 <span data-ttu-id="3c65f-106">[in] Número de módulos para los que se solicita información.</span><span class="sxs-lookup"><span data-stu-id="3c65f-106">[in] The number of modules for which information is requested.</span></span>  
  
 `pcFetchedModules`  
 <span data-ttu-id="3c65f-107">[out] Puntero al número de módulos sobre qué información se devolvió.</span><span class="sxs-lookup"><span data-stu-id="3c65f-107">[out] A pointer to the number of modules about which information was returned.</span></span>  
  
 `pLoadedModules`  
 <span data-ttu-id="3c65f-108">[out] Un puntero a una matriz de [ICorDebugLoadedModule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md) objetos que proporcionan información acerca de los módulos cargan.</span><span class="sxs-lookup"><span data-stu-id="3c65f-108">[out] A pointer to an array of [ICorDebugLoadedModule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md) objects that provide information about loaded modules.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c65f-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3c65f-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c65f-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="3c65f-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c65f-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3c65f-111">Requirements</span></span>  
 <span data-ttu-id="3c65f-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c65f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c65f-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3c65f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3c65f-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c65f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c65f-115">**Versiones de .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c65f-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c65f-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="3c65f-116">See Also</span></span>  
 [<span data-ttu-id="3c65f-117">ICorDebugDataTarget3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3c65f-117">ICorDebugDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-interface.md)  
 [<span data-ttu-id="3c65f-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="3c65f-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
