---
description: 'Más información acerca de: ICorDebugMemoryBuffer:: método de método'
title: ICorDebugMemoryBuffer::GetSize (método)
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
ms.openlocfilehash: 7de23dd13a1e0ef841145e3845d7d0052ce3ef9a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754045"
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="c052d-103">ICorDebugMemoryBuffer::GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="c052d-103">ICorDebugMemoryBuffer::GetSize Method</span></span>

<span data-ttu-id="c052d-104">Obtiene el tamaño del búfer de memoria en bytes.</span><span class="sxs-lookup"><span data-stu-id="c052d-104">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c052d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c052d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c052d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c052d-106">Parameters</span></span>  

 `pcbBufferLength`  
 <span data-ttu-id="c052d-107">[out] Puntero al tamaño del búfer de memoria.</span><span class="sxs-lookup"><span data-stu-id="c052d-107">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c052d-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c052d-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c052d-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c052d-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c052d-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c052d-110">Requirements</span></span>  

 <span data-ttu-id="c052d-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c052d-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c052d-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c052d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c052d-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c052d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c052d-114">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c052d-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c052d-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="c052d-115">See also</span></span>

- [<span data-ttu-id="c052d-116">Método ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="c052d-116">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="c052d-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="c052d-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
