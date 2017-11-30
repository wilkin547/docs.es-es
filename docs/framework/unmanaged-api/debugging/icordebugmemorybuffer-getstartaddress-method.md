---
title: "ICorDebugMemoryBuffer::GetStartAddress (método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 97c08e87f63b36bfee5ade75e44f4867441bee92
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="c0cb1-102">ICorDebugMemoryBuffer::GetStartAddress (método)</span><span class="sxs-lookup"><span data-stu-id="c0cb1-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="c0cb1-103">Obtiene la dirección de inicio del búfer de memoria.</span><span class="sxs-lookup"><span data-stu-id="c0cb1-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0cb1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c0cb1-104">Syntax</span></span>  
  
```  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c0cb1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c0cb1-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="c0cb1-106">[out] Puntero a la dirección de inicio del búfer de memoria.</span><span class="sxs-lookup"><span data-stu-id="c0cb1-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0cb1-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c0cb1-107">Remarks</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="c0cb1-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c0cb1-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0cb1-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c0cb1-109">Requirements</span></span>  
 <span data-ttu-id="c0cb1-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0cb1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0cb1-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c0cb1-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c0cb1-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0cb1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0cb1-113">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0cb1-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0cb1-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0cb1-114">See Also</span></span>  
 [<span data-ttu-id="c0cb1-115">ICorDebugMemoryBuffer (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c0cb1-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 [<span data-ttu-id="c0cb1-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="c0cb1-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
