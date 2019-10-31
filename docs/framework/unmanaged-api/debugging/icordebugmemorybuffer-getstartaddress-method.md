---
title: 'ICorDebugMemoryBuffer:: Getstartaddress ((método)'
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
ms.openlocfilehash: e2876398ceaf863bbb3c7e576d59b89c52f1bdaf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127985"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="f07a8-102">ICorDebugMemoryBuffer:: Getstartaddress ((método)</span><span class="sxs-lookup"><span data-stu-id="f07a8-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="f07a8-103">Obtiene la dirección de inicio del búfer de memoria.</span><span class="sxs-lookup"><span data-stu-id="f07a8-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f07a8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f07a8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f07a8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f07a8-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="f07a8-106">[out] Puntero a la dirección de inicio del búfer de memoria.</span><span class="sxs-lookup"><span data-stu-id="f07a8-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f07a8-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f07a8-107">Remarks</span></span>  
  
> [!WARNING]
> <span data-ttu-id="f07a8-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f07a8-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f07a8-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f07a8-109">Requirements</span></span>  
 <span data-ttu-id="f07a8-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f07a8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f07a8-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f07a8-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f07a8-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f07a8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f07a8-113">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f07a8-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f07a8-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f07a8-114">See also</span></span>

- [<span data-ttu-id="f07a8-115">ICorDebugMemoryBuffer (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f07a8-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="f07a8-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="f07a8-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
