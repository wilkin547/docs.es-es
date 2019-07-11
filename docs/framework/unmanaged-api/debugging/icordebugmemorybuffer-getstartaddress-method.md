---
title: Getstartaddress (método)
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9208d07b697c3bb8a99e13582eda70dcb8dd826b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752772"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="99eb5-102">Getstartaddress (método)</span><span class="sxs-lookup"><span data-stu-id="99eb5-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="99eb5-103">Obtiene la dirección de inicio del búfer de memoria.</span><span class="sxs-lookup"><span data-stu-id="99eb5-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99eb5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="99eb5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99eb5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="99eb5-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="99eb5-106">[out] Puntero a la dirección de inicio del búfer de memoria.</span><span class="sxs-lookup"><span data-stu-id="99eb5-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99eb5-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="99eb5-107">Remarks</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="99eb5-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="99eb5-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99eb5-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="99eb5-109">Requirements</span></span>  
 <span data-ttu-id="99eb5-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99eb5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99eb5-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="99eb5-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="99eb5-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99eb5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99eb5-113">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99eb5-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99eb5-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="99eb5-114">See also</span></span>

- [<span data-ttu-id="99eb5-115">ICorDebugMemoryBuffer (interfaz)</span><span class="sxs-lookup"><span data-stu-id="99eb5-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="99eb5-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="99eb5-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
