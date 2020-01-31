---
title: Método de ICorDebugLoadedModule::GetBaseAddress
ms.date: 03/30/2017
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
ms.openlocfilehash: 190c9114cffa537ba162b19abdf30d5a6aee87f8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788445"
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a><span data-ttu-id="1fb3a-102">Método de ICorDebugLoadedModule::GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="1fb3a-102">ICorDebugLoadedModule::GetBaseAddress Method</span></span>
<span data-ttu-id="1fb3a-103">Obtiene la dirección base del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="1fb3a-103">Gets the base address of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fb3a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1fb3a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1fb3a-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="1fb3a-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="1fb3a-106">[out] Puntero a la dirección base del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="1fb3a-106">[out] A pointer to the base address of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1fb3a-107">Notas</span><span class="sxs-lookup"><span data-stu-id="1fb3a-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1fb3a-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="1fb3a-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fb3a-109">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="1fb3a-109">Requirements</span></span>  
 <span data-ttu-id="1fb3a-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1fb3a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1fb3a-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1fb3a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1fb3a-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1fb3a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1fb3a-113">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fb3a-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fb3a-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="1fb3a-114">See also</span></span>

- [<span data-ttu-id="1fb3a-115">ICorDebugLoadedModule (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1fb3a-115">ICorDebugLoadedModule Interface</span></span>](icordebugloadedmodule-interface.md)
- [<span data-ttu-id="1fb3a-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="1fb3a-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
