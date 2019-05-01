---
title: Método ICorDebugInstanceFieldSymbol::GetSize
ms.date: 03/30/2017
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8cc09de2120399dcfe309757d554e1de72e55f07
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946378"
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="3a0b3-102">Método ICorDebugInstanceFieldSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="3a0b3-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="3a0b3-103">Obtiene el tamaño, en bytes, del campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="3a0b3-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a0b3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3a0b3-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a0b3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3a0b3-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="3a0b3-106">[out] Puntero a la longitud del campo.</span><span class="sxs-lookup"><span data-stu-id="3a0b3-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a0b3-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3a0b3-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3a0b3-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="3a0b3-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a0b3-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3a0b3-109">Requirements</span></span>  
 <span data-ttu-id="3a0b3-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a0b3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a0b3-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3a0b3-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3a0b3-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3a0b3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3a0b3-113">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a0b3-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a0b3-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a0b3-114">See also</span></span>

- [<span data-ttu-id="3a0b3-115">ICorDebugInstanceFieldSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3a0b3-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="3a0b3-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="3a0b3-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
