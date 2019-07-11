---
title: ICorDebugStaticFieldSymbol::GetSize (método)
ms.date: 03/30/2017
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4a30778a287b4115df552444549a92c006288005
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760751"
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="7ef42-102">ICorDebugStaticFieldSymbol::GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="7ef42-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="7ef42-103">Obtiene el tamaño del campo estático, en bytes.</span><span class="sxs-lookup"><span data-stu-id="7ef42-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ef42-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7ef42-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ef42-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7ef42-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="7ef42-106">[out] Puntero a la longitud del campo.</span><span class="sxs-lookup"><span data-stu-id="7ef42-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ef42-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7ef42-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7ef42-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="7ef42-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ef42-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7ef42-109">Requirements</span></span>  
 <span data-ttu-id="7ef42-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ef42-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ef42-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ef42-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ef42-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ef42-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ef42-113">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ef42-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ef42-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ef42-114">See also</span></span>

- [<span data-ttu-id="7ef42-115">ICorDebugStaticFieldSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7ef42-115">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="7ef42-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="7ef42-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
