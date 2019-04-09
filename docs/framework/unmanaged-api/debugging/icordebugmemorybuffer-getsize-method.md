---
title: ICorDebugMemoryBuffer::GetSize (método)
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d687f2bbd3c20564368d4246961b56382ea14cf5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099682"
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="20673-102">ICorDebugMemoryBuffer::GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="20673-102">ICorDebugMemoryBuffer::GetSize Method</span></span>
<span data-ttu-id="20673-103">Obtiene el tamaño del búfer de memoria en bytes.</span><span class="sxs-lookup"><span data-stu-id="20673-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20673-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="20673-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20673-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="20673-105">Parameters</span></span>  
 `pcbBufferLength`  
 <span data-ttu-id="20673-106">[out] Puntero al tamaño del búfer de memoria.</span><span class="sxs-lookup"><span data-stu-id="20673-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20673-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="20673-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="20673-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="20673-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20673-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="20673-109">Requirements</span></span>  
 <span data-ttu-id="20673-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20673-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20673-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="20673-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="20673-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20673-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="20673-113">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="20673-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="20673-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="20673-114">See also</span></span>

- [<span data-ttu-id="20673-115">Método ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="20673-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="20673-116">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="20673-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
