---
title: "ICorDebugMemoryBuffer::GetSize (método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a21198c70512af703e106870d1bc3f7882d62fe9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="ab65b-102">ICorDebugMemoryBuffer::GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="ab65b-102">ICorDebugMemoryBuffer::GetSize Method</span></span>
<span data-ttu-id="ab65b-103">Obtiene el tamaño del búfer de memoria en bytes.</span><span class="sxs-lookup"><span data-stu-id="ab65b-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab65b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ab65b-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ab65b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ab65b-105">Parameters</span></span>  
 `pcbBufferLength`  
 <span data-ttu-id="ab65b-106">[out] Puntero al tamaño del búfer de memoria.</span><span class="sxs-lookup"><span data-stu-id="ab65b-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab65b-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ab65b-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ab65b-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="ab65b-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab65b-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ab65b-109">Requirements</span></span>  
 <span data-ttu-id="ab65b-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab65b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab65b-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ab65b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ab65b-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab65b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab65b-113">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab65b-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab65b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab65b-114">See Also</span></span>  
 [<span data-ttu-id="ab65b-115">ICorDebugMemoryBuffer (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ab65b-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 [<span data-ttu-id="ab65b-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="ab65b-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
