---
description: 'Más información sobre: ICorDebugMemoryBuffer:: Getstartaddress ((método)'
title: ICorDebugMemoryBuffer::GetStartAddress (método)
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
ms.openlocfilehash: 46720d70b8a1019e712b577b24dec5d4c3d5a31d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722716"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="44854-103">ICorDebugMemoryBuffer::GetStartAddress (método)</span><span class="sxs-lookup"><span data-stu-id="44854-103">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>

<span data-ttu-id="44854-104">Obtiene la dirección de inicio del búfer de memoria.</span><span class="sxs-lookup"><span data-stu-id="44854-104">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44854-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="44854-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44854-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="44854-106">Parameters</span></span>  

 `address`  
 <span data-ttu-id="44854-107">[out] Puntero a la dirección de inicio del búfer de memoria.</span><span class="sxs-lookup"><span data-stu-id="44854-107">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44854-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="44854-108">Remarks</span></span>  
  
> [!WARNING]
> <span data-ttu-id="44854-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="44854-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44854-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="44854-110">Requirements</span></span>  

 <span data-ttu-id="44854-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44854-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44854-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="44854-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="44854-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44854-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44854-114">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44854-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44854-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="44854-115">See also</span></span>

- [<span data-ttu-id="44854-116">Método ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="44854-116">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="44854-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="44854-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
