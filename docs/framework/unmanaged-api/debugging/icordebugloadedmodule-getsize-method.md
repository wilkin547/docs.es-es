---
title: Método de ICorDebugLoadedModule::GetSize
ms.date: 03/30/2017
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
ms.openlocfilehash: 3f2f8a1721847b8f7b845c42aa3c91e032c2d474
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122642"
---
# <a name="icordebugloadedmodulegetsize-method"></a><span data-ttu-id="53527-102">Método de ICorDebugLoadedModule::GetSize</span><span class="sxs-lookup"><span data-stu-id="53527-102">ICorDebugLoadedModule::GetSize Method</span></span>
<span data-ttu-id="53527-103">Obtiene el tamaño, en bytes, del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="53527-103">Gets the size in bytes of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53527-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="53527-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="53527-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="53527-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="53527-106">[out] Puntero al número de bytes del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="53527-106">[out] A pointer to the number of bytes in the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="53527-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="53527-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="53527-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="53527-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53527-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="53527-109">Requirements</span></span>  
 <span data-ttu-id="53527-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53527-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53527-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="53527-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="53527-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="53527-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="53527-113">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53527-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53527-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="53527-114">See also</span></span>

- [<span data-ttu-id="53527-115">ICorDebugLoadedModule (interfaz)</span><span class="sxs-lookup"><span data-stu-id="53527-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="53527-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="53527-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
