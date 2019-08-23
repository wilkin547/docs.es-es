---
title: Método ICorDebugInstanceFieldSymbol::GetSize
ms.date: 03/30/2017
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 94ff0ddc266ef9a3f5fabf56f43f1eba2c74e3a8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910175"
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="dc7f4-102">Método ICorDebugInstanceFieldSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="dc7f4-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="dc7f4-103">Obtiene el tamaño, en bytes, del campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="dc7f4-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc7f4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dc7f4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc7f4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dc7f4-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="dc7f4-106">[out] Puntero a la longitud del campo.</span><span class="sxs-lookup"><span data-stu-id="dc7f4-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc7f4-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dc7f4-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dc7f4-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="dc7f4-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc7f4-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dc7f4-109">Requirements</span></span>  
 <span data-ttu-id="dc7f4-110">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc7f4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc7f4-111">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="dc7f4-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dc7f4-112">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dc7f4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc7f4-113">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc7f4-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc7f4-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc7f4-114">See also</span></span>

- [<span data-ttu-id="dc7f4-115">ICorDebugInstanceFieldSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dc7f4-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="dc7f4-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="dc7f4-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
