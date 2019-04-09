---
title: Getstartaddress (método)
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 58649a0fc12ce63a1307af5d831dbf5e0d5a776a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136986"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="75891-102">Getstartaddress (método)</span><span class="sxs-lookup"><span data-stu-id="75891-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="75891-103">Obtiene la dirección de inicio del búfer de memoria.</span><span class="sxs-lookup"><span data-stu-id="75891-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75891-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="75891-104">Syntax</span></span>  
  
```  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="75891-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="75891-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="75891-106">[out] Puntero a la dirección de inicio del búfer de memoria.</span><span class="sxs-lookup"><span data-stu-id="75891-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75891-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="75891-107">Remarks</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="75891-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="75891-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75891-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="75891-109">Requirements</span></span>  
 <span data-ttu-id="75891-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75891-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75891-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="75891-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="75891-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75891-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="75891-113">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="75891-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="75891-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="75891-114">See also</span></span>

- [<span data-ttu-id="75891-115">Método ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="75891-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="75891-116">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="75891-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
