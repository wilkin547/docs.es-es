---
title: Método de ICorDebugLoadedModule::GetSize
ms.date: 03/30/2017
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
ms.openlocfilehash: f207cd1c612b6444a9512adaa356ac2d01de7b9f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788462"
---
# <a name="icordebugloadedmodulegetsize-method"></a><span data-ttu-id="2c354-102">Método de ICorDebugLoadedModule::GetSize</span><span class="sxs-lookup"><span data-stu-id="2c354-102">ICorDebugLoadedModule::GetSize Method</span></span>
<span data-ttu-id="2c354-103">Obtiene el tamaño, en bytes, del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="2c354-103">Gets the size in bytes of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c354-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2c354-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c354-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="2c354-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="2c354-106">[out] Puntero al número de bytes del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="2c354-106">[out] A pointer to the number of bytes in the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c354-107">Notas</span><span class="sxs-lookup"><span data-stu-id="2c354-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2c354-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="2c354-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c354-109">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="2c354-109">Requirements</span></span>  
 <span data-ttu-id="2c354-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c354-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c354-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2c354-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2c354-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c354-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c354-113">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c354-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c354-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c354-114">See also</span></span>

- [<span data-ttu-id="2c354-115">ICorDebugLoadedModule (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2c354-115">ICorDebugLoadedModule Interface</span></span>](icordebugloadedmodule-interface.md)
- [<span data-ttu-id="2c354-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="2c354-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
