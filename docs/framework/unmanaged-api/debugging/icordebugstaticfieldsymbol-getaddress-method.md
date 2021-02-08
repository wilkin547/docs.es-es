---
description: 'Más información sobre: ICorDebugStaticFieldSymbol:: GetAddress (método)'
title: ICorDebugStaticFieldSymbol::GetAddress (método)
ms.date: 03/30/2017
ms.assetid: 5a6c9a5a-ec72-4c40-a9c3-cee7baa63687
ms.openlocfilehash: 1944839ff6afc31dc3667111397cbb088b95b412
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801012"
---
# <a name="icordebugstaticfieldsymbolgetaddress-method"></a><span data-ttu-id="0aad3-103">ICorDebugStaticFieldSymbol::GetAddress (método)</span><span class="sxs-lookup"><span data-stu-id="0aad3-103">ICorDebugStaticFieldSymbol::GetAddress Method</span></span>

<span data-ttu-id="0aad3-104">Obtiene la dirección de un campo estático.</span><span class="sxs-lookup"><span data-stu-id="0aad3-104">Gets the address of a static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0aad3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0aad3-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress(  
   [out] CORDB_ADDRESS *pRVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0aad3-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0aad3-106">Parameters</span></span>  

 <span data-ttu-id="0aad3-107">pRVA</span><span class="sxs-lookup"><span data-stu-id="0aad3-107">pRVA</span></span>  
 <span data-ttu-id="0aad3-108">[out] Puntero a la dirección virtual relativa (RVA) del campo estático.</span><span class="sxs-lookup"><span data-stu-id="0aad3-108">[out] A pointer to the relative virtual address (RVA) of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0aad3-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0aad3-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0aad3-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="0aad3-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0aad3-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0aad3-111">Requirements</span></span>  

 <span data-ttu-id="0aad3-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0aad3-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0aad3-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0aad3-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0aad3-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0aad3-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0aad3-115">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0aad3-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0aad3-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="0aad3-116">See also</span></span>

- [<span data-ttu-id="0aad3-117">Interfaz ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="0aad3-117">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="0aad3-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="0aad3-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
