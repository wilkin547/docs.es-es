---
title: ICorDebugMemoryBuffer::GetStartAddress (método)
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
ms.openlocfilehash: f2b09c847a6bf577b78c8155f85f07b93877fbe9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793166"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="5e503-102">ICorDebugMemoryBuffer::GetStartAddress (método)</span><span class="sxs-lookup"><span data-stu-id="5e503-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="5e503-103">Obtiene la dirección de inicio del búfer de memoria.</span><span class="sxs-lookup"><span data-stu-id="5e503-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e503-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5e503-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e503-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="5e503-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="5e503-106">[out] Puntero a la dirección de inicio del búfer de memoria.</span><span class="sxs-lookup"><span data-stu-id="5e503-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e503-107">Notas</span><span class="sxs-lookup"><span data-stu-id="5e503-107">Remarks</span></span>  
  
> [!WARNING]
> <span data-ttu-id="5e503-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="5e503-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e503-109">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="5e503-109">Requirements</span></span>  
 <span data-ttu-id="5e503-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e503-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e503-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5e503-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5e503-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e503-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e503-113">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e503-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e503-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e503-114">See also</span></span>

- [<span data-ttu-id="5e503-115">ICorDebugMemoryBuffer (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5e503-115">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="5e503-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="5e503-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
