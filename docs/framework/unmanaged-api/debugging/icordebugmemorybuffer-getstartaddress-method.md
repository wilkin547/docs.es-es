---
title: ICorDebugMemoryBuffer::GetStartAddress (método)
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
ms.openlocfilehash: f76bf1479db987e4956d8b876f67d629d927f956
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710770"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="c729b-102">ICorDebugMemoryBuffer::GetStartAddress (método)</span><span class="sxs-lookup"><span data-stu-id="c729b-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>

<span data-ttu-id="c729b-103">Obtiene la dirección de inicio del búfer de memoria.</span><span class="sxs-lookup"><span data-stu-id="c729b-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c729b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c729b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c729b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c729b-105">Parameters</span></span>  

 `address`  
 <span data-ttu-id="c729b-106">[out] Puntero a la dirección de inicio del búfer de memoria.</span><span class="sxs-lookup"><span data-stu-id="c729b-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c729b-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c729b-107">Remarks</span></span>  
  
> [!WARNING]
> <span data-ttu-id="c729b-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c729b-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c729b-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c729b-109">Requirements</span></span>  

 <span data-ttu-id="c729b-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c729b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c729b-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c729b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c729b-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c729b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c729b-113">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c729b-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c729b-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c729b-114">See also</span></span>

- [<span data-ttu-id="c729b-115">Método ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="c729b-115">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="c729b-116">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="c729b-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
