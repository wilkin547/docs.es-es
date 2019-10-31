---
title: 'ICorDebugStaticFieldSymbol:: (método)'
ms.date: 03/30/2017
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
ms.openlocfilehash: 0fa9c519a40624dd8c5471231263d2430738af87
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131767"
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="148bd-102">ICorDebugStaticFieldSymbol:: (método)</span><span class="sxs-lookup"><span data-stu-id="148bd-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="148bd-103">Obtiene el tamaño del campo estático, en bytes.</span><span class="sxs-lookup"><span data-stu-id="148bd-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="148bd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="148bd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="148bd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="148bd-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="148bd-106">[out] Puntero a la longitud del campo.</span><span class="sxs-lookup"><span data-stu-id="148bd-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="148bd-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="148bd-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="148bd-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="148bd-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="148bd-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="148bd-109">Requirements</span></span>  
 <span data-ttu-id="148bd-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="148bd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="148bd-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="148bd-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="148bd-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="148bd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="148bd-113">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="148bd-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="148bd-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="148bd-114">See also</span></span>

- [<span data-ttu-id="148bd-115">ICorDebugStaticFieldSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="148bd-115">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="148bd-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="148bd-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
