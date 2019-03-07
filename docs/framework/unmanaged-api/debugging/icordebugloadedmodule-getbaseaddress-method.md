---
title: Método de ICorDebugLoadedModule::GetBaseAddress
ms.date: 03/30/2017
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 31b398080c1355441a35871d0685283783efcd52
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501233"
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a><span data-ttu-id="c6ed8-102">Método de ICorDebugLoadedModule::GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="c6ed8-102">ICorDebugLoadedModule::GetBaseAddress Method</span></span>
<span data-ttu-id="c6ed8-103">Obtiene la dirección base del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="c6ed8-103">Gets the base address of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6ed8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c6ed8-104">Syntax</span></span>  
  
```  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6ed8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c6ed8-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="c6ed8-106">[out] Puntero a la dirección base del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="c6ed8-106">[out] A pointer to the base address of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6ed8-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c6ed8-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c6ed8-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c6ed8-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6ed8-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c6ed8-109">Requirements</span></span>  
 <span data-ttu-id="c6ed8-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6ed8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6ed8-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c6ed8-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c6ed8-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6ed8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6ed8-113">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6ed8-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6ed8-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="c6ed8-114">See also</span></span>
- [<span data-ttu-id="c6ed8-115">ICorDebugLoadedModule (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c6ed8-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="c6ed8-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="c6ed8-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
