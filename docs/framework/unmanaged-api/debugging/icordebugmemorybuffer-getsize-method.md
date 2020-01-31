---
title: ICorDebugMemoryBuffer::GetSize (método)
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
ms.openlocfilehash: 51c13b67951c714d1aec602ffea22891328565a0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793184"
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="d896e-102">ICorDebugMemoryBuffer::GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="d896e-102">ICorDebugMemoryBuffer::GetSize Method</span></span>
<span data-ttu-id="d896e-103">Obtiene el tamaño del búfer de memoria en bytes.</span><span class="sxs-lookup"><span data-stu-id="d896e-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d896e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d896e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d896e-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="d896e-105">Parameters</span></span>  
 `pcbBufferLength`  
 <span data-ttu-id="d896e-106">[out] Puntero al tamaño del búfer de memoria.</span><span class="sxs-lookup"><span data-stu-id="d896e-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d896e-107">Notas</span><span class="sxs-lookup"><span data-stu-id="d896e-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d896e-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="d896e-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d896e-109">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="d896e-109">Requirements</span></span>  
 <span data-ttu-id="d896e-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d896e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d896e-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d896e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d896e-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d896e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d896e-113">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d896e-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d896e-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="d896e-114">See also</span></span>

- [<span data-ttu-id="d896e-115">ICorDebugMemoryBuffer (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d896e-115">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="d896e-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="d896e-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
