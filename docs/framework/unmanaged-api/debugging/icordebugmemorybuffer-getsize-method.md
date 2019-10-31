---
title: 'ICorDebugMemoryBuffer:: (método)'
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
ms.openlocfilehash: 1693860abe99884ee443be0666dfb6b485a219a0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128004"
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="a9ad9-102">ICorDebugMemoryBuffer:: (método)</span><span class="sxs-lookup"><span data-stu-id="a9ad9-102">ICorDebugMemoryBuffer::GetSize Method</span></span>
<span data-ttu-id="a9ad9-103">Obtiene el tamaño del búfer de memoria en bytes.</span><span class="sxs-lookup"><span data-stu-id="a9ad9-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9ad9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9ad9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9ad9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a9ad9-105">Parameters</span></span>  
 `pcbBufferLength`  
 <span data-ttu-id="a9ad9-106">[out] Puntero al tamaño del búfer de memoria.</span><span class="sxs-lookup"><span data-stu-id="a9ad9-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a9ad9-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a9ad9-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a9ad9-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a9ad9-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9ad9-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9ad9-109">Requirements</span></span>  
 <span data-ttu-id="a9ad9-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9ad9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9ad9-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a9ad9-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a9ad9-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9ad9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9ad9-113">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9ad9-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9ad9-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9ad9-114">See also</span></span>

- [<span data-ttu-id="a9ad9-115">ICorDebugMemoryBuffer (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a9ad9-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="a9ad9-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="a9ad9-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
