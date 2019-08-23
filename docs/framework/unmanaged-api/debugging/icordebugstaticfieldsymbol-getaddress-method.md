---
title: ICorDebugStaticFieldSymbol::GetAddress (método)
ms.date: 03/30/2017
ms.assetid: 5a6c9a5a-ec72-4c40-a9c3-cee7baa63687
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9d41b99d7410333cb6a22443271c1fcbc41c3594
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962697"
---
# <a name="icordebugstaticfieldsymbolgetaddress-method"></a><span data-ttu-id="7b6dc-102">ICorDebugStaticFieldSymbol::GetAddress (método)</span><span class="sxs-lookup"><span data-stu-id="7b6dc-102">ICorDebugStaticFieldSymbol::GetAddress Method</span></span>
<span data-ttu-id="7b6dc-103">Obtiene la dirección de un campo estático.</span><span class="sxs-lookup"><span data-stu-id="7b6dc-103">Gets the address of a static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b6dc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7b6dc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress(  
   [out] CORDB_ADDRESS *pRVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b6dc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7b6dc-105">Parameters</span></span>  
 <span data-ttu-id="7b6dc-106">pRVA</span><span class="sxs-lookup"><span data-stu-id="7b6dc-106">pRVA</span></span>  
 <span data-ttu-id="7b6dc-107">[out] Puntero a la dirección virtual relativa (RVA) del campo estático.</span><span class="sxs-lookup"><span data-stu-id="7b6dc-107">[out] A pointer to the relative virtual address (RVA) of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b6dc-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7b6dc-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7b6dc-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="7b6dc-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b6dc-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7b6dc-110">Requirements</span></span>  
 <span data-ttu-id="7b6dc-111">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b6dc-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b6dc-112">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="7b6dc-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b6dc-113">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b6dc-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b6dc-114">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b6dc-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b6dc-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b6dc-115">See also</span></span>

- [<span data-ttu-id="7b6dc-116">ICorDebugStaticFieldSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7b6dc-116">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="7b6dc-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="7b6dc-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
