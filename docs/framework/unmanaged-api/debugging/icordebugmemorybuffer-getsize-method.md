---
title: ICorDebugMemoryBuffer::GetSize (método)
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
ms.openlocfilehash: 1bef2e2d0e1a1cef74c7568fdd2e9b7986500488
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212612"
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="08912-102">ICorDebugMemoryBuffer::GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="08912-102">ICorDebugMemoryBuffer::GetSize Method</span></span>
<span data-ttu-id="08912-103">Obtiene el tamaño del búfer de memoria en bytes.</span><span class="sxs-lookup"><span data-stu-id="08912-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08912-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="08912-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08912-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="08912-105">Parameters</span></span>  
 `pcbBufferLength`  
 <span data-ttu-id="08912-106">[out] Puntero al tamaño del búfer de memoria.</span><span class="sxs-lookup"><span data-stu-id="08912-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08912-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="08912-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="08912-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="08912-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08912-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="08912-109">Requirements</span></span>  
 <span data-ttu-id="08912-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08912-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08912-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="08912-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="08912-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08912-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08912-113">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08912-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08912-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="08912-114">See also</span></span>

- [<span data-ttu-id="08912-115">Método ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="08912-115">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="08912-116">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="08912-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
