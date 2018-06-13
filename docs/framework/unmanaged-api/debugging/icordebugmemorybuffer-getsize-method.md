---
title: ICorDebugMemoryBuffer::GetSize (método)
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: caf95e0b5c8d4ae942bb428f53d4e58313e0e78e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414757"
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="52ea7-102">ICorDebugMemoryBuffer::GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="52ea7-102">ICorDebugMemoryBuffer::GetSize Method</span></span>
<span data-ttu-id="52ea7-103">Obtiene el tamaño del búfer de memoria en bytes.</span><span class="sxs-lookup"><span data-stu-id="52ea7-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52ea7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="52ea7-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="52ea7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="52ea7-105">Parameters</span></span>  
 `pcbBufferLength`  
 <span data-ttu-id="52ea7-106">[out] Puntero al tamaño del búfer de memoria.</span><span class="sxs-lookup"><span data-stu-id="52ea7-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52ea7-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="52ea7-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="52ea7-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="52ea7-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52ea7-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="52ea7-109">Requirements</span></span>  
 <span data-ttu-id="52ea7-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52ea7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52ea7-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="52ea7-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="52ea7-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52ea7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52ea7-113">**Versiones de .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52ea7-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52ea7-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="52ea7-114">See Also</span></span>  
 [<span data-ttu-id="52ea7-115">ICorDebugMemoryBuffer (interfaz)</span><span class="sxs-lookup"><span data-stu-id="52ea7-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 [<span data-ttu-id="52ea7-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="52ea7-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
