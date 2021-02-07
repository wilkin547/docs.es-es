---
description: 'Más información sobre: ICorDebugDataTarget3:: GetLoadedModules (método)'
title: Método de ICorDebugDataTarget3::GetLoadedModules
ms.date: 03/30/2017
ms.assetid: 9a48c05b-1949-416e-933c-52549b6fcf5e
ms.openlocfilehash: ea6350155fd79b52a37133cad95f624635433a3e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764351"
---
# <a name="icordebugdatatarget3getloadedmodules-method"></a><span data-ttu-id="f03e3-103">Método de ICorDebugDataTarget3::GetLoadedModules</span><span class="sxs-lookup"><span data-stu-id="f03e3-103">ICorDebugDataTarget3::GetLoadedModules Method</span></span>

<span data-ttu-id="f03e3-104">Obtiene una lista de los módulos que se han cargado hasta ahora.</span><span class="sxs-lookup"><span data-stu-id="f03e3-104">Gets a list of the modules that have been loaded so far.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f03e3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f03e3-105">Syntax</span></span>  
  
```cpp  
HRESULT GetLoadedModules(  
   [in] ULONG32 cRequestedModules,  
   [out] ULONG32 *pcFetchedModules,  
   [out, size_is(cRequestedModules), length_is(*pcFetchedModules)] ICorDebugLoadedModule *pLoadedModules[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f03e3-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f03e3-106">Parameters</span></span>  

 `cRequestedModules`  
 <span data-ttu-id="f03e3-107">[in] Número de módulos para los que se solicita información.</span><span class="sxs-lookup"><span data-stu-id="f03e3-107">[in] The number of modules for which information is requested.</span></span>  
  
 `pcFetchedModules`  
 <span data-ttu-id="f03e3-108">[out] Puntero al número de módulos sobre qué información se devolvió.</span><span class="sxs-lookup"><span data-stu-id="f03e3-108">[out] A pointer to the number of modules about which information was returned.</span></span>  
  
 `pLoadedModules`  
 <span data-ttu-id="f03e3-109">enuncia Puntero a una matriz de objetos [ICorDebugLoadedModule](icordebugloadedmodule-interface.md) que proporcionan información sobre los módulos cargados.</span><span class="sxs-lookup"><span data-stu-id="f03e3-109">[out] A pointer to an array of [ICorDebugLoadedModule](icordebugloadedmodule-interface.md) objects that provide information about loaded modules.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f03e3-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f03e3-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f03e3-111">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f03e3-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f03e3-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f03e3-112">Requirements</span></span>  

 <span data-ttu-id="f03e3-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f03e3-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f03e3-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f03e3-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f03e3-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f03e3-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f03e3-116">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f03e3-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f03e3-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="f03e3-117">See also</span></span>

- [<span data-ttu-id="f03e3-118">Interfaz de ICorDebugDataTarget3</span><span class="sxs-lookup"><span data-stu-id="f03e3-118">ICorDebugDataTarget3 Interface</span></span>](icordebugdatatarget3-interface.md)
- [<span data-ttu-id="f03e3-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="f03e3-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
