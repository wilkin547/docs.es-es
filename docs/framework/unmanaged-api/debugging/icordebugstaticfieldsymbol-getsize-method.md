---
title: ICorDebugStaticFieldSymbol::GetSize (método)
ms.date: 03/30/2017
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
ms.openlocfilehash: deeb887dad38417e3ebb980f5ef2f89392388d65
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791822"
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="03eac-102">ICorDebugStaticFieldSymbol::GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="03eac-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="03eac-103">Obtiene el tamaño del campo estático, en bytes.</span><span class="sxs-lookup"><span data-stu-id="03eac-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03eac-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="03eac-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03eac-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="03eac-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="03eac-106">[out] Puntero a la longitud del campo.</span><span class="sxs-lookup"><span data-stu-id="03eac-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="03eac-107">Notas</span><span class="sxs-lookup"><span data-stu-id="03eac-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="03eac-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="03eac-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03eac-109">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="03eac-109">Requirements</span></span>  
 <span data-ttu-id="03eac-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03eac-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03eac-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="03eac-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="03eac-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03eac-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03eac-113">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03eac-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03eac-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="03eac-114">See also</span></span>

- [<span data-ttu-id="03eac-115">ICorDebugStaticFieldSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="03eac-115">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="03eac-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="03eac-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
