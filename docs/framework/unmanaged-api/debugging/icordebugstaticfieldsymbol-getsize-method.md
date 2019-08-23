---
title: ICorDebugStaticFieldSymbol::GetSize (método)
ms.date: 03/30/2017
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d99e06c1093dbc67e9c1999e4b9ccabd6579340e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962659"
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="228a5-102">ICorDebugStaticFieldSymbol::GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="228a5-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="228a5-103">Obtiene el tamaño del campo estático, en bytes.</span><span class="sxs-lookup"><span data-stu-id="228a5-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="228a5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="228a5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="228a5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="228a5-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="228a5-106">[out] Puntero a la longitud del campo.</span><span class="sxs-lookup"><span data-stu-id="228a5-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="228a5-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="228a5-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="228a5-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="228a5-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="228a5-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="228a5-109">Requirements</span></span>  
 <span data-ttu-id="228a5-110">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="228a5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="228a5-111">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="228a5-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="228a5-112">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="228a5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="228a5-113">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="228a5-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="228a5-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="228a5-114">See also</span></span>

- [<span data-ttu-id="228a5-115">ICorDebugStaticFieldSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="228a5-115">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="228a5-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="228a5-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
