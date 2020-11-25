---
title: ICorDebugMemoryBuffer::GetSize (método)
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
ms.openlocfilehash: 7f5458dd12ca83c1a5190bbf7fab0f8e5d06a0e1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710769"
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="78743-102">ICorDebugMemoryBuffer::GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="78743-102">ICorDebugMemoryBuffer::GetSize Method</span></span>

<span data-ttu-id="78743-103">Obtiene el tamaño del búfer de memoria en bytes.</span><span class="sxs-lookup"><span data-stu-id="78743-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78743-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="78743-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78743-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="78743-105">Parameters</span></span>  

 `pcbBufferLength`  
 <span data-ttu-id="78743-106">[out] Puntero al tamaño del búfer de memoria.</span><span class="sxs-lookup"><span data-stu-id="78743-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="78743-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="78743-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="78743-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="78743-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78743-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="78743-109">Requirements</span></span>  

 <span data-ttu-id="78743-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78743-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78743-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="78743-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="78743-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="78743-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="78743-113">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78743-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78743-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="78743-114">See also</span></span>

- [<span data-ttu-id="78743-115">Método ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="78743-115">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="78743-116">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="78743-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
