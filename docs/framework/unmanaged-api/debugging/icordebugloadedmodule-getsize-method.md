---
title: Método de ICorDebugLoadedModule::GetSize
ms.date: 03/30/2017
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 61bb5a019a8ba5450fa2859a851f4ac9425d45b5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759906"
---
# <a name="icordebugloadedmodulegetsize-method"></a><span data-ttu-id="49b18-102">Método de ICorDebugLoadedModule::GetSize</span><span class="sxs-lookup"><span data-stu-id="49b18-102">ICorDebugLoadedModule::GetSize Method</span></span>
<span data-ttu-id="49b18-103">Obtiene el tamaño, en bytes, del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="49b18-103">Gets the size in bytes of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49b18-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="49b18-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49b18-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="49b18-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="49b18-106">[out] Puntero al número de bytes del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="49b18-106">[out] A pointer to the number of bytes in the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49b18-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="49b18-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="49b18-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="49b18-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49b18-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="49b18-109">Requirements</span></span>  
 <span data-ttu-id="49b18-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49b18-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49b18-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="49b18-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="49b18-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49b18-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49b18-113">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49b18-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49b18-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="49b18-114">See also</span></span>

- [<span data-ttu-id="49b18-115">ICorDebugLoadedModule (interfaz)</span><span class="sxs-lookup"><span data-stu-id="49b18-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="49b18-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="49b18-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
