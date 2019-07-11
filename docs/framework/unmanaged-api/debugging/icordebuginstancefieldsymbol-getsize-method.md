---
title: Método ICorDebugInstanceFieldSymbol::GetSize
ms.date: 03/30/2017
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a4fdef8b5eaa99eed9605e7563110dda1b1f11f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760079"
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="baf89-102">Método ICorDebugInstanceFieldSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="baf89-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="baf89-103">Obtiene el tamaño, en bytes, del campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="baf89-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="baf89-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="baf89-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="baf89-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="baf89-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="baf89-106">[out] Puntero a la longitud del campo.</span><span class="sxs-lookup"><span data-stu-id="baf89-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="baf89-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="baf89-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="baf89-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="baf89-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="baf89-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="baf89-109">Requirements</span></span>  
 <span data-ttu-id="baf89-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="baf89-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="baf89-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="baf89-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="baf89-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="baf89-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="baf89-113">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="baf89-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baf89-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="baf89-114">See also</span></span>

- [<span data-ttu-id="baf89-115">ICorDebugInstanceFieldSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="baf89-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="baf89-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="baf89-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
