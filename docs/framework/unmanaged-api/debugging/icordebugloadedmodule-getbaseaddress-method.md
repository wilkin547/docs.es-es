---
title: Método de ICorDebugLoadedModule::GetBaseAddress
ms.date: 03/30/2017
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
ms.openlocfilehash: 8af814ff2eaaf3ae6dae9031c13bf37ea0c1236b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122657"
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a><span data-ttu-id="cdd47-102">Método de ICorDebugLoadedModule::GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="cdd47-102">ICorDebugLoadedModule::GetBaseAddress Method</span></span>
<span data-ttu-id="cdd47-103">Obtiene la dirección base del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="cdd47-103">Gets the base address of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdd47-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cdd47-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cdd47-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cdd47-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="cdd47-106">[out] Puntero a la dirección base del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="cdd47-106">[out] A pointer to the base address of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cdd47-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cdd47-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cdd47-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="cdd47-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdd47-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cdd47-109">Requirements</span></span>  
 <span data-ttu-id="cdd47-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cdd47-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cdd47-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cdd47-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cdd47-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cdd47-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cdd47-113">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cdd47-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdd47-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="cdd47-114">See also</span></span>

- [<span data-ttu-id="cdd47-115">ICorDebugLoadedModule (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cdd47-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="cdd47-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="cdd47-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
