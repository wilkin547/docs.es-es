---
title: Método ICorDebugInstanceFieldSymbol::GetSize
ms.date: 03/30/2017
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
ms.openlocfilehash: eb70c441441954e2ffce6ca832c58369c606b128
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782276"
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="6e137-102">Método ICorDebugInstanceFieldSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="6e137-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="6e137-103">Obtiene el tamaño, en bytes, del campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="6e137-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e137-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6e137-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e137-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="6e137-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="6e137-106">[out] Puntero a la longitud del campo.</span><span class="sxs-lookup"><span data-stu-id="6e137-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6e137-107">Notas</span><span class="sxs-lookup"><span data-stu-id="6e137-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6e137-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="6e137-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e137-109">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="6e137-109">Requirements</span></span>  
 <span data-ttu-id="6e137-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e137-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e137-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6e137-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6e137-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6e137-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6e137-113">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e137-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e137-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="6e137-114">See also</span></span>

- [<span data-ttu-id="6e137-115">ICorDebugInstanceFieldSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6e137-115">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="6e137-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="6e137-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
