---
title: ICorDebugMemoryBuffer::GetSize (método)
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c5984addb41c33468068f7ad24a15533f75dc367
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54714729"
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="2cbcb-102">ICorDebugMemoryBuffer::GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="2cbcb-102">ICorDebugMemoryBuffer::GetSize Method</span></span>
<span data-ttu-id="2cbcb-103">Obtiene el tamaño del búfer de memoria en bytes.</span><span class="sxs-lookup"><span data-stu-id="2cbcb-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cbcb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2cbcb-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2cbcb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2cbcb-105">Parameters</span></span>  
 `pcbBufferLength`  
 <span data-ttu-id="2cbcb-106">[out] Puntero al tamaño del búfer de memoria.</span><span class="sxs-lookup"><span data-stu-id="2cbcb-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2cbcb-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2cbcb-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2cbcb-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="2cbcb-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2cbcb-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2cbcb-109">Requirements</span></span>  
 <span data-ttu-id="2cbcb-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2cbcb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2cbcb-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2cbcb-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2cbcb-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2cbcb-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2cbcb-113">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2cbcb-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cbcb-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="2cbcb-114">See also</span></span>
- [<span data-ttu-id="2cbcb-115">ICorDebugMemoryBuffer (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2cbcb-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="2cbcb-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="2cbcb-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
