---
title: ICorDebugMemoryBuffer::GetStartAddress (método)
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1aa816ea9e6185791e09bcdb0e47c50761a5ebc6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422938"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="bfeda-102">ICorDebugMemoryBuffer::GetStartAddress (método)</span><span class="sxs-lookup"><span data-stu-id="bfeda-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="bfeda-103">Obtiene la dirección de inicio del búfer de memoria.</span><span class="sxs-lookup"><span data-stu-id="bfeda-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfeda-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bfeda-104">Syntax</span></span>  
  
```  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bfeda-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bfeda-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="bfeda-106">[out] Puntero a la dirección de inicio del búfer de memoria.</span><span class="sxs-lookup"><span data-stu-id="bfeda-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bfeda-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bfeda-107">Remarks</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="bfeda-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="bfeda-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfeda-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bfeda-109">Requirements</span></span>  
 <span data-ttu-id="bfeda-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bfeda-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfeda-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bfeda-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bfeda-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bfeda-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bfeda-113">**Versiones de .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfeda-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfeda-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="bfeda-114">See Also</span></span>  
 [<span data-ttu-id="bfeda-115">ICorDebugMemoryBuffer (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bfeda-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 [<span data-ttu-id="bfeda-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="bfeda-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
