---
title: ICorDebugStaticFieldSymbol::GetAddress (método)
ms.date: 03/30/2017
ms.assetid: 5a6c9a5a-ec72-4c40-a9c3-cee7baa63687
ms.openlocfilehash: be4d59fe668026c4b40be4c6d0afcf718c8157bd
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791847"
---
# <a name="icordebugstaticfieldsymbolgetaddress-method"></a><span data-ttu-id="8b285-102">ICorDebugStaticFieldSymbol::GetAddress (método)</span><span class="sxs-lookup"><span data-stu-id="8b285-102">ICorDebugStaticFieldSymbol::GetAddress Method</span></span>
<span data-ttu-id="8b285-103">Obtiene la dirección de un campo estático.</span><span class="sxs-lookup"><span data-stu-id="8b285-103">Gets the address of a static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b285-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8b285-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress(  
   [out] CORDB_ADDRESS *pRVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b285-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="8b285-105">Parameters</span></span>  
 <span data-ttu-id="8b285-106">pRVA</span><span class="sxs-lookup"><span data-stu-id="8b285-106">pRVA</span></span>  
 <span data-ttu-id="8b285-107">[out] Puntero a la dirección virtual relativa (RVA) del campo estático.</span><span class="sxs-lookup"><span data-stu-id="8b285-107">[out] A pointer to the relative virtual address (RVA) of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b285-108">Notas</span><span class="sxs-lookup"><span data-stu-id="8b285-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8b285-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="8b285-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b285-110">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="8b285-110">Requirements</span></span>  
 <span data-ttu-id="8b285-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b285-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b285-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8b285-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8b285-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b285-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b285-114">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b285-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b285-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="8b285-115">See also</span></span>

- [<span data-ttu-id="8b285-116">ICorDebugStaticFieldSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8b285-116">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="8b285-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="8b285-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
